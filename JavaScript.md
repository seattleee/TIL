**JavaScript**

* How it works
  * Being a scripting language, **JavaScript cannot run on its own. In fact, the browser is responsible for running JavaScript code**. When a user requests an HTML page with JavaScript in it, the script is sent to the browser and it is up to the browser to execute it. The main advantage of JavaScript is that **all modern web browsers support** JavaScript. So, you do not have to worry about whether your site visitor uses Internet Explorer, Google Chrome, Firefox or any other browser. JavaScript will be supported. Also, JavaScript **runs on any operating system** including Windows,[ Linux ](https://www.guru99.com/unix-linux-tutorial.html)or Mac. Thus, JavaScript overcomes the main disadvantages of[ VBScript ](https://www.guru99.com/vbscript-tutorials-for-beginners.html)(Now deprecated) which is limited to just IE and Windows. 



<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<h3>내부 자바스크립트 작성</h3>
	<script src="welcome.js"></script>

```javascript
<h3>인라인 자바스크립트 작성</h3>
<button onclick="welcome(subject1)">웹프로그래밍</button>
<a href="welcome(subject2);">자바스트립트</a>
<div id="here"></div>
</body>
</html>
```

```javascript

<!DOCTYPE html>
<html>
<body>

<script>
	var v1=100;
    document.write(window.v1+1);
    
</script>

</body>
</html> 

```

<u>Description</u>

v1 값에 100을 두면

값이 101이 되고

v1 값에 "100"을 주면

값이 1001이 된다. 자리 수가 더해지는 것이 아니라 100 그리고 1이 있는 것이다.

JavaScript





```javascript
<!DOCTYPE html>
<html>
<body>

<script>

	var v1;
    document.write(window.v1+1);
	v1=100;
    document.write(window.v1+1);
</script>

</body>
</html> 
```



**worst case** 

* even if it represents the result "undefined", obviously not a good case.

* To cover up the case, you can use "hoisting" which lift up the function or commend, 'v1'





**산술연산**

```javascript
<script>
	var num1=15, num2=4;
    var grade1=2.8, grade2=4.3, grade3=15.0;
    var str1 = "Javascript", str2="Programming", str3="80";
    
    document.write(num1+num2+'<br>');
    document.write(num1*num2+'<br>');
    document.write(num1/num2+'<br>');
    document.write(num1++ +30 + '<br>');
    document.write(num1 + '<br>');
    document.write(--num2 + 30 +'<br>');
    document.write(num2+'<br>');
    document.write(num1+grade1 +'<br><br>');
    
</script>
```





Practice - NAMING CODE



```javascript
<body>

<script>

	for(prop in window){
    	document.write(prop + "<br>");
    }
	document.write("<hr>");
    document.write(name);
    
    document.write("<hr>");
    var name="hi";
    document.write(name);
  </script>
    
</body>
</html> 
```





* **비교연산자**

```javascript
<!DOCTYPE html>
<html>
<body>
<h3>비교연산자</h3>
<script>
	var num1=15, num2=4, num3=15;
    var grade=15.0;
    var str = "80";
    
    document.write( (num1 <= num2) +'<br>');
    document.write( (num1 != num3) +'<br>');
    document.write( (num3 == grade) +'<br>');
    document.write( (num3 === grade) + '<br>');
    document.write( (num3 ==15) + '<br>');
    document.write( (num3 === "15") +'<br>');
    document.write( (str ==80) +'<br>');
    document.write( (str ===80) +'<br><br>');
    
</script>

</body>
</html> 
```



* 자바스크립트의 문장 (치환문, 함수문)

```javascript
<script>
	var kor=92, math=77, eng=88;
    var total, avg;
    
    total=kor+math+eng; //치환문
    avg=total/3; //치환문
    document.write('<table border=1>'); //함수문
    document.write('<tr><td>국어</tr><td>'+kor+'</td></tr>'); //함수문
    document.write('<tr><td>수학</tr><td>'+math+'</td></tr>'); //함수문
    document.write('<tr><td>영어</tr><td>'+eng+'</td></tr>'); //함수문
    document.write('<tr><td>총점</tr><td>'+total+'</td></tr>'); //함수문
    document.write('<tr><td>평균</tr><td>'+avg+'</td></tr>'); //함수문
    document.write('</table>'); //함수문
    
</script>
```



* 자바스크립트 블록문

```javascript
<h3>블록문 사용 예</h3>
<script>
	var x,y,temp;
    // 블록문 사용
    x=30, y=70, temp="***";
    if(x>y) {temp=x; x=y; y=temp;}
    document.write("x= "+x+", y="+y+"<br>");
    
  //
    x=30, y=70, temp="***";
    if(x>y) temp=x; x=y; y=temp;
    document.write("x= "+x+", y="+y+"<br>");
    
  //
    x=30, y=70, temp="***";
    if(x>y) {temp=x;} x=y; y=temp;
    document.write("x= "+x+", y="+y+"<br>");
</script>
```



```javascript
		<script>
			var str="javascript";
            document.write(str.charAt(10));
            document.write(str);
		</script>
		
```



