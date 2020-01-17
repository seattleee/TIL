**mainservlet**



```javascript
package controller;
		
		import java.io.BufferedReader;
import java.io.IOException;
import java.io.PrintWriter;
		

		import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
		

import org.apache.jasper.tagplugins.jstl.core.Out;
import org.json.simple.*;
		
		public class mainservlet extends HttpServlet {
			private static final long serialVersionUID = 1L;
		
			protected void process(HttpServletRequest request, HttpServletResponse response) 
					throws ServletException, IOException {
				
				request.setCharacterEncoding("UTF-8");
				response.setContentType("application/json;charset=utf-8");
				PrintWriter out=response.getWriter();
				BufferedReader br=request.getReader();
				JSONObject obj=(JSONObject)JSONValue.parse(br);
				
				String sign = (String)obj.get("sign");
				
				if(sign != null){
					
					if(sign.equals("login")){

						String id=(String)obj.get("id");
						System.out.println(id+":"+obj.get("pw"));
						
						obj=new JSONObject();
						//login 처리 biz
					
						boolean flag=true;
						if(flag){
							obj.put("resultCode",1);
							obj.put("message",id+"님 환영합니다");
						}else{
							obj.put("resultCode",0);
							obj.put("message", "다시로그인하세요");
						}
						
					}else if(sign.equals("logout")){
						//logout처리 ==> 할당된 세션을 종료
						obj=new JSONObject();
						System.out.println("로그아웃");
						obj.put("message", "로그아웃되셨습니다");
					
					}else if(sign.equals("signin")){
						obj=new JSONObject();
						obj.put("message", "회원가입 되었습니다");
					
					}else if(sign.equals("send")){
						String money=(String)obj.get("money");
						obj=new JSONObject();
						obj.put("message", money+"원이 후원 되었습니다");
						
					}else if(sign.equals("question")){
					String question=(String)obj.get("question");
					obj=new JSONObject();
					obj.put("message", question+"이 전송 되었습니다");
					
				}
					
					out.print(obj);
					
				} else {
					System.out.println("sign=null");
			
				}
			
			}			
		
	protected void doGet(HttpServletRequest request, HttpServletResponse response) 
			throws ServletException, IOException {
		process(request, response);
	}
	protected void doPost(HttpServletRequest request, HttpServletResponse response) 
			throws ServletException, IOException {
		process(request, response);
	}

}
```





**Index10**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>첫페이지</title>
<style type="text/css">
	@import"css/table.css"
</style>

	<meta name="viewport" content="width=device-width, initial-scale=1">
 	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
 	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
 	<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
  	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"></script>
  	<script src="./js/my.js"></script>
	
</head>
<body>
<table border="1">
	<tr id="title"><td colspan="3"><h1>&nbsp&nbsp&nbsp&nbsp My DID</h1></td></tr>
	<tr>
	 <td colspan="3">
	 	<ul>
	 		<li class="dropdown">
	 			<a class="a_style" href="">Home</a>	 		
	 		<li class="dropdown">
	 			<a href="">Our Company</a>
	 			<div class="dropdown-content">
	 				<a href="#">회사 소개</a>
	 				<a href="#">히스토리</a>
	 				<a href="#" id="hi">인사말</a>	
	 			</div>
	 		<li class="dropdown">
	 			<a href="">Board</a>
	 			<div class="dropdown-content">
	 				<a href="#">Q & A</a>
	 				<a href="#">홍보</a>
	 				<a href="#">자주 묻는 질문</a>	
	 			</div>
	 		<li class="dropdown">
	 			<a href="">Contact us</a>
	 			<div class="dropdown-content">
	 				<a href="#">연락처</a>
	 				<a href="#" id="map">지도</a>
	 				<a href="#">지점 안내</a>	
	 			</div>
 			</li>
	 	</ul>
 	</td>
	</tr>
	<tr>
		<td class="c1">
		
		<div class="p2">
		<button id="join" type="button" class="btn btn-primary">회원가입</button></div><br><br>
		<div id="logDiv"><button type="button" class="btn btn-primary" id="login">로그인</button></div>
		<br><br>
		<a href="memberInsert.html">MY DID 소개</a>
		<br><br>
		</td>
	<td id="banner" >
		<img src="./image/mydid1.png"><br><br>
					<ul>
						<li>
						<a href="serviceindetail.html">Service in Detail </a>
						</li>
						<li>
						<a href="#" id="ask">후원 문의</a>
						</li>
					</ul>
	
	
	</td>
	<td class="c1"><button id="sponsor">후원</button></td><br>
	<tr id="copyright"><td colspan="3"><p>My DID</p></td></tr>
	
 </table>
</body>

</html>

```



```javascript

```

**My JS**



```javascript
$(document).ready(function(){
	//로그인 폼 콘텐츠
	let login_html_content = "<hr>";
	login_html_content += "ID<input id='form_id'><br>";
	login_html_content += "PW<input type='password' id='form_pw'><br>";
	login_html_content += "<button id='login_btn'>login</button>";
	//회원가입 폼 콘텐츠
	let join_html_content = "<hr>";
	join_html_content += "ID<input id='form_id'><br>";
	join_html_content += "PW<input type='password' id='form_pw'><br>";
	join_html_content += "NAME<input type='name' id='form_name'><br>";
	join_html_content += "<button id='signin_btn'>sign in</button>";

	
	
	//로그아웃 버튼을 눌렀을 때
	$(document).on("click", "#logout",function(){
		
		let temp={sign:"logout"};
		var jsonOBJ = JSON.stringify(temp);
		$.ajax({url:"main", 
			type:"POST",
			data:jsonOBJ,
			dataType:"json",
			success:function(returnData){
				if(returnData){
					alert("로그아웃");
				}else if(returnData.resultCode==0){
					alert(returnData.message);
				}
			},
	       error: function(err) {
	           alert(err);
	       }
		});
		
	});
	
	//회원가입 버튼을 눌렀을 때
	$(document).on("click", "#join",function(){
		
//		if(this.textContent != '로그아웃'){ 
			$('#banner').html(join_html_content);
//		}
			
	});
	
	//로그인 버튼을 눌렀을 때
   $('#login').click(function(){
      if(this.textContent != '로그아웃'){ 
	      $('#banner').html(login_html_content);
      }
   });
   
   //회원가입 폼에서 sign in 버튼을 눌렀을 때
   $(document).on("click","#signin_btn", function(){
	   let id_val=$('#form_id').val();
	   let pw_val=$('#form_pw').val();
	   let name_val=$('#form_name').val();
	   let temp={
			   sign:"signin",
			   id:id_val,
			   pw:pw_val,
			   name:name_val
	   };
	   
	   var jsonOBJ = JSON.stringify(temp);
	   
	   //alert(jsonOBJ.id+":"+jsonOBJ.pw);
	   
	   $.ajax({url:"main", 
		   type:"POST",
		   data:jsonOBJ,
		   dataType:"json",
		   success:function(returnData){
//				   alert(returnData.message);
				   //$('#login').remove();
			   		$('#join').remove();
			   	
				   $('#banner').html(returnData.message);
		   },
		   error: function(err) {
			   alert(err);
		   }
	   });
	   $(document).on("click","#logout", function(){
		   $('#banner').html(login_html_content);
		   $('#logout').remove();
		   $('#logDiv').html("<button type='button' class='btn btn-primary' id='login'>로그인</button>");
	   });
	   
   });

   //지도
   $('#map').click(function(){
	 //지도 폼 콘텐츠
		let map_html_content = "<hr>";
		map_html_content += "MAP<img src= 'image/location.png'><br>";
		
		$('#banner').html(map_html_content);
   });
	
   //인사말
   $('#hi').click(function(){
	 //인사말 폼 콘텐츠
		let hi_html_content = "<hr>";
		hi_html_content += "HI<p>Welcome to My DID</p><br>";
		      
		$('#banner').html(hi_html_content);
   });
   
   //후원 폼 콘텐츠
   $('#sponsor').click(function(){
	   let sponsor_html_content = "<hr>";
   sponsor_html_content += "money<input id='money'><br>";
   sponsor_html_content += "<button id='send'>complete</button>";
   $('#banner').html(sponsor_html_content);   
   });
   
   $(document).on("click","#send", function(){
	   let money=$('#money').val();
	   let temp={
			   sign:"send",
			   money:money
			  
	   };
	   
	   var jsonOBJ = JSON.stringify(temp);
   
	   $.ajax({url:"main", 
		   type:"POST",
		   data:jsonOBJ,
		   dataType:"json",
		   success:function(returnData){
				   $('#banner').html(returnData.message);
		   },
		   error: function(err) {
			   alert(err);
		   }
	   });
   });
   
   //후원 폼 콘텐츠
   $('#ask').click(function(){
	   let ask_html_content = "<hr>";
   ask_html_content += "question<input id='question'><br>";
   ask_html_content += "<button id='sendquestion'>전송</button>";
   $('#banner').html(ask_html_content);   
   });
   
   $(document).on("click","#sendquestion", function(){
	   let question=$('#question').val();
	   let temp={
			   sign:"question",
			   question:question
			  
	   };
	   
	   var jsonOBJ = JSON.stringify(temp);
   
	   $.ajax({url:"main", 
		   type:"POST",
		   data:jsonOBJ,
		   dataType:"json",
		   success:function(returnData){
				   $('#banner').html(returnData.message);
		   },
		   error: function(err) {
			   alert(err);
		   }
	   });
   });
	      
   //로그인 화면에서 id/pw입력 후 로그인 버튼을 눌렀을 때
   $(document).on("click","#login_btn", function(){
	   let id_val=$('#form_id').val();
	   let pw_val=$('#form_pw').val();
	   let temp={
			   sign:"login",
			   id:id_val,
			   pw:pw_val
	   };
		
	   var jsonOBJ = JSON.stringify(temp);
	   
		//alert(jsonOBJ.id+":"+jsonOBJ.pw);
		 
		$.ajax({url:"main", 
				type:"POST",
				data:jsonOBJ,
				dataType:"json",
				success:function(returnData){
					if(returnData.resultCode==1){
						alert(returnData.message);
						$('#login').remove();
						$('#logDiv').html("<button type='button' class='btn btn-primary' id='logout'>로그아웃</button>");
						$('#banner').html("<img src='image/CANADA.png'width='300'>");
				}else if(returnData.resultCode==0){
						alert(returnData.message);
				}
			},
		       error: function(err) {
		           alert(err);
		       }
			});
		$(document).on("click","#logout", function(){
			$('#banner').html(login_html_content);
			$('#logout').remove();
			$('#logDiv').html("<button type='button' class='btn btn-primary' id='login'>로그인</button>");
		});
		
	});

});
```

