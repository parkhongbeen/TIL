## Docker란 무엇인가?

> 가상의 환경에서 미리 정해져있는 필요한 프로그램들의 리스트를 통째로 설치하고 실행한 뒤 가상의 환경을 종료시킴으로써 내 컴퓨터는 깔끔하게 아무 영향을 받지 않도록 도와주는 프로그램

### Image, Docker engine, Container

**image**는 가상환경에 대한 설정과 설치해야할 Dependencies(패키지를 실행하기 위해 필요한 패키지 목록), 수행할 작업등을 적어놓은 설정이고 `docker build`라는 명령어를 통해 생성할 수 있습니다.

**docker engine**은 image를 통해 container라는 실행 객체를 생성하고 실행합니다.

**container**는 철저하게 가상환경에서 docker engine을 통해 실행되기 때문에 내 컴퓨터의 설정과는 무관하게, 어떤 컴퓨터에서든 동일하게 프로그램을 실행할 수 있게 해주고, 내 컴퓨터의 데이터에는 아무런 영향을 끼치지 못 하게 합니다.

`$ docker build`을통해 Image를 빌드하고

`$ docker run`을 통해 Image를 run하고 container가 실행됩니다.

### Image VS Container

https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container
stackoverflow에 좋은 질문답변글이 올라와 첨부합니다. 위 링크의 내용을 요약하면 image는 class같은 느낌이고 container는 class를 바탕으로 생성된 object같은 느낌이라고 합니다.

**Dockerfile**-> (빌드) -> **이미지** -> (실행) -> **컨테이너**

- Dockerfile: 운영 체제가 원하는 방식으로 프로비저닝(사용자의 요구에 맞게 시스템자원을 할당, 배치, 배포해 두었다가 필요시 시스템을 즉시 사용할 수 있는 상태로 미리 준비해 두는 것)하고 모든 소프트웨어를 설치/구성하는 Docker지침 세트가 포함되어 있습니다.

- 이미지: 컴파일 된 Docker 컨테이너를 실행할 때마다 Dockerfile을 다시 작성하는 시간을 절약합니다.
- 컨테이너: 가상 운영 체제 자체가 실제 환경인 것처럼 ssh를 사용하여 원하는 명령을 실행할 수 있습니다.

즉, 같은 image라도 각 container별로 사용자가 프로그램을 진행시키는 방향에 따라 프로그램의 결과가 달라질 수 있다는 말입니다.또한 image는 설정과 수행할 작업에 대한 정보들이라고 할 수 있고, container는 그 설정을 바탕으로 작업을 하고 있는 작업 영역이라고 볼 수 있습니다.

### Docker를 통해 어떤 작업을 하는 걸까?

Docker는 수행하고자 하는 작업 혹은 프로그램에 필요한 패키지의 **dependencies**(패키지를 실행하기 위해 필요한 패키지목록)을 **모두 담아 이미지**를 만듭니다. 그리고 그 image를 run하면 **내 컴퓨터에 필요한 dependencies가 없더라도! 마치 있는 것처럼 프로그램이 동작**하게 됩니다.!

docker engine을 이용해 image에 입력된 설정과 작업들을 바탕으로 container가 실행되게 되는 것이죠,

![도커흐름](https://user-images.githubusercontent.com/53684676/79072710-6c235580-7d1d-11ea-8b5e-136b15b7a00c.png)

![도커파일이미지컨테이너](https://user-images.githubusercontent.com/53684676/79072721-7d6c6200-7d1d-11ea-9d12-f0617f1a0897.png)

### 가상환경

![가상환경](https://user-images.githubusercontent.com/53684676/79072743-99700380-7d1d-11ea-8212-d4767f5b349f.png)

### Docker

![도커](https://user-images.githubusercontent.com/53684676/79072741-9543e600-7d1d-11ea-8219-67de6ec4855f.png)