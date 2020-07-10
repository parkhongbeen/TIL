### hostname

시스템의 호스트네임이란 인터넷에 접속된 수 많은 컴퓨터들이 자신을 구별하기 위해 가지고 있는 것이 IP주소인데, IP 대신 기억하기 쉽게 사용하는 것이 호스트네임이다.

리눅스서버에서 호스트네임을 확인하는 방법은 `hostname`이란 명령어가 있는데 아래는 내 컴퓨터의 호스트명을 보여준 것이다.

![image](https://user-images.githubusercontent.com/53684676/85649274-ae81ef00-b6dd-11ea-9a63-4bded46c5d3b.png)

호스트명을 변경하는 파일은 `/etc/sysconfig/network`에서 변경만 해주고 네트워크환경을 적용하는 스크립트(/etc/rc.d/init.d/network)를 재실행 해주면 된다.

이와 같은 방법으로 호스트명을 변경하면 서버를 재부팅한 후에도 지속적으로 적용이 된다.

<!-- more -->

일시적인 호스트명을 변경할 때에는 `hostname`이라는 명령어를 이용하면 된다.

```
$ hostname
hongeens-MacBook-Pro.local
$ hostname hong
hong
$ hostname
hong
```

이와 같은 방법으로 호스트명을 변경하면 서버를 재부팅한 후에는 원래의 호스트명이 그대로 설정되어 있다. 즉, 일시적으로만 호스트명이 변경된 것이다. 좀 더 정확하게 표현한다면 hostname이라는 명령어를 이용하여 HOSTNAME 이라는 쉘변수의 값을 일시적으로 수정한 것에 불과한 것이며 재부팅을 하게 되면 원래의 호스트명이 설정이 된다.