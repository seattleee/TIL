

```javascript
<body>
    <div id="container"></div>
    <script type="text/babel" >
        class Stuff extends React.Component{
            render(){
                return (
                    <div>
                        <h1 key="1"> Boring {Math.random() * 100} content!</h1>
                    </div>
                );
            }
        }
        function b(){
            let a=(propkey)=><div key={propkey}><Stuff /></div>
            let arr=[];

                for(let i=0;i<100;++i){
                    let a=<div key={i}><Stuff /></div>
                    arr.push(a);  //arr[i]=a; 이렇게 해도됨
                }
                    
            return arr;
        }

        ReactDOM.render(
            <div>{b()}</div>,        
        document.querySelector('#container'));
    </script>
</body>
```





```javascript
        function b(){
            const a= (propkey)=><div key={propkey}><Stuff /></div>;
            let arr=[];

                for(let i=0;i<100;++i){
                    arr.push(a(i));
                }
                    
            return arr;
        }
```





* 베이직 React

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <script type="text/babel">
    class HelloWorld extends React.Component{
        c;
        state={
            greeting:"나를잡아봐",
            no:Math.random()*600,
            color:"yellow"
        }
        a=()=>{
            this.setState({
                no:Math.random()*600
            });
        }
        b=()=>{
            this.setState({
                color:"red"
            });
        clearInterval(this.c);
        }
        componentDidMount(){
            console.log("ComponentDidMount 호출됨");
            this.c=setInterval(this.a,500);
        }
        render(){
            console.log("render 호출됨");
            const myStyle={
                backgroundColor:this.state.color,
                width:100,
                height:100,
                top:this.state.no,
                left:this.state.no,
                position:"fixed",
                borderRadius:50
            }
            return(
                <h1 onClick={this.b} style={myStyle}>{this.state.greeting} {this.props.name}</h1>
            );
        }
    }

    ReactDOM. render(
        <div>
       <HelloWorld name="이호경"/>
       </div>
        , document.body
    );

    </script>
</body>
</html>
```

