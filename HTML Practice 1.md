**TestWeb4**

* mainServletjava

  ```html
  package controller;
  
  import java.io.IOException;
  
  import javax.servlet.RequestDispatcher;
  import javax.servlet.ServletException;
  import javax.servlet.http.HttpServlet;
  import javax.servlet.http.HttpServletRequest;
  import javax.servlet.http.HttpServletResponse;
  
  public class mainServlet extends HttpServlet {
  	/**
  	 * 
  	 */
  	private static final long serialVersionUID = 1L;
  
  	protected void process(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
  		request.setCharacterEncoding("utf-8");
  		
  		//요청분석(라우팅)
  		String sign=request.getParameter("sign");
  		if(sign.equals("memberInsert")){//회원가입처리
  			String id=request.getParameter("id");
  			String pw=request.getParameter("pw");
  			String name=request.getParameter("name");
  			//biz...
  			
  			request.setAttribute("name", id);
  			//view지정
  			RequestDispatcher disp=request.getRequestDispatcher("memberInsert_result.jsp");
  			disp.forward(request,response);}
  	}
  	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
  		process(request, response);
  		
  	}
  
  	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
  		process(request, response);
  	}
  
  }
  ```



* title.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="UTF-8">
  <title>첫페이지</title>
  <style type="text/css">
  	@import"css/table.css"
  </style>
  </head>
  <body>
  <table border="1">
  	<tr id="title"><td colspan="3"><h1>HOGI SHOP</h1></td></tr>
  	<tr>
  	 <td colspan="3">
  	 	<ul>
  	 		<li class="dropdown">
  	 			<a class="a_style" href="">Home</a>	 		
  	 		<li class="dropdown">
  	 			<a href="">HTML5</a>
  	 			<div class="dropdown-content">
  	 				<a href="#">HTML menu1</a>
  	 				<a href="#">HTML menu2</a>
  	 				<a href="#">HTML menu3</a>	
  	 			</div>
  	 		<li class="dropdown">
  	 			<a href="">CSS3</a>
  	 			<div class="dropdown-content">
  	 				<a href="#">CSS menu1</a>
  	 				<a href="#">CSS menu2</a>
  	 				<a href="#">CSS menu3</a>	
  	 			</div>
  	 		<li class="dropdown">
  	 			<a href="">Javascript</a>
  	 			<div class="dropdown-content">
  	 				<a href="#">JS menu1</a>
  	 				<a href="#">JS menu2</a>
  	 				<a href="#">JS menu3</a>	
  	 			</div>
   			</li>
  	 	</ul>
   	</td>
  	</tr>
  ```

  

* template.html

  ```HTML
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="UTF-8">
  <title>첫페이지</title>
  <style type="text/css">
  	@import"css/table.css"
  </style>
  </head>
  <body>
  <table border="1">
  	<tr id="menu"><td colspan="3">title</td></tr>
  	<tr>
  		<td class="c1">
  		<a href="memberInsert.html">회원가입</a>
  		</td>
  		<td>content</td>
  		<td class="c1">banner</td>
  	</tr>
  	<tr id="copyright"><td colspan="3">copyright</td></tr>
  	
   </table>
  </body>
  </html>
  ```

  

* menu.jsp

  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
  	<tr>
  		<td class="c1">
  		
  ```HTML
  	<a href="memberInsert.jsp">회원가입</a>
  	<br><br>
  	<a href="memberInsert.jsp">Take a look</a>
  	<br><br>
  	<a href="memberInsert.jsp">Trend</a>
  	</td>
  ```

* memberinsert.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
      
  <jsp:include page="title.jsp"></jsp:include>
  <jsp:include page="menu.jsp"></jsp:include>
      
  		<td>
  		<h3>회원가입</h3>
  			<form action="main" method="post">
  			<input type="hidden" name="sign" value="memberInsert" />
  			
  			ID<input type="text" name="id" required><br>
  			PW<input name="pw" type="password"><br>
  			NAME<input type="text" name="name"><br>
  			Class<input name="class" value="블록체인C반" disabled><br>
  			<input type="submit" value="회원가입">
  			
  			</form>
  	
  
  <jsp:include page="banner.jsp"></jsp:include>
  <jsp:include page="copyright.jsp"></jsp:include>
  ```



* memberinsert_result.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=utf-8"
      pageEncoding="utf-8"%>
  	
  <jsp:include page="title.jsp"></jsp:include>
  <jsp:include page="menu.jsp"></jsp:include>
      
  <td>${name}가입 되셨습니다 </td>
  
  <jsp:include page="banner.jsp"></jsp:include>
  <jsp:include page="copyright.jsp"></jsp:include>
  ```

* index.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
  
      <jsp:include page="title.jsp"></jsp:include>
      <jsp:include page="menu.jsp"></jsp:include>
      <jsp:include page="content.jsp" ></jsp:include>
      <jsp:include page="banner.jsp"></jsp:include>
      <jsp:include page="copyright.jsp"></jsp:include>
  ```

* copyright.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
      
  <tr id="copyright"><td colspan="3"><p>copyright</p></td></tr>
  	
   </table>
  </body>
  </html>
  ```

* content.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
      
  <td>
  	<ol>
  		<li>웹 서버 설치</li>
  		<li>HTML5 문서 작성하기</li>
  			<ul>
  				<li>하이퍼링크</li>
  				<li>테이블</li>
  				<li>입력양식</li>
  			</ul>
  		<li>CSS3 스타일시트 작성하기</li>
  			<ul>
  				<li>선택자</li>
  				<li>기본속성</li>
  				<li>고급속성</li>
  				<ul>
  					<li>
  					<a href="box.jsp">박스테스트</a>
  					</li>
  					<li>
  					<a href="box2.html">박스테스트2</a>
  					</li>
  				</ul>
  				<li>레이아웃</li>
  			</ul>
  		<li>자바스크립트 프로그래밍</li>
  		<li>HTML DOM 프로그래밍</li>	
  	</ol>
  
  
  </td>
  ```

* box2.html

```HTML
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<style>
	div.img{margin:20px 20px;padding:10px;
			width:200px;height:70px;}
		
	P{background:aqua;}
	div{background:skyblue;text-align:center;
		line-height:70px;}
	span{background:orange;border:5px solid red;
	padding:20px; margin:160px 150px;
	width:200px;height:70px;
	}
	
	img{bckground:green;}
	#body{width:500px;margin:0auto;background:lightgray;''}
</style>

<body>
<div id="b1"> 박스-1</div>
<div id="c1">
	<div id="c2">
	<div id="b2">박스-2</div>
	<div id="b3">박스-3</div>
	</div>
	<div id="b4">박스-4</div>
	</div>
	<div id="b5">박스-5</div>
	
<div id="body"></div>
이페이지는 각 박스 유형의 출력 예를 나타낸다.
<div>div태그와 p태그</div> 박스는 블록 유형이다.
<p>그리고 <span>span태그</span>박스는 인라인 유형이다.</p>
<p>img 태그로 표현하는 이미지
<img src=""alt="img태그"/> 박스는 인라인-블록유형이다</p>

</body>
</html>
```

* box.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
      
  <jsp:include page="title.jsp"></jsp:include>
  <jsp:include page="menu.jsp"></jsp:include>
      
  		<td>
  			<h3>For Men</h3>
  			<div id="b1">남자 옷</div>
  			<div id="b1">남자 신발</div>
  			<h3>For Women</h3>
  			<hr>
  			<span id="span1">여자 옷</span><br>
  			<span id="span1">여자 신발</span>
  			
  			</td>
  		
  		
  
  <jsp:include page="banner.jsp"></jsp:include>
  <jsp:include page="copyright.jsp"></jsp:include>
  ```

* banner.jsp

  ```HTML
  <%@ page language="java" contentType="text/html; charset=UTF-8"
      pageEncoding="UTF-8"%>
      
  <td class="c1">banner</td>
  	</tr>
  ```

* css

  ```css
  /*{color:green;font-size:15px'}*/
  table{width:100%;height:700px;border-collapse:collapse;border:2px soild green;}
  tr:first-child{background:pink;}
  #title{height:20%}
  #copyright{height:10%}
  .c1{width:15%}
  h1{background:orange;}
  h1:hover{background:pink;color:white;}
  h1:active{background:pink;color:black;}
  h1:before{content:url(../image/shopping.png);}
  h1:after{content:"(HTML+CSS+Javascript)";font-size:small;color:red;}
  p{background:aqua;}
  p::first-letter{color:red;font-size:50px;font-weight:bold;}
  p::first-line{background:gold;}
  /*
  li:first-child{color:red;}
  li:last-child{color:blue;}
  li:nth-child(2){color:yellow;}
  li:nth-last-child(2){color:gray;}
  */
  ol>li{color:red;}
  input[type="text"]{color:blue;}
  input[required]{background:gold;color:red;}
  input[disabled]{color:green;}
  
  h3{background:black;color:white;}
  #b1{background:blue;width:150px;height:50px;
  	margin:20px;
  	border-width:5px;
  	border-style:solid;
  	border-color:black;
  	padding:30px;
  }
  
  #b2{background:blue;width:150px;height:50px;
  
  	margin:20px;
  	border:10pxblackdouble;
  	padding:20px 30px
  }
  #b1,#b2{background:pink;color:purple;}
  #span1{background:pink;color:purple;}
  #span2{background:pink;}
  
  #style1{background:lightgray;width:200px;margin:0;padding:0;}
  
  #style2{background:lightgray;padding:6px;}
  
  ul{background: lightfray; padding: 6px;}
  li{display: inline; padding: 10px 20px;}
  li a{padding:5px 10px; color:color:black; text-decoration:none;}
  li a:hover {background: darkgray;}
  li.dropdown{display: inline-block;}
  .dropdown-content{display:none; position: absolute;background:ghostwhite; box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);}
  .dropdown-content a {display: block; padding: 12px 16px; text-decoration:none; text-align:left; color:black;}
  .dropdown-content a:hover{background: lavender;}
  .dropdown:hover .dropdown-content {display: block;}
  ```

