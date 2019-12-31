**도커란?**

* 복잡한 리눅스 어플리케이션을 컨테이너로 묶어서 실행할 수 있음

* 개발, 테스트, 서비스 환경을 하나로 통일, 효율적 관리 가능

* 컨테이너를 공유할 수 있다



**컨테이너란?**

* 가상화보다 훨씬 가벼운 기술



**가상머신**

* 미리구축한 가상 머신 이미지를 여러서버에 복사하여 실행하면 이미지 하나로 서버를 계속 만들수 있다

* 클라우드 서비스 - 서버를 임대해주는 서비스 등장
* 가상머신, 문제 발생 - 컴퓨터를 통째로 만들다보니 각종 성능 손실 발생
* 인텔, amd는 cpu안에 가상화 기능 삽입 시작
* 문제: 느림(가상화의 가장 큰 문제점)
* 호스트와 커널을 공유하는 반가상화 기술 등장
* 이미지 안에 os가 포함되기 때문에 이미지 용량이 너무 큼
* 오픈소스 가상화 소프트웨어는 os가상화에 주력 -배포와 관리 기능이 부족



**리눅스 컨테이너**

* 컨테이너 안에 가상 공간을 만들지만 실행 파일을 호스트에서 직접 실행
* 가상화라기보다는 컨테이너로 격리되어있다



**도커의 특징**

* 도커는 게스트 os를 설치하지 않음
* 이미지 생성과 배포에 특화 되어 있음
* 중앙저장소에 이미지를 올리고 받을 수 있음, 이미지버전 관리도 제공
* 다양한 API를 제공하여 원하는 만큼 자동화 가능
* 개발과 서버 운영에 유용



**도커 이미지, 컨테이너**

**이미지**는 서비스 운영에 필요한 서버 프로그램, 소스코드, 컴파일된 실행파일을 묶은 형태

**컨테이너**는 이미지를 실행한 상태



이미지로 여러개의 컨테이너를 만들 수 있음

운영체제를 치면 이미지는 실행파일이고 컨테이너는 프로세스



**도커의 이미지 처리 방식**

- 유니온 파일 시스템 형식 (바뀐부분과 합쳐짐 = 유니온)
- 도커는 베이스 이미지에 바뀐 부분만 이미지로 생성
- 컨테이너로 실행할 때는 베이스 이미지와 바뀐부분을 합쳐서 실행
- Docker hub 및 개인 저장소에서 이미지를 공유할 때 바뀐 부분만 주고 받음
- 각 이미지들은 의존 관계를 형성한다



**서비스 운영 환경과 도커**

클라우드 환경

* 호스팅 or IDC 코로케이션 서비스 사용
* 서버 구입과 설치에 돈이 많이 들고 시간이 오래 걸림
* 가상 서버를 임대하여 사용한 만큼만 요금 지불
* 클릭 몇 번 만으로 가상 서버를 생성



Immutable infrastructure**

* 한번 설정한 운영 환경은 변경하지 않는다는 개념
* 서비스 운영 환경을 이미지로 생성한 뒤 서버에 배포하여 실행
* 서비스가 업데이트 되면 운영 환경 자체를 변경하지 않고 이미지를 새로 생성하여 배포
* 클라우드 플랫폼에서 서버를 쓰고 버리는 것과 같이 Immutable infrastructure도 서비스 운영환경을 쓰고 버림





\#1 도커 저장소 추가 (아래 내용 추가 후 저장)

root@server:~# gedit /etc/apt/sources.list         

 :deb https://apt.dockerproject.org/repo ubuntu-xenial main


#2 apt-get udpate 

#3 HTTPS 통신을 위한 패키지와 공개키를 설치

root@server:~# apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common
root@server:~# apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

#4 linux-image extra 및 docker-engine 패키지 설치

root@server:~# apt-get install linux-image-extra-$(uname -r)

root@server:~# apt-get install docker-engine ⇐ 설치 여부 질문에 Yes 입력

#5 도커 설치 확인

root@server:~# docker version

Client:

 Version:   17.05.0-ce 

API version: 1.29

 Go version:  go1.7.5 

Git commit:  89658be Built:    Thu May  4 22:10:54 2017 OS/Arch:   linux/amd64
Server: Version:   17.05.0-ce API version: 1.29 (minimum version 1.12) Go version:  go1.7.5 Git commit:  89658be Built:    Thu May  4 22:10:54 2017 OS/Arch:   linux/amd64 Experimental: false

**도커 이미지 생성** **#1 작업 디렉터리 및 main.go 파일 생성**

root@server:~# cd ~root@server:~# mkdir dockerroot@server:~# cd dockerroot@server:~/docker# gedit main.go// 8080 포트로 대기하는 웹 서버에 /로 요청이 들어오면 Hello Docker!!라는 응답 메시지를 반환package main
import (	"fmt"	"log"	"net/http")
func main() {	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {		log.Println("received request")		fmt.Fprintf(w, "Hello Docker!!")	})
	log.Println("start server")	server := &http.Server{Addr: ":8080"}	if err := server.ListenAndServe(); err != nil {		log.Println(err)	}}
**#2 main.go 실행 및 확인**root@server:~/docker# apt-get install golang-go
root@server:~/docker# go run main.go2019/12/23 15:00:03 start server
(새 터미널에서)root@server:~# curl http://localhost:8080/Hello Docker!!root@server:~# 
(브라우져에서)![img](https://lh6.googleusercontent.com/FeHFi3_S5cG3S2kJ5i-8fQxfOw01PegyZEGoTCU8SjCXeMpH6d-KI4Kl7MWZLnO-3SgFeVZrXz3-7kAT06zPKWo187ip67u0ywhnp86sV5Q7d8FgSM3FVPGJ3o_lYAgbXclaeUWu)
**#3 Dockerfile 작성**root@server:~/docker# gedit DockerfileFROM golang:1.9  ⇐ 베이스 이미지를 가져온다.(저장소 이름이 생략 → 도커 허브의 공식 이미지)
RUN mkdir /echo  ⇐ 컨테이너 내부에 /echo 디렉터리 생성하라 COPY main.go /echo
CMD [ "go", "run", "/echo/main.go" ]

**#4 도커 이미지를 빌드**root@server:~/docker# docker image build -t example/echo:latest .Sending build context to Docker daemon 3.072kBStep 1/4 : FROM golang:1.91.9: Pulling from library/golang55cbf04beb70: Pull complete 1607093a898c: Pull complete 9a8ea045c926: Pull complete d4eee24d4dac: Pull complete 9c35c9787a2f: Pull complete 8b376bbb244f: Pull complete 0d4eafcc732a: Pull complete 186b06a99029: Pull complete Digest: sha256:8b5968585131604a92af02f5690713efadf029cc8dad53f79280b87a80eb1354Status: Downloaded newer image for golang:1.9 ---> ef89ef5c42a9Step 2/4 : RUN mkdir /echo ---> Running in d574ae29436d ---> f629052dbb9cRemoving intermediate container d574ae29436dStep 3/4 : COPY main.go /echo ---> 365a8e8b706aRemoving intermediate container f9086399c9feStep 4/4 : CMD go run /echo/main.go ---> Running in 43ef8d52b72f ---> be867a4ba9d0Removing intermediate container 43ef8d52b72fSuccessfully built be867a4ba9d0Successfully tagged example/echo:latest**#5 도커 이미지 확인**root@server:~/docker# docker image lsREPOSITORY     TAG                 IMAGE ID      CREATED             SIZEexample/echo    latest              be867a4ba9d0    5 minutes ago       750MBgolang       1.9                 ef89ef5c42a9    17 months ago       750MBroot@server:~/docker# docker imagesREPOSITORY     TAG                 IMAGE ID      CREATED             SIZEexample/echo    latest              be867a4ba9d0    5 minutes ago       750MBgolang       1.9                 ef89ef5c42a9    17 months ago       750MB**#6 도커 컨테이너 실행**root@server:~/docker# docker container run -p 9000:8080   example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -d  example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -it example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -itd example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -it example/echo:latest /bin/bashroot@server:~/docker# docker container run -p 9000:8080 -itd example/echo:latest /bin/bash**#7 백그라운드에 실행되는 컨테이너에 접속**root@server:~/docker# docker attach CONTAINER_ID**#8 도커 컨테이터에서 빠져 나오는 방법**입력을 받을 수 없는 경우 ⇒ (다른 터미널에서) docker container stop CONTAINER_ID입력을 받을 수 있는 경우 ⇒ Ctrl+C or Ctrl+PQ쉘이 제공되는 경우 ⇒ exit or Ctrl+PQ**#9 도커 컨테이너 상태 확인**root@server:~/docker# docker container psroot@server:~/docker# docker container ps -a



```shell
example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -it example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -itd example/echo:latestroot@server:~/docker# docker container run -p 9000:8080 -it example/echo:latest
```

~~~

~~~

