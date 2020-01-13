JavaScript 

https://developer.mozilla.org/ko/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript



* Primitive and reference data type

![img](https://postfiles.pstatic.net/MjAxOTExMThfMTkx/MDAxNTc0MDYyNzM4MjY2.6ev8M2ExkIuDpPjl5-Y2Zcbif0SrAGx0d6vXwPNK2sYg.vkf7HM4DyyfBdayFXd1y6d2BFScUdY2cQYQdY57A3bwg.PNG.dldnjswns516/image.png?type=w773)



둘의 가장 큰 차이점은 변수 선언시 메모리 공간에 데이터를

 직접 담는가? 아니면 다른곳을 참조하는 주소값을 담는가? 입니다.



프리미티브 타입은 직접 데이터를 담는 타입 입니다.

그리고 기본값이 있기 때문에 null값이 존재하지 않습니다.



|        | 타입    | 메모리 크기 | 기본값                                                       | 데이터 표현범위                                              |
| ------ | ------- | ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 논리형 | boolean | 1 byte      | false                                                        | true,false                                                   |
| 정수형 | byte    | 1 byte      | 0                                                            | -128~127                                                     |
| short  | 2 byte  | 0           | -32,768 ~32,767                                              |                                                              |
| int    | 4 byte  | 0           | -2,147,483,648~ 2,147,483,647                                |                                                              |
| long   | 8 byte  | 0L          | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807       |                                                              |
| 실수형 | float   | 4 byte      | 0.0F                                                         | 7개의 유효 숫자를 가지며,-3.4E+38의 근사값 ~7개의 유효 숫자를 가지며,3.4E+38의 근사값 |
| double | 8 byte  | 0.0         | 15개의 유효 숫자를 가지며,-1.7E+308의 근사값 ~15개의 유효 숫자를 가지며,1.7E+308의 근사값 |                                                              |
| 문자형 | char    | 2 byte      | '\u0000'                                                     | 0 ~ 65,535                                                   |





* Reference data type







**자바스크립트 기본문법**

* 자료형
  * number형

```javascript


<script>

var x=314e-2, y=12345e10;
var num1=99999999999999, num2=9999999999999999;

document.write("x="+x+"<br>");
document.write("y="+y+"<br>");
document.write("num1="+(num1)+"<br>");
document.write("num2="+(num2)+"<br>");
document.write("54/0="+(54/0)+"<br>");
document.write("-54/0="+(-54/0)+"<br>");
document.write("88/'pi'="+(88/'pi'));


</script>
```



* undefined 자료형

```javascript
<script>

var obj=new Object();
var num;

document.write (obj+'<br>');
document.write (num+'<br>');
obj=null;
document.write (obj+'<br>');
obj=undefined;
document.write (obj+'<br>');
document.write ( (undefined==null ) +'<br>');
document.write ( (undefined===null ));

</script>
```





* Typeof

  ```javascript
  var num1=3.145, num2=20, num3=100;
  var str1="58", str2="3.678",str3="javascript";
  var flag1=true, flag2=false;
  
  document.write(str1 + num2 + '<br>');
  document.write(Number(str1) + num2 + '<br>');
  document.write(parselnt(str1) + num2 + '<br>');
  document.write(parselnt(str2) + num2 + '<br>');
  document.write(parselnt(str3) + num2 + '<br>');
  document.write(parseFloat(str2) + num2 + '<br>');
  document.write(parselnt(num1) + num2 + '<br><hr>');
  
  document.write((num2) + num3 + '<br>');
  document.write((num2) + num3.toString() + '<br>');
  document.write(Boolean(num2) + num3.toString() + '<br>');
  document.write(str3 + Number(flag1) + '<br>');
  document.write(str3 + Number(flag2) + '<br>');
  ```

  



**Try again**

```
<script>

	var score;
	var grade;

	document.write("<h3>학점판정</h3>");
	score = prompt("성적을 입력하세요");
	switch (parseInt(score/10)) {
		case 10,9: grade="A"; break;
		case 8: grade="B"; break;
		case 7: grade="C"; break;
		case 6: grade="D"; break;		
		default: grade="F";
	}
	document.write("<hr>학점판정 결과:");
	document.write(score + " ("+grade+")");

</script>



<script>

	var score;
	var grade;

	document.write("<h3>학점판정</h3>");
	score = prompt("성적을 입력하세요");
	switch (parseInt(score/10)) {
		case 1:
		case 3:
		case 5:
		case 7:
		case 8:
		case 10:
		case 12: grade="31"; break;
			
		case 2: grade="28"; break;
		case 4: 
		case 6: 
		case 9:
		case 11:grade="30"; break;		
		
	}
	document.write("<hr>결과:");
	document.write(score + "월은" ("+일 까지 입니다+")");

</script>
```





``` <script>
<script>
sum=0;
for(i=1; i<100000; i=i+1) {
	sum=sum+i;
    if(sum>100000) break;
}

document.write("1부터의 N까지의 합이 처음으로 100,000을 넘을 때<br>");
document.write("N은 "+i+" 이고, 합은 "+sum+" 입니다. <hr>");


</script>


```





```

<script>
sum=0; count=0;
for(i=1; i<=100; i=i+1) {
	if (i%7==0) {count++;
    	continue;
    }
    sum=sum +i;
}
  
  document.write("1~100사이의 8의 배수 개수:" +count+"<br>");
  document.write("1~100사이의 8의 배수를 제외한 합:" +sum);
</script>

```

