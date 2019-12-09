인증시도 횟수 제한

https://blog.naver.com/gs_info/221569634913

* Captcha: 자동화된 요청 방지 사용자와의 상호작용을 통한 처리
* reCCAPTCHA : 사람도 방지화에 어려움을 느껴서 본래 Captcha의 의미로 돌아가고자 만든 것
  * 커서의 움직임, 상황 파악 및 문제 풀이 같은 것으로 사람인지 아닌지 파악



##### 보상(채굴보상과 수수료 보상)

* 새로운 블록을 블록체인에 추가해 블록에 포함된 모든 거래를 유효한 거래로 확정시켜준 대가
* 비트코인에서의 보상은 새로운 발행되는 비트코인과 해당블록에 포함되는 거래의 거래 수수료의 합

##### 비트코인의 새로운 발행

* 채굴자가 블록을 처음 구성할 때 채굴자의 지갑으로 일정량의 비트코인이 입금되는 거래를 그 블록의 첫 거래
* 새로 발행되는 비트코인은 최초의 50BTC에서 시작해서 블록체인에 21만개의 블록이 추가될 때마다 절반으로 줄어듦



##### 트랜잭션 수수료

* 모든 트랜잭션은 수수료를 지불
* 트랜잭션 당사자끼리 자율적으로 정의



![img](https://lh5.googleusercontent.com/S2i8O3VnUkyZgFgnfGg1IlUzZsxjmjPKQD3FTLMZAHCrA6zuI7_Tk8fLSj2Tm66-oLNO1lfbhO_fevQPQ0f9BchxK3n8_2nxdwNTgjvuQVSC6C5qIVMY8ljsPMOEeYIHTy146256)



##### PoW

* 블록체인의 가장 기본적인 합의 알고리즘
* 거래승인 과정에 많은 컴퓨팅 파워가 필요한 어려운 작업을 수행
* 가장 긴 블록체인을 합의하고 다른 기록은 폐기
* 비트코인, 이더리움
* 장점:
  * 참가자의 수에 영향을 받지 않고 얼마든지 참가자를 늘릴 수 있다
* 단점:
  * 과도한 에너지 소비
  * 네트워크 불일치가 생길시 최종성이 불확실하게 됨
  * 채굴 독점



##### PoS (Proof of Stake)

* Quantum Mechanic에 의해 2011년 비트코인 논단 강의에서 처음 제기
* 대량 통화를 소유하고 있는 참가자는 그 통화가치를 지키기 위해 시스템의 신뢰성을 손실하지 않을 것을 전제
* 채굴시스템에서 사용자의 소유 지분이 블록 생성권의 지분율을 나타냄
* 포크가 발생했을 때 더 많은 자산을 보유한 체인 체택



#####  PBFT

* Private Blockchian에서 사용
* 최종성의 불확실성과 성능 문제를 해결
* 장애에 매우 강력한 내성을 가진 알고리즘
* 언제나 참가자 전원과 의사소통을 해야함
  * 참가자가 즐가하면 통신량이 증가하고 처리량이 처하



******합의 알고리즘 "PBFT / PoW / PoS 구분"**



실습. Kali1에서 Kali2 접속하기, host에서 Kali접속하기 등~

#### VirtualBox, 가상네트워크 설정하기 https://technote.kr/213



#### 정보보안 개론

##### 해킹과 보안의 역사

* 해킹이란, 데이터과 프로그램을 없애거나 망치는일(국내에서의 해킹 정의, More negative)
* 컴퓨터 조작을 즐기기, 무엇이나 숙고하지 않고 실행하기(해외에서의 해킹 정의, More poitive)



#### 보안의 3대 요소

* **기밀성(Confidentiality)**- 인가된 사용자만 정보 자산에 접근할 수 있는 것
* **무결성(Integrity)**- 적절한 권한을 가진 사용자에 의해 인가된 방법으로만 정보를 변경할 수 있도록 하는 것
* **가용성(Avilability)**- 정보자산에 대해 적절한 시간에 접근 가능한 것을 의미



##### 시스템 보안에 대한 이해

* 계정과 패스워드 관리 
* 세션관리
* 접근제어
* 권한 관리
* 로그 관리 - 로그 --> 감사추적 or 장애 분석
* 취약점 관리

SSO - Single Sign On 

Zero Trust - (Don't Trust, so I cannot give you anything)



##### 계정 관리

* 인증수단
  * ID / PW
  * 식별이란 아이디라는 문자열을 통해 그 자신이 누군지 확인하는 과정
  * 아이디만으로는 정확한 식별이 어려워 인증(Authentication)을 위한 다른 무언가(PW)를 요청
* 패스워드 보안의 4가지 인증방법
  * 알고 있는 것(something you know) eg. PW
  * 가지고 있는 것(something you have) eg. 출입카드
  * 스스로의 모습(something you are) eg. 지문인식
  * 위치하는 곳(somewhere you are) eg. 콜백



###### 운영체제의 계정관리

* Administrators
* Power Users
* Backup Operators
* Users
* Guests



계정 및 패스워드 관리

* 관리자 계정 관리 - Administrator계정은 administrator 그룹에서 삭제할 수 없지만, 계정 이름을 변경하거나 사용안함으로 설정 가능

계정 잠금 임계값 설정



##### 리눅스 계정과 권한 체계

* etc, passwd
  * 계정 목록을 저장하고 있는 파일
    * Root : x : 0 : 0 : root : /root : /bin/bash
      * 사용자 계정
      * 패스워드가 암호화되어 shadow 파일에 저장되어 있음
      * 사용자번호
      * 그룹번호
      * 사용자 이름
      * 사용자의 홈 디렉토리 (일반사용자는 /home디렉토리 하위에 위치)
      * 사용자의 쉘(shell)
* UID, GID
  * 관리자는 0으로 일반사용자는 그 외의 

(Sudo. 에 대한 개념 ?)

pw파일 vs shadow file로 저장하는 방법..?



root@kali:/etc# pwunconvroot@kali:/etc# cat /etc/passwd | grep rootroot:$6$xhM1CJI.$opnnLHSL4M5H/mAP8eBK1WJcH/xwHoUe636gK92o0fqlBXc3uIje2FMoDvN2dIqGMaJbociP/Xn8oHgl7MiGf/:0:0:root:/root:/bin/bash



root@kali:/etc# adduser user00 ⇐ user00 계정을 생성Adding user `user00' ...Adding new group `user00' (1000) ...Adding new user `user00' (1000) with group `user00' ...Creating home directory `/home/user00' ...Copying files from `/etc/skel' ...새 UNIX 암호 입력: user00새 UNIX 암호 재입력: user00passwd: 암호를 성공적으로 업데이트했습니다user00의 사용자의 정보를 바꿉니다새로운 값을 넣거나, 기본값을 원하시면 엔터를 치세요  이름 []:   방 번호 []:   직장 번화번호 []:   집 전화번호 []:   기타 []: Is the information correct? [Y/n] root@kali:/etc# cat /etc/passwd | grep user00user00:$6$xgJeJrpI$l8ODhW4S4dzrkLTlx0YYoW1VaShde65q4hUDaIPv1mQnSm5n.VQHtJGREvlxwnHSIHhtXzoUccsjcPj8SWUlo.:1000:1000:,,,:/home/user00:/bin/bash

root@kali:/etc# su - user00 ⇐ user00으로 전환user00@kali:~$ pwd ⇐ 현재 디렉터리 확인/home/user00user00@kali:~$ cat /etc/passwd | grep user00user00:$6$xgJeJrpI$l8ODhW4S4dzrkLTlx0YYoW1VaShde65q4hUDaIPv1mQnSm5n.VQHtJGREvlxwnHSIHhtXzoUccsjcPj8SWUlo.:1000:1000:,,,:/home/user00:/bin/bashuser00@kali:~$ cat /etc/passwd | grep rootroot:$6$xhM1CJI.$opnnLHSL4M5H/mAP8eBK1WJcH/xwHoUe636gK92o0fqlBXc3uIje2FMoDvN2dIqGMaJbociP/Xn8oHgl7MiGf/:0:0:root:/root:/bin/bash
⇒ /etc/passwd 파일을 모든 사용자가 읽을 수 있으므로 계정 정보가 노출될 가능성이 높다.