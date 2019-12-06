# IT서비스와 보안

* 블록체인 활용 이해

  암호화

####       비도 = 암호화 강도

​       P    ---->    A    ---> E

​                     **"key"**



키운영 방식에 따라 대칭키 암호화 방식과 비대칭키 암호화 방식으로 분류대칭키 암호화 방식 = 암호화 키와 복호화 키가 동일~~~~~~ = 유일키, **비밀키**, 관용 암호화 방식

단점 : 키 분배 및 관리의 문제   

​              **A                                                              B**  

   data   +   skey         -------- ??? ---------->         skey   ⇐    상대방에게 비밀키를 어떻게 전달할 것인가?    

​             ||                   → 키 분배의 문제   

​         E(data)                  --------------------->        E(data)



​        A ----------------> B            ⇒ 통신 대상에 비례하여 키를 관리해야 한다.    

​     skey_ab                              → 키 관리의 문제    

​             ----------------> C    

​      skey_ac      

​               ----------------> D       

​      skey_ad  

비대칭 암호화 방식

대칭키 암호화의 단점을 개선하기 위해서 개발

암호화에 사용되는 키와 복호화에 사용되는 키가 상이(=다르다)

유일키(x) → 개인키 + 공개키 

비밀키(x) → 공개키는 외부에 오픈

비대칭 암호화 방식을 통한



기밀성 보장 방법 

-(송신측) 수신자의 공개키를 암호화하고, 

-(수신측) 수신자의 개인키로 복호화

인증, 원본증명, 부인방지를 보장하는 방법

-(송신측) 송신자의 개인키로 암호화 ⇒ (전자)서명

-(수신측) 송신자의 공개키로 복호화 ⇒ (서명)검증

비대칭 암호화 방식의 단점 → 대칭 암호화 방식에 비해 속도가 느리다.



#### Types of Blockchain

#####  Public vs Private (Decentralize)

* Public

  Permissionless / e.g bitcoin 

* Private

​       Permissioned / for business

* Consortium 

​       Permissioned / dealing with transactions quickly / Ripple, hyperledger



#### blockchain Technology Stack



#### Skills

##### Block

* A bundle of valid transcations
* The number of  tansactions in a block : average 1,400

* Size : 1.14MB
* Heighet : +1 as Genesis Block(0) comes out
* Depth : = Confirm, +1 by adding a new block(1)



![img](https://lh4.googleusercontent.com/jkOJYB5Xp_AhFvJvSmzSOd5X26Fhci-sqBq4qHKqa_Dbc_Jng_ySNVz2qp-3TRcufTSxnGk_rlB7qlowHWyKdZvZrJUBPt5rewUU--t4-6zcdaLCAoCgfiSYwfvWxvq2X8_tEV3R)



##### Block Hash

![img](https://lh5.googleusercontent.com/KPUJTJ_oHp1ggu07zLEJZf2d5TTBe4w-Pm6DkTbVlkGTtFPIynjwmZKBMMgr_anl_Rmrm3SElKMgr0ks1_M_laPD5RX6y99l_QDLLkDiWluxEgBLghYDo7tLeb7v1HqN5PTSpfl6)

![img](https://lh5.googleusercontent.com/h9I2yp63CTQvbIbdFTgj2lACJ50cB01Cg5vIXDi_eNclJXETr8tq0qW-oRALd2Vvn3G2aQ_kPpr3Hy6lklYOwIJuk6tdU0KF4SsVaO9a_sW5abX7NVTe0yp63Qm6YSyN3Iy3NkS3)

##### 

##### Transaction

* ![](https://lh3.googleusercontent.com/I3CphYp-Cv73D05ocn_0dj_F3vJLjhV1vxAv0lH2EnDWsW5JlXcRveqZXpFy7p3UQYIkCX5zm0WmoWXNbOm2fOLMaxE0CmDrnRSf4url5d251GQZh1igjvTw6c4gvzJTYV_eR_4O)



![img](https://lh5.googleusercontent.com/oLUmoQiLoGyTuqXqoECpXs60vUQNYOjV56lQu6RaZEislSsqSZmO2sM5fNJKKSpTsP4kC6LOAOGMTDSBltkPucQlOfMfy6F1mvB3pRQ_OaW7t_HMSH1toA3U5dL9bQX3J25uc-4b)

UTXO : 자산에 대한 소유자를 지정해주는 방식

![img](https://lh6.googleusercontent.com/HTrAYSdlhG3SbdtSlNQbbtaaC2tg5aqHVCxwaiSNFn1acCy1R2v-AqShKR3fwBi5mHXLiu-j5dS3MuGDQOBuhmLT2yfjrpr2cjIB78Mmx1tVd6vEX4tyN4KTm2tnLlsaZmCYQkvH)

![img](https://lh5.googleusercontent.com/4U_W342HCBcZrz2rlsdzR0hrGJPUlPwIlVw4NBrZmZsZbj4mHRzuFa8_PHccwMmqW6eokkece7trzfihG67JaswxLxMFWMuqUQqK6ja0SjKPomBqduefSM6ZIjC2C70-iCmf7wE9)

Symmetic-key

![img](https://lh6.googleusercontent.com/Au-zuTBIXYYpTUG2kpFVgTy3aOznpGvAIwxDv-PSRYRHtrEAPXXHxRDVqWi9PD-sntvy2vNMw4ar9KdB1PjMYJHYuLytcwn6EOaHt9HRzby_-KCJcsrgtFL9lFATRecDPR7lRPiJ)

public-key

 ![img](https://lh5.googleusercontent.com/gKIT3H9vDAhkgTtP0GXZG-D68lq7-ubldD2WvFzNB7QifIx2i1XuZAH_4F_kd_T8sZJ62SdihvcriF7gLRO-ZbGSLlOr8e0eZbde7tY1KsDQlw9jUlvODXRWRciLUhj4_8WjSryi)





![img](https://lh3.googleusercontent.com/2hzkZpk8H-bx5Ns1zZkUNBzztzXT0hHHktEsCP93HNDOPULm0q1PTWCvmCr31SGNU3nee1gicpIVQgL_1mVNj1sS_RHMCMeDw5_-q6SJI_jzyGfY3MWUvaLG87zCPAAr5CIylSyu)



**전자 서명 (Important)**

![img](https://lh5.googleusercontent.com/4U_W342HCBcZrz2rlsdzR0hrGJPUlPwIlVw4NBrZmZsZbj4mHRzuFa8_PHccwMmqW6eokkece7trzfihG67JaswxLxMFWMuqUQqK6ja0SjKPomBqduefSM6ZIjC2C70-iCmf7wE9)

![img](https://lh6.googleusercontent.com/BX4KyQPb7bn0ZnNU1nINkIMNUZh8BEI1PyQBoigCGqXrvNeeRZLlvYH4Jj9BFjnoIhCQUpMQ67MybIJ-J1byfu1FnirOLfhKVW2CBOXIV_gzs3RWz1jKUgt83etxBJqV8p5br14b)

![img](https://lh6.googleusercontent.com/15pqwvumukYg0yCcuCWGQKtz2FXXktdSdb0o8SWWa_BOZPRPMDOaTW_cQcxSOTn4g5pYaJuaPvF0BQt0-USI5aP_qLzBEmP0aoOKDrV3Z0HjqmqjEOGstjEUekx2vPJXGeRQRSC4)

![img](https://lh5.googleusercontent.com/hCGpe9sIxvQXcPF7seA-9ky7Dab0Qr4tCt0jYAdBx1lRXLGFpPJk5w-ZfGXNU5fgRW1fPAITaRWoZb4JR9bJwDm29zWafY1NXrkKy_zzDkttt-pCpLJGtIRBBuyndWleSK4f3b_j)



Practice for blockchain

<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<h1>JSCoing</h1>

	<script>
		/* JavaScript에서 객체를 정의하는 방법 */
		/* Case 1*/
		function User (name, age){
				this.name = name;
				this.age = age;
			
		}
		
		var user1 = new User("이십대", 20);
		var user2 = new User("삼십대", 30);
		var user3 = new User("사십대", 40);
		
		console.log(user1);
		console.log(user2);
		console.log(user3);
		
		/*Case 2*/
		class UserClass {
			constructor(name, age){
				this.name = name;
				this.age = age;
			}
		}
		
		var user10 = new UserClass ("이십대", 20);
		var user20 = new UserClass ("삼십대", 30);
		var user30 = new UserClass ("사십대", 40);
		
		console.log(user10);
		console.log(user20);
		console.log(user30);
		
		/* JavaScript 프로토타입 객체 */
		User.prototype.domain = "test.com";
		console.log(user1.domain);
		console.log(user2.domain);
		console.log(user3.domain);
		
		console.log(user10.domain); // undefined
		
		User.prototype.getEmail = function() {
			return this.name + "@" + this.domain;
			
		}
		console.log(user1.getEmail());
		console.log(user2.getEmail());
		console.log(user3.getEmail());		


​		
		/* 블록체인 객체 정의 */
		function Blockchain(){
			this. chain = [];
			this.pendingTransactions = [];
		}
		
		/* 블록체인 생성 함수 정의 */
		Blockchain.prototype.createNewBlock = function(previousBlockHash, nonce, hash){
			const newBlock = {
				index : this.chain.length + 1,
				timestamp : Date.now(),
				transaction : this.pendingTransactions,
				nonce :nonce,
				hash : hash,
				previousBlockHash : previousBlockHash
			};
			
			this.pendingTransactions = [];
			this.chain.push(newBlock);
			
			return newBlock;
		}


​			
​			
		const jscoin = new Blockchain();
		console.log(jscoin);
		// 새로운 블록을 생성
		jscoin.createNewBlock("0000", 100, "1111");
		jscoin.createNewBlock("1111", 200, "2222");
		jscoin.createNewBlock("2222", 300, "3333");
		console.log(jscoin);


​		
		/*마지막 블록을 반환하는 함수를 정의*/
		Blockchain.prototype.getLastBlock = function(){
			return this.chain[this.chain.length-1];
		
		}
		
		jscoin.createNewBlock("3333", 400, "4444");
		jscoin.createNewBlock("4444", 500, "5555");
		jscoin.createNewBlock("5555", 600, "6666");
		console.log(jscoin.getLastBlock());
		
		/* 트랜잭션을 생성하는 함수를 정의*/
		Blockchain.prototype.createNewTransaction = function(sender, recipient, amount){
			const newTransaction = {
					sender : sender,
					recipient : recipient, 
					amount : amount
			}
			this.pendingTransactions.push(newTransaction);
			
			return;
		}
		
		jscoin.createNewBlock("0000", 100, "1111");
		jscoin.createNewTransaction("aaa", "bbb", 1000);
		console.log(jscoin); // 대기 트랜잭션이 존재하는 것을 확인
		
		jscoin.createNewBlock("1111", 200, "2222");
		console.log(jscoin); // 대기 트랜잭션이 사라진 것을 확인


​		
		/*블록 해쉬값을 구하는 함수 정의 */
		const sha 256 = require('sha256');
		
		/* 블록 해쉬값을 구하는 함수 정의 */
		Blockchain.prototype.hashBlock = function(previousVlockHash, currentBlockData, nonce){
			const data = previousBlockHash + nonce.toString() + JSON.stringfy(currentBlockData);
			const hash = sha356(data);
			
			return hash;
			
		}
		
		const previousBlockHash = "previousBlockHash";
		const currentBlockData = [
	    	{ sender : "a", recipient : "b", amount : 100'},
	    	{ sender : "c", recipient : "d", amount : 200'},
	    	{ sender : "e", recipient : "f", amount : 300'},
	    ];
		const nonce = 100;
		
		const hashblock = jscoin.hashBlock (previousBlockHash, currentBlockData, nonce);
		console.log(hashblock);
		
	  /* 작업증명 코드를 추가*/
	  Blockchian.prototype.pow = function(previousBlockHash, currentBlockDate){
		  let nonce = 0;
		  let hash = this.hashBlock(preciousBlockHash, currentBlockDate, nonce);
		  while (hash, substring(0,4) ! = this.difficulty){
			  nonce ++;
			  hash = this.hashBlock(previousBlockHash, currentBlockData, nonce);
		  }
		  return nonce;
		  
		  // 테스트 코드
		  const previousBlockHash = "previous BlockHash";
		  const currentBlockData 
		  }
	  /*블록체인 객체 정의 */
	      function Blockchain() {
	    	  this.difficulty = "0000";//
	    	  this.chain = [];
	    	  this.pendingTransactions = [];
	    	  
	    	  //제너시스 블록을 생성
	    	  this.createNewblock(0,0,0);
	    	  
	    	  :
	 		const jscoin = new Blockchain();
	    	console.log(jscoin); //
	    	
	    	/* 난이를 체크하는 함수 */
	    	Blockchain.prototype.checkDifficulty = function(hash) {
	    		let head = hash.substring(0, this.difficulty);
	    		return (head.match(/0/g) || []).length == this.difficulty;
	    	}
	      }
	      
		</script>
			
			
	</body>
	</html>


</body>
</html>

