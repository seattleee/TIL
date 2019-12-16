**Levels of System**

static, CGI, Servlet, Java, JSP, MVC pattern(=model 2 Architecture)

5 Java EE, Interface(채워지지 않은 API가 제공된 것), Web container, (connectors between ) *플랫폼의 독립성!!!!! *Interface로  중소기업 및 다른 기업들이 창의적으로 API를 채워 서비스를 창간할 수 있도록 하는 것이 핵심

4 JDK JVM JRE(실행을 담당), API 

3 Web Server

2 OS

1 HW



*Engin, OS



자바코드

Class, MyServlet, extends H.S

() {} 기능 (=Method)



코드 프로세스 

요청을 분석하는 일 => **Biz** => 결과응답

Biz 재활용을 잘해야함



App Server (web logic, web sphere jeus = 금융권에서 사용하는 언어)

안정성 (transaction, security, Per?)

Model 1 Archi = JSP기반으로 Java 80%, Http 20%



Model Driven Development



root@server:~# gedit ~/.vimrc
root@server:~# vi text1.txt
root@server:~# vi test1.txt
root@server:~# vi test1.txt
root@server:~# ;;
bash: syntax error near unexpected token `;;'
root@server:~# ll
합계 120
drwx------ 18 root root 4096 12월 16 23:23 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 1327 12월 16 23:23 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 110 12월 16 23:23 test1.txt
-rw-r--r-- 1 root root  0 12월 16 23:19 text1.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 13 19:31 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# mv test1.txt Hello.java
root@server:~# ll
합계 120
drwx------ 18 root root 4096 12월 16 23:23 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 1327 12월 16 23:23 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 110 12월 16 23:23 Hello.java
-rw-r--r-- 1 root root  0 12월 16 23:19 text1.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 13 19:31 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# javac Hello.java
'javac' 프로그램은 다음 패키지에서 찾을 수 있습니다:
 \* default-jdk
 \* ecj
 \* gcj-5-jdk
 \* openjdk-8-jdk-headless
 \* gcj-4.8-jdk
 \* gcj-4.9-jdk
 \* openjdk-9-jdk-headless
다음을 실행해 보십시오: apt install <선택한 패키지>
root@server:~# ^C
root@server:~# ^C
root@server:~# apt install openjdk-8-jdk-headless
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다   
상태 정보를 읽는 중입니다... 완료
The following additional packages will be installed:
 ca-certificates-java java-common openjdk-8-jre-headless
제안하는 패키지:
 default-jre openjdk-8-demo openjdk-8-source fonts-dejavu-extra
 fonts-ipafont-gothic fonts-ipafont-mincho fonts-wqy-microhei
 fonts-wqy-zenhei fonts-indic
다음 새 패키지를 설치할 것입니다:
 ca-certificates-java java-common openjdk-8-jdk-headless
 openjdk-8-jre-headless
0개 업그레이드, 4개 새로 설치, 0개 제거 및 304개 업그레이드 안 함.
35.4 M바이트 아카이브를 받아야 합니다.
이 작업 후 139 M바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n] y
받기:1 http://us.archive.ubuntu.com/ubuntu xenial/main amd64 java-common all 0.56ubuntu2 [7,742 B]
받기:2 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 openjdk-8-jre-headless amd64 8u222-b10-1ubuntu1~16.04.1 [27.1 MB]
받기:3 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 ca-certificates-java all 20160321ubuntu1 [12.5 kB]
받기:4 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 openjdk-8-jdk-headless amd64 8u222-b10-1ubuntu1~16.04.1 [8,212 kB]
내려받기 35.4 M바이트, 소요시간 2분 0초 (293 k바이트/초)           
Selecting previously unselected package java-common.
(데이터베이스 읽는중 ...현재 180439개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../java-common_0.56ubuntu2_all.deb ...
Unpacking java-common (0.56ubuntu2) ...
Selecting previously unselected package openjdk-8-jre-headless:amd64.
Preparing to unpack .../openjdk-8-jre-headless_8u222-b10-1ubuntu1~16.04.1_amd64.deb ...
Unpacking openjdk-8-jre-headless:amd64 (8u222-b10-1ubuntu1~16.04.1) ...
Selecting previously unselected package ca-certificates-java.
Preparing to unpack .../ca-certificates-java_20160321ubuntu1_all.deb ...
Unpacking ca-certificates-java (20160321ubuntu1) ...
Selecting previously unselected package openjdk-8-jdk-headless:amd64.
Preparing to unpack .../openjdk-8-jdk-headless_8u222-b10-1ubuntu1~16.04.1_amd64.deb ...
Unpacking openjdk-8-jdk-headless:amd64 (8u222-b10-1ubuntu1~16.04.1) ...
Processing triggers for man-db (2.7.5-1) ...
Processing triggers for ca-certificates (20170717~16.04.2) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
java-common (0.56ubuntu2) 설정하는 중입니다 ...
ca-certificates-java (20160321ubuntu1) 설정하는 중입니다 ...
Adding debian:TÜBİTAK_UEKAE_Kök_Sertifika_Hizmet_Sağlayıcısı_-_Sürüm_3.pem
Adding debian:China_Internet_Network_Information_Center_EV_Certificates_Root.pem
Adding debian:Visa_eCommerce_Root.pem
Adding debian:GeoTrust_Universal_CA.pem
Adding debian:Network_Solutions_Certificate_Authority.pem
Adding debian:EE_Certification_Centre_Root_CA.pem
Adding debian:Deutsche_Telekom_Root_CA_2.pem
Adding debian:UTN_USERFirst_Hardware_Root_CA.pem
Adding debian:Starfield_Class_2_CA.pem
Adding debian:DigiCert_High_Assurance_EV_Root_CA.pem
Adding debian:TWCA_Root_Certification_Authority.pem
Adding debian:Certigna.pem
Adding debian:USERTrust_RSA_Certification_Authority.pem
Adding debian:Buypass_Class_3_Root_CA.pem
Adding debian:Izenpe.com.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G2.pem
Adding debian:QuoVadis_Root_CA_2.pem
Adding debian:Camerfirma_Global_Chambersign_Root.pem
Adding debian:GeoTrust_Universal_CA_2.pem
Adding debian:Go_Daddy_Root_Certificate_Authority_-_G2.pem
Adding debian:TURKTRUST_Certificate_Services_Provider_Root_2007.pem
Adding debian:XRamp_Global_CA_Root.pem
Adding debian:Trustis_FPS_Root_CA.pem
Adding debian:Amazon_Root_CA_3.pem
Adding debian:TUBITAK_Kamu_SM_SSL_Kok_Sertifikasi_-_Surum_1.pem
Adding debian:Sonera_Class_2_Root_CA.pem
Adding debian:GeoTrust_Global_CA.pem
Adding debian:GeoTrust_Primary_Certification_Authority.pem
Adding debian:DST_Root_CA_X3.pem
Adding debian:AC_RAIZ_FNMT-RCM.pem
Adding debian:Starfield_Services_Root_Certificate_Authority_-_G2.pem
Adding debian:OpenTrust_Root_CA_G2.pem
Adding debian:certSIGN_ROOT_CA.pem
Adding debian:Security_Communication_EV_RootCA1.pem
Adding debian:AddTrust_Public_Services_Root.pem
Adding debian:QuoVadis_Root_CA_2_G3.pem
Adding debian:GlobalSign_Root_CA_-_R3.pem
Adding debian:Certplus_Class_2_Primary_CA.pem
Adding debian:Actalis_Authentication_Root_CA.pem
Adding debian:Starfield_Root_Certificate_Authority_-_G2.pem
Adding debian:Camerfirma_Chambers_of_Commerce_Root.pem
Adding debian:Certum_Trusted_Network_CA.pem
Adding debian:IdenTrust_Public_Sector_Root_CA_1.pem
Adding debian:CA_Disig_Root_R1.pem
Adding debian:Go_Daddy_Class_2_CA.pem
Adding debian:COMODO_Certification_Authority.pem
Adding debian:TWCA_Global_Root_CA.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R4.pem
Adding debian:QuoVadis_Root_CA_3.pem
Adding debian:CNNIC_ROOT.pem
Adding debian:Security_Communication_RootCA2.pem
Adding debian:Entrust_Root_Certification_Authority.pem
Adding debian:DigiCert_Global_Root_G2.pem
Adding debian:Secure_Global_CA.pem
Adding debian:Certum_Root_CA.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2015.pem
Adding debian:GeoTrust_Global_CA_2.pem
Adding debian:Certum_Trusted_Network_CA_2.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_2009.pem
Adding debian:Certinomis_-_Autorité_Racine.pem
Adding debian:Hongkong_Post_Root_CA_1.pem
Adding debian:Staat_der_Nederlanden_Root_CA_-_G3.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G4.pem
Adding debian:Autoridad_de_Certificacion_Firmaprofesional_CIF_A62634068.pem
Adding debian:DigiCert_Assured_ID_Root_G2.pem
Adding debian:Entrust_Root_Certification_Authority_-_EC1.pem
Adding debian:AffirmTrust_Networking.pem
Adding debian:ePKI_Root_Certification_Authority.pem
Adding debian:PSCProcert.pem
Adding debian:thawte_Primary_Root_CA_-_G3.pem
Adding debian:thawte_Primary_Root_CA_-_G2.pem
Adding debian:Taiwan_GRCA.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_ECC_RootCA_2015.pem
Adding debian:SZAFIR_ROOT_CA2.pem
Adding debian:DigiCert_Assured_ID_Root_G3.pem
Adding debian:GlobalSign_Root_CA.pem
Adding debian:USERTrust_ECC_Certification_Authority.pem
Adding debian:Entrust_Root_Certification_Authority_-_G2.pem
Adding debian:thawte_Primary_Root_CA.pem
Adding debian:ssl-cert-snakeoil.pem
Adding debian:Swisscom_Root_EV_CA_2.pem
Adding debian:Buypass_Class_2_Root_CA.pem
Adding debian:DigiCert_Assured_ID_Root_CA.pem
Adding debian:Global_Chambersign_Root_-_2008.pem
Adding debian:T-TeleSec_GlobalRoot_Class_3.pem
Adding debian:ACEDICOM_Root.pem
Adding debian:DigiCert_Global_Root_CA.pem
Adding debian:ISRG_Root_X1.pem
Adding debian:Security_Communication_Root_CA.pem
Adding debian:COMODO_RSA_Certification_Authority.pem
Adding debian:SecureTrust_CA.pem
Adding debian:OISTE_WISeKey_Global_Root_GA_CA.pem
Adding debian:E-Tugra_Certification_Authority.pem
Adding debian:D-TRUST_Root_Class_3_CA_2_EV_2009.pem
Adding debian:Baltimore_CyberTrust_Root.pem
Adding debian:Swisscom_Root_CA_2.pem
Adding debian:TÜRKTRUST_Elektronik_Sertifika_Hizmet_Sağlayıcısı_H5.pem
Adding debian:LuxTrust_Global_Root_2.pem
Adding debian:GlobalSign_Root_CA_-_R2.pem
Adding debian:Certplus_Root_CA_G2.pem
Adding debian:GlobalSign_ECC_Root_CA_-_R5.pem
Adding debian:Amazon_Root_CA_4.pem
Adding debian:AddTrust_External_Root.pem
Adding debian:QuoVadis_Root_CA_3_G3.pem
Adding debian:ACCVRAIZ1.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G3.pem
Adding debian:QuoVadis_Root_CA_1_G3.pem
Adding debian:GeoTrust_Primary_Certification_Authority_-_G2.pem
Adding debian:AffirmTrust_Premium_ECC.pem
Adding debian:Staat_der_Nederlanden_EV_Root_CA.pem
Adding debian:CFCA_EV_ROOT.pem
Adding debian:OpenTrust_Root_CA_G3.pem
Adding debian:DigiCert_Trusted_Root_G4.pem
Adding debian:Amazon_Root_CA_2.pem
Adding debian:VeriSign_Universal_Root_Certification_Authority.pem
Adding debian:Comodo_Secure_Services_root.pem
Adding debian:IdenTrust_Commercial_Root_CA_1.pem
Adding debian:Cybertrust_Global_Root.pem
Adding debian:CA_Disig_Root_R2.pem
Adding debian:Verisign_Class_3_Public_Primary_Certification_Authority_-_G3.pem
Adding debian:AddTrust_Qualified_Certificates_Root.pem
Adding debian:Comodo_AAA_Services_root.pem
Adding debian:OISTE_WISeKey_Global_Root_GB_CA.pem
Adding debian:NetLock_Arany_=Class_Gold=_Főtanúsítvány.pem
Adding debian:Microsec_e-Szigno_Root_CA_2009.pem
Adding debian:SwissSign_Gold_CA_-_G2.pem
Adding debian:Swisscom_Root_CA_1.pem
Adding debian:Amazon_Root_CA_1.pem
Adding debian:Atos_TrustedRoot_2011.pem
Adding debian:TeliaSonera_Root_CA_v1.pem
Adding debian:VeriSign_Class_3_Public_Primary_Certification_Authority_-_G5.pem
Adding debian:AffirmTrust_Commercial.pem
Adding debian:COMODO_ECC_Certification_Authority.pem
Adding debian:QuoVadis_Root_CA.pem
Adding debian:Entrust.net_Premium_2048_Secure_Server_CA.pem
Adding debian:OpenTrust_Root_CA_G1.pem
Adding debian:DigiCert_Global_Root_G3.pem
Adding debian:AddTrust_Low-Value_Services_Root.pem
Adding debian:AffirmTrust_Premium.pem
Adding debian:Chambers_of_Commerce_Root_-_2008.pem
Adding debian:Hellenic_Academic_and_Research_Institutions_RootCA_2011.pem
Adding debian:DST_ACES_CA_X6.pem
Adding debian:SwissSign_Silver_CA_-_G2.pem
Adding debian:Comodo_Trusted_Services_root.pem
Adding debian:SecureSign_RootCA11.pem
Adding debian:Certinomis_-_Root_CA.pem
Adding debian:T-TeleSec_GlobalRoot_Class_2.pem
Adding debian:Certplus_Root_CA_G1.pem
Adding debian:EC-ACC.pem
done.
openjdk-8-jre-headless:amd64 (8u222-b10-1ubuntu1~16.04.1) 설정하는 중입니다 ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmid to provide /usr/bin/rmid (rmid) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/hsdb to provide /usr/bin/hsdb (hsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java to provide /usr/bin/java (java) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/clhsdb to provide /usr/bin/clhsdb (clhsdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/keytool to provide /usr/bin/keytool (keytool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/jjs to provide /usr/bin/jjs (jjs) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/pack200 to provide /usr/bin/pack200 (pack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/rmiregistry to provide /usr/bin/rmiregistry (rmiregistry) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/unpack200 to provide /usr/bin/unpack200 (unpack200) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/orbd to provide /usr/bin/orbd (orbd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/servertool to provide /usr/bin/servertool (servertool) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/tnameserv to provide /usr/bin/tnameserv (tnameserv) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/jexec to provide /usr/bin/jexec (jexec) in auto mode
openjdk-8-jdk-headless:amd64 (8u222-b10-1ubuntu1~16.04.1) 설정하는 중입니다 ...
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/idlj to provide /usr/bin/idlj (idlj) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdeps to provide /usr/bin/jdeps (jdeps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsimport to provide /usr/bin/wsimport (wsimport) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jinfo to provide /usr/bin/jinfo (jinfo) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jsadebugd to provide /usr/bin/jsadebugd (jsadebugd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/native2ascii to provide /usr/bin/native2ascii (native2ascii) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstat to provide /usr/bin/jstat (jstat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javadoc to provide /usr/bin/javadoc (javadoc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javah to provide /usr/bin/javah (javah) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstack to provide /usr/bin/jstack (jstack) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jrunscript to provide /usr/bin/jrunscript (jrunscript) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javac to provide /usr/bin/javac (javac) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jhat to provide /usr/bin/jhat (jhat) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/javap to provide /usr/bin/javap (javap) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jar to provide /usr/bin/jar (jar) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/extcheck to provide /usr/bin/extcheck (extcheck) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/schemagen to provide /usr/bin/schemagen (schemagen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jps to provide /usr/bin/jps (jps) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/xjc to provide /usr/bin/xjc (xjc) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/rmic to provide /usr/bin/rmic (rmic) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jstatd to provide /usr/bin/jstatd (jstatd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jdb to provide /usr/bin/jdb (jdb) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/serialver to provide /usr/bin/serialver (serialver) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/wsgen to provide /usr/bin/wsgen (wsgen) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jcmd to provide /usr/bin/jcmd (jcmd) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jarsigner to provide /usr/bin/jarsigner (jarsigner) in auto mode
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/bin/jmap to provide /usr/bin/jmap (jmap) in auto mode
Processing triggers for ca-certificates (20170717~16.04.2) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...

done.
done.
root@server:~# javac Hello.java
root@server:~# java Hello
오류: 기본 클래스 Hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java Hello
오류: 기본 클래스 Hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# ll
합계 124
drwx------ 18 root root 4096 12월 16 23:40 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 1327 12월 16 23:23 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 110 12월 16 23:23 Hello.java
-rw-r--r-- 1 root root 416 12월 16 23:40 hello.class
-rw-r--r-- 1 root root  0 12월 16 23:19 text1.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:26 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# vi Hello.java
root@server:~# java Hello
오류: 기본 클래스 Hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# vi Hello.java
root@server:~# javac Hello.java
root@server:~# java Hello
Hello Java~!
root@server:~# vi hello.class
root@server:~# java Hello
Hello Java~!
root@server:~# gedit hello.java
root@server:~# java hello
Hello Java~!
root@server:~# edit hello
Unescaped left brace in regex is deprecated, passed through in regex; marked by <-- HERE in m/%{ <-- HERE (.*?)}/ at /usr/bin/edit line 528.
Error: no "edit" mailcap rules found for type "cannot open `hello' (No such file or directory)"
root@server:~# vi hello.java
root@server:~# vi hello.java
root@server:~# javac hello.java
hello.java:10: error: reached end of file while parsing
}
 ^
1 error
root@server:~# vi hello.java
root@server:~# javac hello.java
hello.java:1: error: package java.aet does not exist
import java.aet.*;
^
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
    ^
 symbol:  class frame
 location: class Hello
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
          ^
 symbol:  class Frame
 location: class Hello
hello.java:5: error: cannot find symbol
  TextArea ta=new TextArea();
  ^
 symbol:  class TextArea
 location: class Hello
hello.java:5: error: cannot find symbol
  TextArea ta=new TextArea();
          ^
 symbol:  class TextArea
 location: class Hello
hello.java:9: error: package system does not exist
  system.out.println("Hello Java~!");
     ^
6 errors
root@server:~# vi hello.java
root@server:~# javac hello.java
hello.java:1: error: package java.aet does not exist
import java.aet.*;
^
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
    ^
 symbol:  class frame
 location: class Hello
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
          ^
 symbol:  class Frame
 location: class Hello
hello.java:5: error: cannot find symbol
  TextArea ta=new TextArea();
  ^
 symbol:  class TextArea
 location: class Hello
hello.java:5: error: cannot find symbol
  TextArea ta=new TextArea();
          ^
 symbol:  class TextArea
 location: class Hello
5 errors
root@server:~# vi hello.java
root@server:~# javac hello.java
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
    ^
 symbol:  class frame
 location: class Hello
1 error
root@server:~# vi hello.java
root@server:~# javac hello.java
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
    ^
 symbol:  class frame
 location: class Hello
1 error
root@server:~# javac hello.java
hello.java:4: error: cannot find symbol
    frame f=new Frame("나의 메모장");
    ^
 symbol:  class frame
 location: class Hello
1 error
root@server:~# vi hello.java
root@server:~# javac hello.java
root@server:~# ll
합계 132
drwx------ 18 root root 4096 12월 16 23:52 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3366 12월 16 23:52 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 674 12월 16 23:52 Hello.class
-rw-r--r-- 1 root root 110 12월 16 23:41 Hello.java
-rw-r--r-- 1 root root 416 12월 16 23:40 hello.class
-rw-r--r-- 1 root root 248 12월 16 23:52 hello.java
-rw-r--r-- 1 root root  0 12월 16 23:19 text1.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:26 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# rm Hello.class
root@server:~# rm Hello.java
root@server:~# rm text1.txt
root@server:~# java Hello
오류: 기본 클래스 Hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java hello
Hello Java~!
root@server:~# vi hello.java
root@server:~# java hello
Hello Java~!
root@server:~# rm hello
rm: 'hello'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# rm hello.class
root@server:~# javac hello.java
root@server:~# java hello
오류: 기본 클래스 hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java Hello
Hello Java~!
^Croot@server:~# ^C
root@server:~# ^C
root@server:~# ^C
root@server:~# ^C
root@server:~# man vi
root@server:~# man javac
root@server:~# man java
root@server:~# man apt
root@server:~# man apt-get
root@server:~# ls
Hello.class 공개   문서   비디오 음악
hello.java  다운로드 바탕화면 사진  템플릿
root@server:~# ls -a
.       .bashrc .gnupg  .profile       Hello.class 바탕화면
..       .cache  .java   .viminfo       hello.java  비디오
.ICEauthority .config .local  .vimrc        공개     사진
.Xauthority  .dbus  .mozilla .xsession-errors   다운로드   음악
.bash_history .gconf  .presage .xsession-errors.old 문서     템플릿
root@server:~# ls -l
합계 40
-rw-r--r-- 1 root root 674 12월 16 23:53 Hello.class
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# ls -al
합계 128
drwx------ 19 root root 4096 12월 16 23:54 .
drwxr-xr-x 24 root root 4096 12월 13 19:18 ..
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config
drwx------ 3 root root 4096 12월 13 19:29 .dbus
drwx------ 2 root root 4096 12월 13 19:33 .gconf
drwx------ 3 root root 4096 12월 16 23:04 .gnupg
drwxr-xr-x 3 root root 4096 12월 16 23:54 .java
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local
drwx------ 5 root root 4096 12월 13 20:28 .mozilla
drwx------ 2 root root 4096 12월 13 19:31 .presage
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3374 12월 16 23:53 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 674 12월 16 23:53 Hello.class
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# ll
합계 128
drwx------ 19 root root 4096 12월 16 23:54 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 16 23:54 .java/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3374 12월 16 23:53 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 674 12월 16 23:53 Hello.class
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# rm Hello.class
root@server:~# ll
합계 124
drwx------ 19 root root 4096 12월 17 00:12 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 16 23:54 .java/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3374 12월 16 23:53 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# cp Hello.java2
cp: 'Hello.java2' 다음에 대상 파일 명령이 누락됨
Try 'cp --help' for more information.
root@server:~# cp hello.java2
cp: 'hello.java2' 다음에 대상 파일 명령이 누락됨
Try 'cp --help' for more information.
root@server:~# cp hello.java2
cp: 'hello.java2' 다음에 대상 파일 명령이 누락됨
Try 'cp --help' for more information.
root@server:~# touch abc.txt
root@server:~# ll
합계 124
drwx------ 19 root root 4096 12월 17 00:14 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 16 23:54 .java/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3374 12월 16 23:53 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root  0 12월 17 00:14 abc.txt
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# mv abc.txt abc/
mv: 'abc.txt'를 'abc/'로 옮길 수 없음: 디렉터리가 아닙니다
root@server:~# mv abc.txt abc/
mv: 'abc.txt'를 'abc/'로 옮길 수 없음: 디렉터리가 아닙니다
root@server:~# ls
abc.txt hello.java 공개 다운로드 문서 바탕화면 비디오 사진 음악 템플릿
root@server:~# ls abc
ls: 'abc'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# ls abc/
ls: 'abc/'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~#
root@server:~# cd
root@server:~# rm abc/abc/txt
rm: 'abc/abc/txt'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# ls abc/
ls: 'abc/'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# mv hello.java2 abc/
mv: 'hello.java2'를 설명할 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# ls abc/
ls: 'abc/'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# rm abc/
rm: 'abc/'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# rmdir abc
rmdir: failed to remove 'abc': 그런 파일이나 디렉터리가 없습니다
root@server:~# rm -rf
root@server:~# rm -rf abc
root@server:~# ll
합계 124
drwx------ 19 root root 4096 12월 17 00:14 ./
drwxr-xr-x 24 root root 4096 12월 13 19:18 ../
-rw------- 1 root root 2226 12월 16 23:04 .ICEauthority
-rw------- 1 root root  51 12월 16 23:04 .Xauthority
-rw------- 1 root root 1028 12월 16 23:18 .bash_history
-rw-r--r-- 1 root root 3106 10월 23 2015 .bashrc
drwx------ 12 root root 4096 12월 16 22:27 .cache/
drwxr-xr-x 15 root root 4096 12월 13 19:31 .config/
drwx------ 3 root root 4096 12월 13 19:29 .dbus/
drwx------ 2 root root 4096 12월 13 19:33 .gconf/
drwx------ 3 root root 4096 12월 16 23:04 .gnupg/
drwxr-xr-x 3 root root 4096 12월 16 23:54 .java/
drwxr-xr-x 3 root root 4096 12월 13 19:29 .local/
drwx------ 5 root root 4096 12월 13 20:28 .mozilla/
drwx------ 2 root root 4096 12월 13 19:31 .presage/
-rw-r--r-- 1 root root 148 12월 13 19:30 .profile
-rw------- 1 root root 3374 12월 16 23:53 .viminfo
-rw-r--r-- 1 root root 1246 12월 16 23:18 .vimrc
-rw------- 1 root root 6525 12월 16 23:04 .xsession-errors
-rw------- 1 root root 7692 12월 16 23:04 .xsession-errors.old
-rw-r--r-- 1 root root  0 12월 17 00:14 abc.txt
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개/
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드/
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서/
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면/
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오/
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진/
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악/
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿/
root@server:~# cat hello.java
import java.awt.*;
class Hello{
  public static void main(String [] args){
    Frame f=new Frame("나의 메모장");
  TextArea ta=new TextArea();
  f.add(ta);
  f.setSize(500,400);
  f.setVisible(true);
  System.out.println("Hello Java~!");
}
}

root@server:~# head -3 hello.java
import java.awt.*;
class Hello{
  public static void main(String [] args){
root@server:~# tail -2 hello.java
}

root@server:~# more +5 hello.java
  TextArea ta=new TextArea();
  f.add(ta);
  f.setSize(500,400);
  f.setVisible(true);
  System.out.println("Hello Java~!");
}
}

root@server:~# file hello.java
hello.java: C++ source, UTF-8 Unicode text
root@server:~# gedit /etc/passwd
root@server:~# gedit /etc/shadow
root@server:~# gedit /etc/passwd
root@server:~# pwd
/root
root@server:~# gedit /etc/passwd
gedit /etc/group

root@server:~# gedit /etc/group
root@server:~#
root@server:~# adduser user1
'user1' 사용자를 추가 중...
새 그룹 'user1' (1001) 추가 ...
새 사용자 'user1' (1001) 을(를) 그룹 'user1' (으)로 추가 ...
'/home/user1' 홈 디렉터리를 생성하는 중...
'/etc/skel'에서 파일들을 복사하는 중...
새 UNIX 암호 입력:
새 UNIX 암호 재입력:
passwd: 암호를 성공적으로 업데이트했습니다
user1의 사용자의 정보를 바꿉니다
새로운 값을 넣거나, 기본값을 원하시면 엔터를 치세요
  이름 []:
  방 번호 []:
  직장 전화번호 []:
  집 전화번호 []:
  기타 []:
정보가 올바릅니까? [Y/n]
root@server:~# tail /etc/passwd
colord:x:113:123:colord colour management daemon,,,:/var/lib/colord:/bin/false
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/var/run/speech-dispatcher:/bin/false
hplip:x:115:7:HPLIP system user,,,:/var/run/hplip:/bin/false
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/bin/false
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
ubuntu:x:1000:1000:ubuntu,,,:/home/ubuntu:/bin/bash
user1:x:1001:1001:,,,:/home/user1:/bin/bash
root@server:~# tail /etc/group
bluetooth:x:121:
scanner:x:122:saned
colord:x:123:
pulse:x:124:
pulse-access:x:125:
rtkit:x:126:
saned:x:127:
ubuntu:x:1000:
sambashare:x:128:ubuntu
user1:x:1001:
root@server:~# userdel -r user1
userdel: user1 mail spool (/var/mail/user1) not found
root@server:~# groupadd ubuntuGroup
root@server:~# tail -5 /etc/passwd
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
ubuntu:x:1000:1000:ubuntu,,,:/home/ubuntu:/bin/bash
root@server:~# tail -5 /etx/group
tail: 읽기를 위해 '/etx/group'을(를) 열 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# tail -5 /etc/group
rtkit:x:126:
saned:x:127:
ubuntu:x:1000:
sambashare:x:128:ubuntu
ubuntuGroup:x:1001:
root@server:~# adduser --gid 1001 user2
'user2' 사용자를 추가 중...
새 사용자 'user2' (1001) 을(를) 그룹 'ubuntuGroup' (으)로 추가 ...
'/home/user2' 홈 디렉터리를 생성하는 중...
'/etc/skel'에서 파일들을 복사하는 중...
새 UNIX 암호 입력:
새 UNIX 암호 재입력:
암호가 없음
새 UNIX 암호 입력:
새 UNIX 암호 재입력:
암호가 없음
새 UNIX 암호 입력:
새 UNIX 암호 재입력:
암호가 없음
암호: 인증 토근 수정 오류
passwd: 암호를 바꿨습니다
다시 할까요? [y/N]
user2의 사용자의 정보를 바꿉니다
새로운 값을 넣거나, 기본값을 원하시면 엔터를 치세요
  이름 []:
  방 번호 []:
  직장 전화번호 []:
  집 전화번호 []:
  기타 []:
정보가 올바릅니까? [Y/n]
root@server:~# tail -5 /etc/passwd
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
ubuntu:x:1000:1000:ubuntu,,,:/home/ubuntu:/bin/bash
user2:x:1001:1001:,,,:/home/user2:/bin/bash
root@server:~# tail -5 etc/shadow
tail: 읽기를 위해 'etc/shadow'을(를) 열 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# tail -5 /etc/passwd
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
ubuntu:x:1000:1000:ubuntu,,,:/home/ubuntu:/bin/bash
user2:x:1001:1001:,,,:/home/user2:/bin/bash
root@server:~# tail -5 /etc/shadow
rtkit:*:17954:0:99999:7:::
saned:*:17954:0:99999:7:::
usbmux:*:17954:0:99999:7:::
ubuntu:$6$T94FZYfH$4vvhKHL6CTUqQjSg.bIGcmaqOEr7CYclvgXUsNZ.aRu0hUm12AXvjmukGxeyLNBvbKS5UnRTkB4II0JUWsCWi/:18243:0:99999:7:::
user2:!:18246:0:99999:7:::
root@server:~# ls -a /home/user1
ls: '/home/user1'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# ls -a /home/user2
. .. .bash_logout .bashrc .profile examples.desktop
root@server:~# ls -a /etx/skel
ls: '/etx/skel'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# ls -a /etc/skel
. .. .bash_logout .bashrc .profile examples.desktop
root@server:~# touch sample.txt
root@server:~# ls -l
합계 36
-rw-r--r-- 1 root root  0 12월 17 00:14 abc.txt
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rw-r--r-- 1 root root  0 12월 17 00:52 sample.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# chmod 777 sample.txt
root@server:~# ls -l
합계 36
-rw-r--r-- 1 root root  0 12월 17 00:14 abc.txt
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rwxrwxrwx 1 root root  0 12월 17 00:52 sample.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# rm abc
rm: 'abc'를 지울 수 없음: 그런 파일이나 디렉터리가 없습니다
root@server:~# rm abc.txt
root@server:~# ls
hello.java 공개   문서   비디오 음악
sample.txt 다운로드 바탕화면 사진  템플릿
root@server:~# ls -l
합계 36
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rwxrwxrwx 1 root root  0 12월 17 00:52 sample.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# javac Hello.java
javac: file not found: Hello.java
Usage: javac <options> <source files>
use -help for a list of possible options
root@server:~# ls -l
합계 36
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rwxrwxrwx 1 root root  0 12월 17 00:52 sample.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# java hello
오류: 기본 클래스 hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java hello
오류: 기본 클래스 hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java Hello
오류: 기본 클래스 Hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# java hello.txt
오류: 기본 클래스 hello.txt을(를) 찾거나 로드할 수 없습니다.
root@server:~# java hello
오류: 기본 클래스 hello을(를) 찾거나 로드할 수 없습니다.
root@server:~# ls -l
합계 36
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rwxrwxrwx 1 root root  0 12월 17 00:52 sample.txt
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# vi test.txt
root@server:~# gedit test
root@server:~# ls -l test
-rw-r--r-- 1 root root 21 12월 17 01:01 test
root@server:~# whoami
root
root@server:~# ./test
bash: ./test: 허가 거부
root@server:~# chmod 755 test
root@server:~# ls -l
합계 40
-rw-r--r-- 1 root root 248 12월 16 23:53 hello.java
-rwxrwxrwx 1 root root  0 12월 17 00:52 sample.txt
-rwxr-xr-x 1 root root  21 12월 17 01:01 test
drwxr-xr-x 2 root root 4096 12월 13 19:31 공개
drwxr-xr-x 2 root root 4096 12월 13 19:31 다운로드
drwxr-xr-x 2 root root 4096 12월 13 19:31 문서
drwxr-xr-x 2 root root 4096 12월 16 23:56 바탕화면
drwxr-xr-x 2 root root 4096 12월 13 19:31 비디오
drwxr-xr-x 2 root root 4096 12월 13 19:31 사진
drwxr-xr-x 2 root root 4096 12월 13 19:31 음악
drwxr-xr-x 2 root root 4096 12월 13 19:31 템플릿
root@server:~# edit hello.class
Unescaped left brace in regex is deprecated, passed through in regex; marked by <-- HERE in m/%{ <-- HERE (.*?)}/ at /usr/bin/edit line 528.
Error: no "edit" mailcap rules found for type "application/java-vm"
root@server:~# chown ubuntu test
root@server:~# ls -l test
-rwxr-xr-x 1 ubuntu root 21 12월 17 01:01 test
root@server:~# chgrp ubuntu test
root@server:~# ls -l test
-rwxr-xr-x 1 ubuntu ubuntu 21 12월 17 01:01 test
root@server:~# chown ubuntu.ubuntu test
root@server:~# ./test
./test: 줄 1: 안녕: 명령어를 찾을 수 없음
root@server:~# ./test
./test: 줄 1: 안녕: 명령어를 찾을 수 없음
root@server:~# ./test
./test: 줄 1: 안녕: 명령어를 찾을 수 없음
root@server:~# su - ubuntu
ubuntu@server:~$ pwd
/home/ubuntu
ubuntu@server:~$ ll
합계 112
drwxr-xr-x 17 ubuntu ubuntu 4096 12월 13 19:31 ./
drwxr-xr-x 4 root  root  4096 12월 17 00:36 ../
-rw------- 1 ubuntu ubuntu 318 12월 13 19:23 .ICEauthority
-rw------- 1 ubuntu ubuntu  51 12월 13 19:23 .Xauthority
-rw------- 1 ubuntu ubuntu  15 12월 13 19:31 .bash_history
-rw-r--r-- 1 ubuntu ubuntu 220 12월 13 19:13 .bash_logout
-rw-r--r-- 1 ubuntu ubuntu 3771 12월 13 19:13 .bashrc
drwx------ 10 ubuntu ubuntu 4096 12월 16 22:14 .cache/
drwx------ 16 ubuntu ubuntu 4096 12월 13 19:24 .config/
drwx------ 3 ubuntu ubuntu 4096 12월 13 19:23 .dbus/
-rw-r--r-- 1 ubuntu ubuntu  25 12월 13 19:23 .dmrc
drwx------ 2 ubuntu ubuntu 4096 12월 13 19:26 .gconf/
drwx------ 3 ubuntu ubuntu 4096 12월 13 19:23 .gnupg/
drwx------ 3 ubuntu ubuntu 4096 12월 13 19:23 .local/
drwx------ 2 ubuntu ubuntu 4096 12월 13 19:23 .presage/
-rw-r--r-- 1 ubuntu ubuntu 655 12월 13 19:13 .profile
-rw-r--r-- 1 root  root   0 12월 13 19:19 .sudo_as_admin_successful
-rw------- 1 ubuntu ubuntu 1182 12월 13 19:31 .xsession-errors
-rw-r--r-- 1 ubuntu ubuntu 8980 12월 13 19:13 examples.desktop
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 공개/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 다운로드/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 문서/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 바탕화면/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 비디오/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 사진/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 음악/
drwxr-xr-x 2 ubuntu ubuntu 4096 12월 13 19:23 템플릿/
ubuntu@server:~$ ls -l /root/test
ls: '/root/test'에 접근할 수 없습니다: 허가 거부
ubuntu@server:~$ ls -l /
합계 100
drwxr-xr-x  2 root root 4096 12월 13 19:19 bin
drwxr-xr-x  3 root root 4096 12월 13 19:19 boot
drwxr-xr-x  2 root root 4096 12월 13 19:11 cdrom
drwxr-xr-x 17 root root 3880 12월 16 23:04 dev
drwxr-xr-x 132 root root 12288 12월 17 00:36 etc
drwxr-xr-x  4 root root 4096 12월 17 00:36 home
lrwxrwxrwx  1 root root  33 12월 13 19:18 initrd.img -> boot/initrd.img-4.15.0-45-generic
lrwxrwxrwx  1 root root  33 12월 13 18:52 initrd.img.old -> boot/initrd.img-4.15.0-45-generic
drwxr-xr-x 22 root root 4096 12월 13 19:19 lib
drwxr-xr-x  2 root root 4096 2월 27 2019 lib64
drwx------  2 root root 16384 12월 13 18:52 lost+found
drwxr-xr-x  3 root root 4096 12월 13 20:13 media
drwxr-xr-x  2 root root 4096 2월 27 2019 mnt
drwxr-xr-x  2 root root 4096 2월 27 2019 opt
dr-xr-xr-x 233 root root   0 12월 16 23:04 proc
drwx------ 19 root root 4096 12월 17 01:03 root
drwxr-xr-x 24 root root  760 12월 17 00:25 run
drwxr-xr-x  2 root root 12288 12월 13 19:19 sbin
drwxr-xr-x  2 root root 4096 12월 13 19:22 snap
drwxr-xr-x  2 root root 4096 2월 27 2019 srv
dr-xr-xr-x 13 root root   0 12월 16 23:04 sys
drwxrwxrwt 13 root root 4096 12월 17 00:17 tmp
drwxr-xr-x 11 root root 4096 2월 27 2019 usr
drwxr-xr-x 14 root root 4096 2월 27 2019 var
lrwxrwxrwx  1 root root  30 12월 13 19:18 vmlinuz -> boot/vmlinuz-4.15.0-45-generic
ubuntu@server:~$ excit
excit: 명령을 찾을 수 없습니다
ubuntu@server:~$ exit
로그아웃
root@server:~# mv test ~ubuntu
root@server:~# ls -l test
ls: 'test'에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
root@server:~# su - ubuntu
ubuntu@server:~$ ls -l test
-rwxr-xr-x 1 ubuntu ubuntu 21 12월 17 01:01 test
ubuntu@server:~$ chmod 777 test
ubuntu@server:~$ ls -l test
-rwxrwxrwx 1 ubuntu ubuntu 21 12월 17 01:01 test
ubuntu@server:~$ ./test
./test: 줄 1: 안녕: 명령어를 찾을 수 없음
ubuntu@server:~$ chown root.root test
chown: 'test'의 소유자 변경: 명령을 허용하지 않음
ubuntu@server:~$ chown exit
chown: `exit' 뒤에 명령어가 빠짐
Try 'chown --help' for more information.
ubuntu@server:~$ exit
로그아웃
root@server:~# man dpkg
root@server:~# dpkg -l zip
희망상태=알수없음(U)/설치(I)/지우기(R)/깨끗이(P)/고정(H)
| 상태=아님(N)/설치(I)/설정(C)/풀림(U)/절반설정(F)/일부설치(H)/트리거대기(W)/
| /  트리거밀림(T)
|/ 오류?=(없음)/다시설치필요(R) (상태, 오류가 대문자=불량)
||/ 이름      버전     Architecture 설명
+++-==============-============-============-=================================
ii zip      3.0-11    amd64    Archiver for .zip files
root@server:~# dpkg -i galculator
dpkg: error processing archive galculator (--install):
 아카이브에 접근할 수 없습니다: 그런 파일이나 디렉터리가 없습니다
처리하는데 오류가 발생했습니다:
 galculator
root@server:~# apt install galculator
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다   
상태 정보를 읽는 중입니다... 완료
다음 새 패키지를 설치할 것입니다:
 galculator
0개 업그레이드, 1개 새로 설치, 0개 제거 및 304개 업그레이드 안 함.
159 k바이트 아카이브를 받아야 합니다.
이 작업 후 1,495 k바이트의 디스크 공간을 더 사용하게 됩니다.
받기:1 http://us.archive.ubuntu.com/ubuntu xenial/universe amd64 galculator amd64 2.1.4-1 [159 kB]
내려받기 159 k바이트, 소요시간 1초 (105 k바이트/초)
Selecting previously unselected package galculator.
(데이터베이스 읽는중 ...현재 180797개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../galculator_2.1.4-1_amd64.deb ...
Unpacking galculator (2.1.4-1) ...
Processing triggers for hicolor-icon-theme (0.15-0ubuntu1.1) ...
Processing triggers for man-db (2.7.5-1) ...
Processing triggers for gnome-menus (3.13.3-6ubuntu3.1) ...
Processing triggers for desktop-file-utils (0.22-1ubuntu5.2) ...
Processing triggers for bamfdaemon (0.5.3~bzr0+16.04.20180209-0ubuntu1) ...
Rebuilding /usr/share/applications/bamf-2.index...
Processing triggers for mime-support (3.59ubuntu1) ...
galculator (2.1.4-1) 설정하는 중입니다 ...
root@server:~# dpkg -l mysql-client
dpkg-query: no packages found matching mysql-client
root@server:~# apt-get install mysql-client
패키지 목록을 읽는 중입니다... 완료
의존성 트리를 만드는 중입니다   
상태 정보를 읽는 중입니다... 완료
The following additional packages will be installed:
 libaio1 mysql-client-5.7 mysql-client-core-5.7 mysql-common
다음 새 패키지를 설치할 것입니다:
 libaio1 mysql-client mysql-client-5.7 mysql-client-core-5.7 mysql-common
0개 업그레이드, 5개 새로 설치, 0개 제거 및 304개 업그레이드 안 함.
8,082 k바이트 아카이브를 받아야 합니다.
이 작업 후 62.2 M바이트의 디스크 공간을 더 사용하게 됩니다.
계속 하시겠습니까? [Y/n]
받기:1 http://us.archive.ubuntu.com/ubuntu xenial/main amd64 libaio1 amd64 0.3.110-2 [6,356 B]
받기:2 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-client-core-5.7 amd64 5.7.28-0ubuntu0.16.04.2 [6,575 kB]
받기:3 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-common all 5.7.28-0ubuntu0.16.04.2 [14.7 kB]
받기:4 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-client-5.7 amd64 5.7.28-0ubuntu0.16.04.2 [1,476 kB]
받기:5 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 mysql-client all 5.7.28-0ubuntu0.16.04.2 [10.0 kB]
내려받기 8,082 k바이트, 소요시간 28초 (284 k바이트/초)            
Selecting previously unselected package libaio1:amd64.
(데이터베이스 읽는중 ...현재 180860개의 파일과 디렉터리가 설치되어 있습니다.)
Preparing to unpack .../libaio1_0.3.110-2_amd64.deb ...
Unpacking libaio1:amd64 (0.3.110-2) ...
Selecting previously unselected package mysql-client-core-5.7.
Preparing to unpack .../mysql-client-core-5.7_5.7.28-0ubuntu0.16.04.2_amd64.deb ...
Unpacking mysql-client-core-5.7 (5.7.28-0ubuntu0.16.04.2) ...
Selecting previously unselected package mysql-common.
Preparing to unpack .../mysql-common_5.7.28-0ubuntu0.16.04.2_all.deb ...
Unpacking mysql-common (5.7.28-0ubuntu0.16.04.2) ...
Selecting previously unselected package mysql-client-5.7.
Preparing to unpack .../mysql-client-5.7_5.7.28-0ubuntu0.16.04.2_amd64.deb ...
Unpacking mysql-client-5.7 (5.7.28-0ubuntu0.16.04.2) ...
Selecting previously unselected package mysql-client.
Preparing to unpack .../mysql-client_5.7.28-0ubuntu0.16.04.2_all.deb ...
Unpacking mysql-client (5.7.28-0ubuntu0.16.04.2) ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
Processing triggers for man-db (2.7.5-1) ...
libaio1:amd64 (0.3.110-2) 설정하는 중입니다 ...
mysql-client-core-5.7 (5.7.28-0ubuntu0.16.04.2) 설정하는 중입니다 ...
mysql-common (5.7.28-0ubuntu0.16.04.2) 설정하는 중입니다 ...
update-alternatives: using /etc/mysql/my.cnf.fallback to provide /etc/mysql/my.cnf (my.cnf) in auto mode
mysql-client-5.7 (5.7.28-0ubuntu0.16.04.2) 설정하는 중입니다 ...
mysql-client (5.7.28-0ubuntu0.16.04.2) 설정하는 중입니다 ...
Processing triggers for libc-bin (2.23-0ubuntu11) ...
root@server:~# gedit /etc/apt
.ICEauthority     .local/        공개/
.Xauthority      .mozilla/       다운로드/
.bash_history     .presage/       문서/
.bashrc        .profile       바탕화면/
.cache/        .viminfo       비디오/
.config/       .vimrc        사진/
.dbus/        .xsession-errors   음악/
.gconf/        .xsession-errors.old 템플릿/
.gnupg/        hello.java      
.java/        sample.txt      
root@server:~# gedit /etc/apt/sources.list
root@server:~# ifconfig ens32
ens32   Link encap:Ethernet HWaddr 00:0c:29:90:92:02 
     inet addr:192.168.111.100 Bcast:192.168.111.255 Mask:255.255.255.0
     inet6 addr: fe80::1db2:ab38:c758:1034/64 Scope:Link
     UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1
     RX packets:78624 errors:0 dropped:0 overruns:0 frame:0
     TX packets:39721 errors:0 dropped:0 overruns:0 carrier:0
     collisions:0 txqueuelen:1000
     RX bytes:109655490 (109.6 MB) TX bytes:2876078 (2.8 MB)

root@server:~# ifconfig ens33
ens33: error fetching interface information: Device not found
root@server:~# nm.connectioneditor
nm.connectioneditor: 명령을 찾을 수 없습니다
root@server:~# nm-connection-editor
Gtk-Message: GtkDialog mapped without a transient parent. This is discouraged.
** Message: Cannot save connection due to error: 편집기 초기화 중...
** Message: Connection validates and can be saved
root@server:~# geidt /etc/resolb.conf
'geidt' 명령을 찾을 수 없습니다. 비슷한 명령:
 'gedit' 명령은 패키지 'gedit'(main)에 있습니다.
geidt: 명령을 찾을 수 없습니다
root@server:~# geidt /etc/resolv.conf
'geidt' 명령을 찾을 수 없습니다. 비슷한 명령:
 'gedit' 명령은 패키지 'gedit'(main)에 있습니다.
geidt: 명령을 찾을 수 없습니다
root@server:~# gedit /etc/resolv.conf
root@server:~# gedit /etc/resolv.conf
root@server:~# gedit /etc/resolv.conf
root@server:~# nslookup
\> server
Default server: 127.0.1.1
Address: 127.0.1.1#53
\> server 168.126.63.1
Default server: 168.126.63.1
Address: 168.126.63.1#53
\> www.nate.com
Server:    168.126.63.1
Address:  168.126.63.1#53

Non-authoritative answer:
Name:  www.nate.com
Address: 120.50.131.112
\> exit

root@server:~# gedit /etc/resolv.conf
root@server:~# gedit /etc/resolv.conf
root@server:~#
 



