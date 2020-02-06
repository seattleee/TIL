React의 특징

* 개발의 편리함이 아닌 UI의 동적 처리를 원활케함
* 비주얼적인 요소를 작은 컴포넌트로 분해하여 다룸



**HTML - Head, script**

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
```

**React -** **Head, script**

```react
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js">		 
	</script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-
    dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```



**Java Script - function**

```javascript
    <script>
        $(document).ready(function() {
            $('button').click(function() {
                let a = $('h1').text();
                $('h1').text(++a);
            });
        });
    </script>
```



 **React**

```javascript
class Counter extends React.Component{
     render(){ 
         return(<h1>{this.props.count}</h1>); 
     } 
} 
class CounterParent extends React.Component{
    state={message:0};
        a=()=>{
            this.setState({
                message:this.state.message +1
            });
        }; //state의 메시지에 +1 하라는 의미 2
    render(){ return(
    <div>
        <Counter count={this.state.message} />
        <button onClick={this.a}> + </button> 
    </div> // a라는 메세지를 onClick해라 1
        );
    } 
} 
ReactDOM.render(
    <CounterParent />, document.body ); //태크, 위치
```



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
        $(document).ready(function() {
            $('button').click(function() {
                let a = $('h1').text();
                $('h1').text(++a);
            });
        });
    </script>
    <style>
        div {
            background-color: greenyellow;
            width: 150px;
            text-align: center;
            padding-bottom: 25px;
            border-radius: 15px;
        }
    </style>
</head>

<body>
    <div>
        <h1>0</h1>
        <br><button> + </button>
    </div>
</body>

</html>
```





react jsx