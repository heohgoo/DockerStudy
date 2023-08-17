# DockerStudy


## 😁 Docker

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/9f0e2528-73ce-4d0f-b8c7-3d50f4ff3de0)


> * IT 소프트웨어 "Docker"는 Linux® 컨테이너를 만들고 사용할 수 있도록 하는 컨테이너화 기술입니다.
> * 오픈소스 Docker 커뮤니티는 모든 사용자가 혜택을 누릴 수 있도록 이러한 기술을 개선하기 위해 노력합니다.
> * Docker Inc.라는 기업은 Docker 커뮤니티의 작업을 기반으로 하여 보안을 강화하고 이러한 개선 사항을 더 큰 커뮤니티에 공유합니다. 그런 다음 엔터프라이즈 고객을 위해 개선되고 강화된 기술을 지원합니다.

```출처 : RedHat ``` => https://www.redhat.com/ko/topics/containers/what-is-docker

<br/>
<br/>



> 장점
> 
> 1. 한 대의 물리 서버에 여러 서버를 띄울 수 있다.
> 2. 서버 관리가 용이하며 다루기 쉽다.
> 3. 환경을 `격리`하여 독립된 환경에서 여러 개의 컨테이너를 띄울 수 있다.
> 4. 이미지 파일을 생성하며 `배포`할 수 있다.

<br/>
<br/>
<br/>
<br/>

## 😏 사용법

https://www.docker.com/ 의 메인화면 `or` Developers => Docs => Download and install 에서 OS(Linux, Windows, MAC)에 맞게 다운로드
<br/>
<br/>

docker desktop이나 Windows 기준 명령 프롬프트(MAC => terminals)를 통해 이미지 파일을 `docker hub(https://hub.docker.com/)`에서 `pull`하거나, `container`에 띄울 수 있다.
<br/>
<br/>

> **Windows에서 발생한 설치 오류**
>  
> 'Docker Desktop requires a newer WSL kernel version.'와 같은 오류가 발생한다면 powershell에서 `wsl --update`라는 명령어를 입력하여 WSL 버전을 업데이트하면 오류를 해결할 수 있다.

<br/>
<br/>

https://docs.docker.com/ 에서 docker를 다루는 명령어를 서치할 수 있다.

또는 docker desktop에서 검색 기능을 활용해 이미지 파일을 pull해오거나, 이미지 파일을 컨테이너에 띄울 수 있다.(당연히 제거도 가능하다.)

<br/>
<br/>

아파치 웹 서버 이미지 파일인 httpd 이미지 파일을 pull 해와서 컨테이너에 띄운 후 서버 작동 확인

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/c364447c-3690-49c4-94c3-fe244d091285)

Host의 8080번과 8081번 포트에서 Container의 80번 포트로 `포트포워딩`해주는 컨테이너 2개를 생성하였다.

<br/>
<br/>

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/c224123c-256c-45cd-8a92-d869a1327376)

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/edcfa49e-5fb1-455d-8d79-b0740d21c006)

<br/>
<br/>

docker desktop에서 로그를 확인해보면

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/228a6c51-8f17-4342-9fc3-f470d692677d)

GET 방식으로 index.html 파일을 응답받아온 것을 확인할 수 있다.

<br/>
<br/>

### 명령어 실행

<br/>
<br/>

* 터미널 환경
```
$ docker exec [OPTIONS] CONTAINER COMMAND [ARG ...] 
```

위의 코드로 명령어 실행이 가능하다.

<br/>
<br/>

* 도커 테스크탑 환경

Containers => Terminal 에 들어가서 명령어 입력하면 된다.


예를 들어, 컨테이너에 포함되어 있는 index.html 파일을 수정하고자 한다면, 해당 경로로 이동한 후 nano와 같은 에디터를 사용하여 수정하면 된다.



![image](https://github.com/heohgoo/DockerStudy/assets/95553132/f1fc6053-b06b-4c33-8d33-6510f33d5686)

<br/>
<br/>

![image](https://github.com/heohgoo/DockerStudy/assets/95553132/97105286-925e-4a43-b90d-ba680a4e97b4)




### 호스트와 컨테이너의 파일 시스템 연결
<br/>
<br/>

코드 에디터를 통해 하나의 html 파일을 생성하고 이 html 파일로 컨테이너의 html 파일을 관리할 수 있다.(디렉토리 이동)
<br/>
<br/>

해당 html 파일을 작성하고 터미널에 `윈도우` 기준

```
docker run -p 8888:80 -v C:\Users\Heo\study\docker\htdocs:/usr/local/apache2/htdocs httpd
```

(리눅스와 윈도우 간 상대 경로 표기법이 다르므로 따로 서치해서 변경 => / 사용)

<br/>
<br/>

해당 포트(8888번)에서 실행되는 웹 서버를 통해 GET 방식으로 받아오는 html 파일을 자유롭게 변경할 수 있게 된다.(버전 관리를 한다던지...)
















