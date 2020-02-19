몽고DB



index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-cookie/1.4.1/jquery.cookie.js"></script>
</head>
<body>
    <input id='name' placeholder="이름"><br>
    <input id='age' placeholder="나이"><br>
    <input type='checkbox' name='married'>결혼 여부<br>
    <button id='addMember'>등록</button>
    <button id='updateMember'>수정</button>

    <button id='getAllMember'>모든 맴버 보기</button>
    <div id='all_div'></div>

    <div form#comment-form> <fieldset> <legend>댓글등록</legend></fieldset>
        <div ></div>
    </div>
    <script>
        function deleteMember(_id){
            $.post('/member/delete',{_id}, function(returnData){
                    alert(returnData.message);
                });  
        }

        function display(_id,name,age,married){
            $.cookie('_id',_id);
            console.log($.cookie('_id'));

            $('#name').val(name);
            $('#age').val(age);
            if(married!=='false'){
                $('input[name="married"]').prop("checked",true);
            }else{
                $('input[name="married"]').prop("checked",false);
            }
        }
        $(document).ready(function(){
            $('#updateMember').click(function(){
                const _id=$.cookie('_id');
                const name=$('#name').val();
                const age=$('#age').val();
                const married=$('input[name="married"]').is(":checked");
                const send_param={
                    _id,name, age, married
                }
                $.post('/member/update',send_param, function(returnData){
                    alert(returnData.message);
                });  
            });
            $('#addMember').click(function(){
                const name=$('#name').val();
                const age=$('#age').val();
                const married=$('input[name="married"]').is(":checked");
                const send_param={
                    name, age, married
                }
                $.post('/member/add',send_param, function(returnData){
                    alert(returnData.message);
                });
            });

            $('#getAllMember').click(function(){
                $.post('/member/getAllMember',{},function(returnData){
                    console.log(returnData.users);
                    let result='<table border="1"><tr><td>아이디</td><td>이름</td>'
                        +'<td>나이</td><td>결혼</td><td>삭제여부</td></tr>';
                    returnData.users.forEach((e)=>{
                        result += `<tr><td onclick="display('${e._id}','${e.name}','${e.age}','${e.married}')">${e._id}</td><td>${e.name}</td><td>${e.age}</td><td>${e.married}</td><td><button onclick="deleteMember('${e._id}')">삭제</button></td></tr>`;
                    });
                    result += '</table>';
                    $('#all_div').html(result);
                });
            });
        });

    </script>
</body>
</html>
```

server.js

```javascript
const express=require('express');
const path=require('path');
const connect=require('./schemas');

connect();

const app=express();

app.use(express.static(path.join(__dirname,'public')));

app.use(express.json());
app.use(express.urlencoded({extended:true}));

//app.use('/member', require('./routes/memberRouter'));
app.use('/member', require('./routes/mongo_userRouter'));

app.listen(8080,()=>{
    console.log('8080 server ready..');
});

```



mongo_userRouter.js

```javascript
const express=require('express');
const path=require('path');
const connect=require('./schemas');

connect();

const app=express();

app.use(express.static(path.join(__dirname,'public')));

app.use(express.json());
app.use(express.urlencoded({extended:true}));

//app.use('/member', require('./routes/memberRouter'));
app.use('/member', require('./routes/mongo_userRouter'));

app.listen(8080,()=>{
    console.log('8080 server ready..');
});

```



```javascript
const express=require('express');
const router=express.Router();
const mongo = require('mongodb');

const MongoClient = mongo.MongoClient;
const url = "mongodb://localhost:27017/nodejs";
let dbo;

MongoClient.connect(url, function(err, db) {
    if (err) {
        console.log(err);
    }else{
        dbo = db.db("nodejs");
    }
});
router.post('/delete',(req,res)=>{
    const myquery = { _id: mongo.ObjectID(req.body._id)};
    dbo.collection("member").deleteOne(myquery, function(err, obj) {
        if (err){
            console.log(err);
            res.json({message:false});
        }else{
            res.json({message:true});
        }
    });
});

router.post('/update',(req,res)=>{
    const myquery={_id: mongo.ObjectId(req.body._id)};
    var newvalues = { $set: {name: req.body.name, age:req.body.age, married:req.body.married} };
    dbo.collection("member").updateOne(myquery, newvalues, function(err, result) {
      if (err) {
        console.log(err);
        res.json({message:false});
      }else{
        res.json({message:true});
      }
    });
});

router.post('/add',(req,res)=>{
    dbo.collection("member").insertOne(req.body, function(err, result) {
        if (err) {
            console.log(err);
            res.json({message:false});
        }else{
            res.json({message:true});
        }
    });
});

router.post('/getAllMember',(req,res)=>{
            dbo.collection("member").find({}).toArray(function(err, result) {
                if (err) {
                    console.log(err);
                    res.json({message:false});
                }else{
                    res.json({message:result});
                }
          }); //Connect to MongoDB
    });

module.exports=router;
```

index.js

```javascript
const mongoose=require('mongoose');

module.exports=()=>{
    const connect=()=>{
        if(process.env.NODE_ENV !=='production'){
            mongoose.set('debug',true);
        }
        mongoose.connect('mongodb://localhost:27017/nodejs',{dbName:'nodejs'},(err)=>{
            if(err){
                console.log("con error",err);
            }else{
                console.log('con ok');
            }
        });
    };
    connect();
    mongoose.connection.on('error',(err)=>{
        console.log('몽고DB 연결 에러', err);
    });
    mongoose.connection.on('disconnected',()=>{
        console.log("연결재시도");
        connect();
    });
    require('./user');
    require('./comment');
};
```

user.js

```js
const mongoose=require('mongoose');

const {Schema} =mongoose;

const userSchema=new Schema({
    name:{
        type:String,
        required:true,
        unique:true
    },
    age:{
        type:Number,
        required:true,
    },
    married:{
        type:Boolean,
        required:true,
    },
    comment:String,
    createdAt:{
        type:Date,
        default:Date.now
    }
});

module.exports=mongoose.model('User', userSchema);
```

comment.js

```javascript
const mongoose=require('mongoose');

const {Schema} =mongoose;
const {Types:{ObjectId}}=Schema;

const commentSchema=new Schema({
    commenter:{
        type:ObjectId,
        required:true,
        ref:'User'
    },
    comment:{
        type:String,
        required:true,
    },
    createAt:{
        type:Date,
        default:Date.now
    }
});

module.exports=mongoose.model('Comment', commentSchema);
```

