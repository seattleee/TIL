

Sliding menu



html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Sliding Menu in React</title>
</head>
<body>
    <div id="container"></div>
</body>
</html>
```



index.jsx

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import "./index.css";
import MenuContainer from "./MenuContainer";

ReactDOM.render(
    <MenuContainer/>,
    document.querySelector("#container")
);
```



mainCountainer.jsx

```jsx
import React, {Component} from "react";
import MenuButton from './MenuButton.js';
import Menu from './menu.js';
import Home from './Home';
import Stuff from './Stuff';
import Contact from './Contact';
import {Route, NavLink, HashRouter} from 'react-router-dom';

class MenuContainer extends Component{
    constructor(props){
        super(props);

        this.state={
            visible:false
        }
        this.handleMouseDown =this.handleMouseDown.bind(this);
        this.toggleMenu=this.toggleMenu.bind(this);
    }

    handleMouseDown(e){
        this.toggleMenu();

        console.log("clicked");
        e.stopPropagation();
    }

    toggleMenu(){
        this.setState({
            visible: !this.state.visible
        });
    }

    render(){
        return(
        <div>
                <MenuButton handleMouseDown={this.handleMouseDown}/>
                <Menu handleMouseDown={this.handleMouseDown}
                    menuVisibility={this.state.visible}/>
            <HashRouter>
                <h1>YOYOBABY</h1>
                <ul className="header">
                    <li><NavLink exact to='/'>Home</NavLink></li>
                    <li><NavLink to='/stuff'>Menu</NavLink></li>
                    <li><NavLink to='/contact'>Sign up</NavLink></li>
                </ul>
                <div className="content">
                        <Route exact path="/" component={Home}></Route>
                        <Route path="/stuff" component={Stuff}></Route>
                        <Route path="/contact" component={Contact}></Route>
                </div>
            </HashRouter>
        </div>
        );
    }
}

export default MenuContainer;
```



menu.js

```js
import React, {Component} from "react";
import "./menu.css";
import $ from 'jquery';
import {} from "jquery.cookie";

class Menu extends Component{
    state={
        login_email:"",
        loginStyle:"inline-block",
        logoutStyle:"none"
    }
    logout=()=>{
        $.get('http://localhost:8080/member/logout',(returnData)=>{
            if(returnData.message){
                $.removeCookie("login_name");
                this.setState({
                    login_email:"",
                    loginStyle:"inline-block",
                    logoutStyle:"none"
                });
            }
        });
    }
    login=()=>{
        const send_param={
            email:this.emailE.value,
            pw:this.pwE.value
        } 
        $.post('http://localhost:8080/member/login', send_param, (returnData)=>{
            if(returnData.message){
                $.cookie("login_name",returnData.message);
                this.setState({
                    login_email:returnData.message,
                    loginStyle:"none",
                    logoutStyle:"inline-block"
                });
            }else{
                alert("login fail");
            }
            this.emailE.value='';
            this.pwE.value='';
            this.emailE.focus();

        });
    }

    
    render(){
        const loginStyle={
            display:this.state.loginStyle
        }
        const logoutStyle={
            display:this.state.logoutStyle,
            paddingLeft:50
        }
        let login_name;

        if($.cookie("login_name")){
            login_name=$.cookie("login_name");
            loginStyle.display="none";
            logoutStyle.display="inline-block";
        }

        let visibility ="hide";

        if(this.props.menuVisibility){
            visibility = "show";
        }
        return(
            <div id="flyoutMenu" onDrag={this.props.handleMouseDown}
                                className={visibility}>
                <div style={loginStyle}>
                    이메일<input ref={ref=>this.emailE=ref}/><br/>
                    비밀번호<input type="password" ref={ref=>this.pwE=ref}/> <br/>
                    <button onClick={this.login}>로그인</button>
                    <button>회원가입</button>
                </div>
                <div style={logoutStyle}>
                    {login_name}님 환영합니다
                    <button  onClick={this.logout}>로그아웃</button>
                </div>
                <h2><a href="/">Home</a></h2>
                <h2><a href="/">About</a></h2>
                <h2><a href="/">Contact</a></h2>
                <h2><a href="/">Search</a></h2>
            </div>
        );
    }
}
export default Menu;

```

redux.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://unpkg.com/redux@latest/dist/redux.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
</head>
<body>
    <button id="deleteBtn">delete</button>
    <input>
    <button id="addBtn">add</button>
    <br>
    <div></div>

    <script>
        function reducer(state,action){  //2 리듀서 작성
            if(state==undefined){
                state=[];
            }
            if(action.type==="add"){
                state.unshift(action.value);
                return state;
            }else if(action.type==="delete"){
                return state.filter((item)=>{return item !== action.value});
            }
          
        }
        const store=Redux.createStore(reducer);  //1 스토어 생성
        const state=store.getState();  //3 state 얻기

        $(document).ready(function(){
            store.subscribe(function(){ //4 스토어 구독
                $('div').text(store.getState());
            });

            $('#deleteBtn').click(function(){
                const data=($('input').val());
                const action={
                    type: "delete",
                    value: data
                };
                store.dispatch(action); //5 스토어에 액션 전달
                
                $('input').val('');
            });


            $('#addBtn').click(function(){
                const data=($('input').val());
                const action={
                    type: "add",
                    value: data
                };
                store.dispatch(action); //5 스토어에 액션 전달
                
                $('input').val('');
            });
        });
    </script>
</body>
</html>
```



homejsx

```jsx
import React, {Component} from "react";
import axios from 'axios';
class Contact extends Component{
    state={
        name:''
    }
    memberInsert=()=>{
        const send_param={
            name:this.nameE.value,
            email:this.emailE_Contact.value,
            pw:this.pwE_Contact.value,
            comments:this.commentsE.value
        }
      axios.post('http://localhost:8080/member/insert',send_param)
      .then((returnData)=>{
          if(returnData.data.message){
                this.setState({
                    name:returnData.data.message
                });
          }else{
              alert("회원 가입 오류");
          }
      })
      .catch((err)=>{
          console.log(err);
      });
    }
    render(){
        if(this.state.name){
            return(
                <div>
                    <h2>{this.state.name}님 회원가입 되셨습니다.</h2>
                </div>
            );
        }else{
             return(
                <div>
                    <h2>Contact</h2>
                    <p>회원가입</p>
                    이름<input ref={ref=>this.nameE=ref} /><br/>
                    이메일<input ref={ref=>this.emailE_Contact=ref}/><br/>
                    비밀번호<input ref={ref=>this.pwE_Contact=ref}/><br/>
                    Comments<input ref={ref=>this.commentsE=ref}/><br/>
                    <button onClick={this.memberInsert}>회원가입</button>
                </div>
            );
        }
    }
}

export default Contact;
```



home jsx

```jsx
import React, {Component} from "react";

class Home extends Component{
    render(){
        return(
            <div>
                <h2>HELLO</h2>
                <p>KINGDAE....</p>
            </div>
        );
    }
}

export default Home;
```



stuff.jsx

```jsx
import React, {Component} from "react";

class Stuff extends Component{
    render(){
        return(
            <div>
                <h2>Stuff</h2>
                <p>KINGSTUFF....</p>
            </div>
        );
    }
}

export default Stuff;
```



menubutton.js

```jsx
import React, {PureComponent} from "react";
import './MenuButton.css';

class MenuButton extends PureComponent{
    render(){
        return(
            <button id="roundButton" onMouseDown={this.props.handleMouseDown}></button>
        );
    }
}

export default MenuButton;
```



css



- index.css

```css
body{
    background-color: yellow;
    font-family: sans-serif;
    font-size: 20px;
    padding: 25px;
    margin: 0;
    overflow: auto;
}

#container li{
    margin-bottom: 10px;
}
h1,h2,p,ul,li{
    font-family: sans-serif;
}

ul.header li{
    display: inline;
    list-style-type: none ;
    margin: 0;
}
ul.header{
    background-color: #111;
    padding:0;
}
ul.header li a{
    color:#FFF;
    font-weight: bold;
    text-decoration: none;
    padding: 20px;
    display:inline-block;
}

.content{
    background-color: #FFF;
    padding:20px;
}

.content h2{
    padding:0;
    margin:0;
}

.content li{
    margin-bottom:10px;
}
.active{
    background-color:#0099FF;
    
}
```



menu.css



```css
#flyoutMenu{
    width:30vw;
    height:100vh;
    background-color:rgb(196, 255, 216);
    position:fixed;
    top:0;
    left:0;
    transition:transform .3s
        cubic-bezier(0, .52,0,1);
    overflow:scroll;
    z-index:1000;
}
#flyoutMenu.hide{
    transform:translate3d(-100vw,0,0);
}
#flyoutMenu.show{
    transform:translate3d(0vw,0,0);
    overflow:hidden;
}
#flyoutMenu h2 a{
    color:#333;
    margin-left:15px;
    text-decoration:none;
}
#flyoutMenu h2 a:hover{
    text-decoration:underline;
}


```

menubutton css

```css
#roundButton{
    background-color: #96D9FF;
    margin-bottom:20px;
    width:50px;
    height: 50px;
    border-radius: 50%;
    border: 10px solid #0065A6;
    outline:none;
    transition: all .2s cubic-bezier(0, 1.26, .8, 1.28);
}

#roundButton:hover{
    background-color: #96D9FF;
    cursor:pointer;
    border-color: #003557;
    transform:scale(1.2,1.2);
}

#roundButton:active{
    border-color: #003557;
    background-color: #FFF;
}
```

