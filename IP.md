2019. 12. 10. 

모바일 관련 보안 가이드 https://www.kisa.or.kr/public/laws/laws3.jsp
안드로이드 권한 https://developer.android.com/guide/topics/security/permissions.html?hl=kohttps://developer.android.com/guide/topics/permissions/overview?hl=ko



##### 계정관리

* 시스템에 로그인할 필요가 없는 사용자는 쉘을 제거

  * etc/passwd파일에서 쉘이 정의된 부분을 수정하거나, usermod 명령어를 이용하여 쉘 정보를 변경
  * 웹 사용자 중 시스템에 로그인할 필요가 있는 사용자는 쉘이 부여된 별도의 계정을 사용

* 임의 생성된 관리자 계정의 존재 여부 확인

  관리자계정은 root가 아닌 다른 이름으로 바꿔서 사용하는 것을 권장

  * grep ":0:"  /etc/passwd



##### 패스워드 복잡도

​	크래킹되기 쉬운 패스워드

* 길이가 너무 짧거나 



##### 시스템 보안 관리

* 로그인 하지 않고 시스템 종료 방지



##### 네트워크

* 이더넷 어댑터 =  LAN 카드 = NIC(Network Interface Controller)

* Ethernet
  *  -> LAN 영역에서 사용하는 통신 기술 중 하나
  *  LAN 영역에서 사욧ㅇ하는 기술 중 사실상 표준 (De Facto Standard) 방식

* IPv4 주소

  총 32 비트 (0.0.0.0 ~ 255.255.255.255)로 구성된 주소 체계

  232개의 주소 표현이 가능



##### IP (Internet Protocol)

* 인터넷 공간에서 자기 pc가 사용하는 고유한 식별자를 의미

IP주소의 클래스 (등급) - IP 주소의 첫번째 자리 범위

A클래스 : 1 ~ 126 = 0000 0001 ~0111 1110

B클래스 : 128~191 = 1000 0000 ~ 1011 1111

C클래스 : 192~223 = 1100 0000 ~1101 1111



구글에서 제공하는 DNS 서버의 IP서버의 IP주소 = 8.8.8.8 -> A클래스

KT에서 제공하는 DNS서버의 IP주소 = 168.126.63.1 ->B클래스

127.0.0.1 ->어떤 클래스에도 속하지 않음 => 자기가 사용하는 LAN카드 자신을 의미 =루프백 주소(loopback address)



서브넷마스크(subnet mask)

IP주소를 서브넷 마스크를 이용해 표기하는 방식

IP주소를 네트워크 ID와 호스트 ID로 구분



IP                        Subnet Mask                 Network ID               Host ID

​                                                                 =국번                          =전화번호

10.10.10.10        255.0.0.0                       10                               10.10.10



게이트웨이(gateway)      =         라우터(router)    =>     각기 다른 네트워크 ID를 사용하는 LAN영역을 연결

​    SW측면을 강조                          HW측면 강조



LAN 영역

동일한 네트워크 ID를 고유하는 장치들의 집합

동일한 게이트웨이 주소를 사용하는 장치들의 집합



라우팅(Routing) -> 다른 네트워크 아이디를 사용하는 LAN영역을 연결

스위칭(Switching) -> LAN영역에서 MAC주소에 기반한 내부 통신

물리적 주소 =  MAC 주소

LAN카드에 부여된 주소로 LAN여역에서 내부 통신을 수행하기 위해 필요한 주소

24-F5-AA-EB-58-9B => 48비트 = OUI + 일련번호



DHCP (Dynamic Host Configuration Protocol) = 유동 IP환경

사용할 IP주소 범위를 서버에 미리 등록하면, PC사용자에게 IP주소, 서브넷 마스크, 게이트웨이 주소, DNS주소를 자동으로 할당해 주는 서비스

DNS(Domain Name System) 서버

도메인 이름과 IP주소의 대응 관계를 데이터베이스 형태로 저장하고 사용하는 서버

IP=32비트=네트워크 ID + 호스트 ID => IP주소 기반에 라이팅

MAC = 48비트 =OUI +일련번호 => MAC주소기반에 스위칭



ping : 출발지 호스트(내PC)와 목적지 호스트 (8.8.8.8) 사이에서 회선의 연경 상태나 목적지 운영체제의 동장 여부를 점검하기 위한 도구



K#2 192.168.248.130

K#1

192.168.248.129



nmap을 이용한 포트 스캐닝

 타켓 서버에 포트의 상태를 확인 

네트워크에 연결되어 있는 호스트의 정보를 파악하는 도구   

 . 네트워크에 연결되어 있는 호스트의 IP, OS

 . 서버의 열린 포트   

 . 서비스하는 소프트웨어 버전, … 

TCP Open Scan, 3-Way Handshaking 과정을 통해서 사용 중인 포트를 확인

정상 연결(SYN → SYN/ACK → ACK)의 마지막 ACK를 생략

포트가 열려있으면   : SYN → SYN/ACK → ACK 

포트가 열려있지 않으면 : SYN → RST/ACK

연결에 대한 로그가 남기 때문에 안전하지 않은 방법



stealth scan

3 way handshaking 과정을 거치지 않기 때문에 로그가 남지 않는다.

TCP half open scan     ⇒ -sS

FIN scan, XMAS scan, NULL scan 

FIN : FIN      ⇒ -sF

XMAX : FIN, PSH, URG ⇒ -sX

NULL :        ⇒ -sN

→ 포트가 열려 있으면 → 무응답

→ 포트가 닫혀 있으면 → RST/ACK