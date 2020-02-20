SNS Following/follower

**Clients**

index.html

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





**Src**

contact.jsx

```javascript
import React, {Component} from "react";
import axios from 'axios';
axios.defaults.withCredentials=true;
const headers={withCredentials:true};
class Contact extends Component{
    state={
        name:''
    }
    memberInsert=()=>{
        const send_param={
            headers,
            nick:this.nameE.value,
            email:this.emailE_Contact.value,
            pw:this.pwE_Contact.value,
            comments:this.commentsE.value
        }
      axios.post('http://localhost:8081/member/insert',send_param)
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

home.jsx

```javascript
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

index.jsx

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import "./index.css";
import MenuContainer from "./MenuContainer";

ReactDOM.render(
    <MenuContainer/>,
    document.querySelector("#container")
);
```

menu.js

```javascript
import React, {Component} from "react";
import "./menu.css";
import $ from 'jquery';
import {} from "jquery.cookie";
import axios from 'axios';
axios.defaults.withCredentials=true;
const headers={withCredentials:true};

class Menu extends Component{
    state={
        login_nick:"",
        loginStyle:"inline-block",
        logoutStyle:"none"
    }
    logout=()=>{
        axios.get('http://localhost:8081/member/logout',{
                headers
        }).then((returnData)=>{
            if(returnData.data.message){
                $.removeCookie("login_nick");
                $.removeCookie("login_id");
                this.setState({
                    login_nick:"",
                    loginStyle:"inline-block",
                    logoutStyle:"none"
                });
            }
        });
    }
    login=()=>{
        const send_param={
            headers,
            email:this.emailE.value,
            pw:this.pwE.value
        } 
        axios.post('http://localhost:8081/member/login', send_param)
        .then((returnData)=>{
            console.log(returnData);
            if(returnData.data.nick){
                $.cookie("login_nick",returnData.data.nick);
                $.cookie("login_id",returnData.data.id);
                this.setState({
                    login_nick: returnData.data.nick,
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
        let login_nick;

        if($.cookie("login_nick")){
            login_nick=$.cookie("login_nick");
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
                    {login_nick}님 환영합니다
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

menubutton.jsx



```javascript
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



menuContainer

```javascript
import React, {Component} from "react";
import MenuButton from './MenuButton.js';
import Menu from './menu.js';
import Home from './Home';
import Post from './Post';
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
                    <li><NavLink to='/post'>Post</NavLink></li>
                    <li><NavLink to='/contact'>Sign up</NavLink></li>
                </ul>
                <div className="content">
                        <Route exact path="/" component={Home}></Route>
                        <Route path="/post" component={Post}></Route>
                        <Route path="/contact" component={Contact}></Route>
                </div>
            </HashRouter>
        </div>
        );
    }
}

export default MenuContainer;
```

post.jsx

```javascript
import React, {Component} from "react";
import axios from "axios";
import $ from 'jquery';
import { } from 'jquery.cookie';

axios.defaults.withCredentials=true;
const headers={withCredentials:true};

class Post extends Component{
    state={
        posts:[],
        followings:[],
        followers:[]
    }
    async componentWillMount (){
        const me=$.cookie('login_id');
        
        const send_param={
            headers,
            me
        }
        const result= await axios.post('http://localhost:8081/post/followState', send_param);
        console.log(result.data.followings.length);
        console.log(result.data.followers.length);
       /*  result.data.followings.forEach(e => {
            this.state.followings.push(e.nick);
        });
        result.data.followers.forEach(e => {
            this.state.followers.push(e.nick);
        }); */
        this.setState({
            followings:result.data.followings,
            followers:result.data.followers
        }); 
    }

    follow=async (you)=>{
        
        const me=$.cookie('login_id');
        alert(me +":"+ you);
        const send_param={
            headers,
            me,
            you
        }
        const result= await axios.post('http://localhost:8081/post/follow', send_param);
        console.log(result);
       
    }
    uploadPost= async()=>{
        const send_param={
            headers,
            id:$.cookie("login_id"),
            content:this.postE.value,
            img:''
        }
        try{
            await axios.post('http://localhost:8081/post/upload', send_param);
            const result=await axios.post('http://localhost:8081/post/getAllPosts',
            {headers});
            if(result.data.posts){
            this.setState({
                posts:result.data.posts
            });
        }
            console.log(result);
        }catch(err){
            console.log(err);
        }
    }
    render(){
        const postStyle={
            width:400,
            height:150,
            borderStyle:"solid",
            borderColor:"gray",
            margin:5

        }
        let posts=this.state.posts.map((post)=>{
            let nick=post.user.nick;
            let follow=<button onClick={()=>{this.follow(post.user.id)}}>팔로우하기</button>;
            if($.cookie('login_nick')===post.user.nick){
                nick='';
                follow='';
            }
            return <div key={post.id} style={postStyle}>
                {nick}  {follow}<br/>
                {post.content}
                </div>});

        let followings=this.state.followings.map((following)=>{
        return <div>{following.nick}</div>
        }); 
        let followers=this.state.followers.map((follower)=>{
            return <div>{follower.nick}</div>
            }); 

        return(
            <div>
                <h2>SNS Post </h2><span>팔로잉 목록<div >{followings}</div></span> <span>팔로워 목록<div>{followers}</div></span>
                <div>
                    <textarea ref={ref=>this.postE=ref} rows='5' cols='50'></textarea><br/>
                    <button>사진 업로드</button>
                    <button onClick={this.uploadPost}>짹짹</button>
                </div>
                <div>
                    {posts}
                </div>
            </div>
        );
    }
}

export default Post;
```



**CSS**

index.css

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



Menu.css

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

menubutton.css

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



////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

**helloWorld Router**



config (folder)

config.json

```json
{
  "development": {
    "username": "root",
    "password": "mysql",
    "database": "sns2",
    "host": "127.0.0.1",
    "port":"3307",
    "dialect": "mysql",
    "operatorsAliases": false
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql",
    "operatorsAliases": false
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql",
    "operatorsAliases": false
  }
}
```



**Model**

hashtag.js

```javascript
/* jshint indent: 2 */

module.exports = function(sequelize, DataTypes) {
  return sequelize.define('hashtag', {
   
    title: {
      type: DataTypes.STRING(45),
      allowNull: false,
      unique: true
    }
  },{
    tableName: 'hashtag',
    timestamps:true,
    paranoid:true
  });
};

```

index.js

```javascript
const Sequelize = require('sequelize');

const env = process.env.NODE_ENV || 'development';
const config = require(__dirname + '/../config/config.json')[env];
const db = {};

let sequelize = new Sequelize(config.database, config.username, config.password, config);

db.sequelize = sequelize;
db.Sequelize = Sequelize;

db.User=require('./User')(sequelize,Sequelize);
db.Post=require('./Post')(sequelize,Sequelize);
db.Hashtag=require('./Hashtag')(sequelize,Sequelize);

db.User.hasMany(db.Post);
db.Post.belongsTo(db.User);
db.Post.belongsToMany(db.Hashtag,{through:"PostHashtag"});
db.Hashtag.belongsToMany(db.Post,{through:"PostHashtag"});
db.User.belongsToMany(db.User,{
  foreignKey:'followingId',
  as:'Followers',
  through:'Follow'
});
db.User.belongsToMany(db.User,{
  foreignKey:'followerId',
  as:'Followings',
  through:'Follow'
});


module.exports = db;
```



post.js

```javascript
/* jshint indent: 2 */

module.exports = function(sequelize, DataTypes) {
  return sequelize.define('post', {

    content: {
      type: DataTypes.STRING(140),
      allowNull: true
    },
    img: {
      type: DataTypes.STRING(45),
      allowNull: true
    }
  }, {
    tableName: 'post',
    timestamps:true,
    paranoid:true
  });
};

```



user.js

```javascript
/* jshint indent: 2 */

module.exports = function(sequelize, DataTypes) {
  return sequelize.define('user', {
    email: {
      type: DataTypes.STRING(50),
      allowNull: false,
      unique: true

    },
    nick: {
      type: DataTypes.STRING(45),
      allowNull: false,
      unique: true
    },
    password: {
      type: DataTypes.STRING(45),
      allowNull: false
    }
  }, {
    tableName: 'user',
    timestamps:true,
    paranoid:true
  });
};

```



Routs(folder)

common.js

```javascript
const Post=require('../models').Post;


async function getAllPost(){
    try{
    const posts=await Post.findAll({
        include:{
            model:User,
            attributes:['id','nick'],
        },
        order:[['createdAt','DESC']],
    });
    return posts;
    }catch(err){
        console.log(err);
        return null;
    }
}

module.exports=getAllPost;
```

memberRouter.js

```javascript
const express = require('express');
const router = express.Router();
const mysql = require('mysql');
const User=require('../models').User;
const {getAllPosts}=require('./common');


const con = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "mysql",
  database:"nodejs",
  port:"3307"
});

router.post('/insert',async (req,res)=>{
    const nick=req.body.nick;
    const email=req.body.email;
    const password=req.body.pw;
    const comments =req.body.comments;
    try{
        const result = await User.create({
            email,
            nick,
            password,
        });
        console.log(result);
        res.json({message:nick});
    }catch(err){
        console.log(err);
        res.json({message:false});
    }
});

// router.post('/insert',(req,res)=>{
//     const name=req.body.name;
//     const email=req.body.email;
//     const pw=req.body.pw;
//     const comments=req.body.comments;
//     var sql = `INSERT INTO members (name,email, password, comments) VALUES (?,?,?,?)`;
//     con.query(sql, [name, email, pw, comments], function (err, result) {
//        if(err){
//            res.json({message:false});
//        }else{
//            res.json({message:name});
//        }
//     });
// });

router.get('/logout',(req,res)=>{
    req.session.destroy(()=>{
        res.json({message:true});
    });
});

router.post('/login',async (req, res)=>{
    console.log(req.body);
    var email = req.body.email;
    var password = req.body.pw;
    try{
        const result=await User.findOne({where:{email,password}});
        res.json({nick:result.nick,id:result.id});
    }catch(err){
        console.log(err);
        res.json({message:false});
    }
    // var sql = `SELECT * FROM members WHERE email = ? AND password = ?`;
    // con.query(sql, [email, pw], function (err, result) {
    //     if (err) {
    //         res.json({message:false});
    //     }else{
    //         req.session.email=email;
    //         res.json({message:result[0].name});
    //     }
    // });
});

module.exports=router;
```

postRouter.js

```javascript
const express = require('express');
const router = express.Router();
const Post=require('../models').Post;
const Hashtag=require('../models').Hashtag;
const User=require('../models').User;

router.post('/followState',async (req,res,next)=>{
    try{
        console.log(req.body);
        const user_me=await User.findOne({ 
            where:{
                id:req.body.me
            }
        });
        const followings=await user_me.getFollowings();
        const followers=await user_me.getFollowers();
        console.log(followings);
        res.json({followings,followers});
    }catch(err){
        console.log(err);
        res.json({message:false});
    }
});

router.post('/follow',async (req,res,next)=>{
    try{
       // console.log(req.body);
        const user_me=await User.findOne({ 
            where:{
                id:req.body.me
            },
        });
        await user_me.addFollowing(req.body.you);
        res.json({message:true});
    }catch(err){
        console.log(err);
        res.json({message:false});
    }
});
router.post('/getAllPosts',async (req,res,next)=>{
    try{
        const posts=await Post.findAll({
            include:{
                model:User,
                attributes:['id','nick'],
            },
            order:[['createdAt','DESC']],
        });
        //console.log("============");
       // console.log(posts);
        res.json({posts});
    }catch(err){
        console.log(err);
        res.json({message:false});
    }
});

router.post('/upload',async (req,res,next)=>{

    const content=req.body.content;
    const userId=req.body.id;
    const img=req.body.img;
    try{

        const post_result=await Post.create({
            content,
            userId,
            img
        });
        //console.log(post_result);
        const hashtags=req.body.content.match(/#[^\s]*/g); //자바스크립트에서 패턴을 정의하는 방법이에요 #을 기준으로 해서 뒤에는 어떤 문자든 상관 없이 모든 문자인데[] ^제외하고 \s띄워쓰기
        //console.log(hashtags);
        //const hashtag_result=await //여기 작성....
        if(hashtags){
            const hashtag_result= await Promise.all(hashtags.map((tag)=>{
                return Hashtag.findOrCreate({
                where: {title: tag.slice(1).toLowerCase()},
            });}));
            post_result.addHashtags(hashtag_result.map((r)=>{return r[0]}));//시퀄라이즈에서 제공하는 메서드, 이런 메서드는 정해져있는 메서드가 아니다. 포린 관계에 있는 테이블의 이름가지고 만들어지는 그때그때 만들어지는 메서드들이다.
        }

        //const posts=getAllPosts();
        //console.log(posts);
        res.json({message:true});
    }catch(err){
        res.json({message:false});
    }

});

module.exports=router;
```



**server.js**

```javascript
const memberRouter=require('./routes/memberRouter');
const express=require('express');
const app=express();
const cors=require('cors');
const session=require('express-session');
const sequelize=require('./models').sequelize;

sequelize.sync();

const corsOptions ={
    origin : true,
    credentials: true
};

app.use(cors(corsOptions));
app.use(express.json());
app.use(express.urlencoded({extended:true}));

app.use(session({
    resave:false,
    saveUninitialized:true,
    secret:"미녀 전은수ㅋ",
    cookie:{
        httpOnly:true,
        secure:false
    }
}));

app.use('/member',memberRouter);
app.use('/post',require('./routes/postRouter'));

app.get('/',(req,res)=>{
    res.json({ip:"111.222.333.444"});
});

app.listen(8081,()=>{
    console.log("8080 server ready...");
});
```

