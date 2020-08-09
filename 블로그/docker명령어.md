# Docker명령어

이전 포스팅에서 도커, 이미지, 컨테이너 등의 개념들에 대해서 정리해봤습니다.이어서 docker의 명령어를 간단하게 사용 해 보려고 합니다.

## 다운로드

먼저 [이곳](https://docs.docker.com/get-docker/)을 클릭해서 다운로드를 해주세요!(Mac, Windows, Linux / 본인의 운영체제에 맞게 설치해주시면 됩니다.)

설치가 완료되면 상단에 Docker가 나타납니다. 이 후 `docker` 명령어를 사용할 수 있게 됩니다.

![image](https://user-images.githubusercontent.com/53684676/87034257-84bee100-c222-11ea-94ab-1c42147b568f.png)

<!-- more -->

## 도커 명령어

### 버전확인

![image-20200709203339955](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200709203339955.png)

### 도커 컨테이너 내부 쉘에서 나가기

도커 컨테이너 내부 쉘에서 나가는 방법은 두 가지가 있습니다. 아래 두 방법은 컨테이너를 종료시키고 나오는 방법입니다.

- `exit`: 명령어로 `exit`를 누르고 엔터
- Ctrl + D: 해당 단축키를 누르면 바로 종료

아래 방법은 컨테이너를 종료시키지 않고 나오는 방법입니다.

- `Ctrl + P, Q`: 컨테이너를 종료시키지 않고 나오기(다시 들어가려면 `$ docker attach [컨테이너이름]`)

### 도커 이미지 가져오기

아래 명령어를 사용하면 이미지 저장소에서 이미지를 내려받습니다.

```
$ docker pull [이미지이름]:[태그]
```

그럼 도커 공식 이미지 저장소에서 `centos:7`이미지를 다운받아보겠습니다.

![image](https://user-images.githubusercontent.com/53684676/87035458-5510d880-c224-11ea-9a67-c60a52bbe4c8.png)

### 이미지 확인

```
$ docker images
```

![image](https://user-images.githubusercontent.com/53684676/87036246-7b834380-c225-11ea-9e67-961de2dfcf78.png)

### 컨테이너 생성

```
$ docker run
```

![image](https://user-images.githubusercontent.com/53684676/87037801-c3a36580-c227-11ea-9b82-187a7e126243.png)

- `-i`: 상호 입출력
- `-t`: tty를 활성화하여 bash쉘을 사용
- `-d`: background에서 컨테이너를 돌림

### 컨테이너 목록 확인

![image](https://user-images.githubusercontent.com/53684676/87037910-f3526d80-c227-11ea-846f-9a1c885acaa5.png)

### exec 명령어로 외부에서 명령어 실행하기

![image](https://user-images.githubusercontent.com/53684676/87038037-2268df00-c228-11ea-9848-7645ecf4e824.png)

### 컨테이너 멈추기

![image-20200709210811267](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200709210811267.png)

### 삭제

```
$ docker rm [컨테이너id]  #컨테이너삭제

$ docker rmi [이미지id]  #이미지삭제
```