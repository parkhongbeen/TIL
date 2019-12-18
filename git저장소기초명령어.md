# git 저장소 기초 명령어

> 기존 디렉토리를 Git저장소로 만들기

- Mac

```
> cd /Users/user/my_project
```

- Linux

```
> cd /home/user/my_project
```

- windows

```
> cd /c/user/my_project
```



여기서 폴더는 본인이 만든(연결하고자하는) 폴더로 한다.

그리고 아래와 같은 명령을 실행한다

```
> git remote add origin <저장소url>

> git remote

> git commit 
# (commit내용을 적기위해 vim으로 이동됨)
# 편집모드(i클릭)로 들어가서 첫줄에 제목,둘째줄에는 내용을 적는다./제목은 상세할수록 좋다.

> git push -u origin master
# 처음에 한번만 -u 설정을 하면 앞으로 git push만 입력해도 origin의 master브랜치로 push한다.
```

---

> 기존 저장소를 Clone하기

```
ex)
> git clone https://github.com/test/test
```

이 명령은 "test" 라는 디렉토리를 만들고 그 안에 `. git` 디렉토리를 만든다.그리고 저장소의 데이터를 모두 가져와서 자동으로 가장 최신버전을 Checkout 해 놓는다.

아래과 같은 명령을 사용하여 저장소를 Clone 하면 test가 아니라 다른 디렉토리 이름으로 Clone 할 수 있다.

```
$ git clone https://github.com/test/test mytest

```

디렉토리 이름이 mytest 라는 것만 빼면 이 명령의 결과와 앞선 명령의 결과는 같다.

------

> remote 저장소 변경

```
# 현재 원격 저장소 상태 확인
> git remote -v
# 변경하고자 하는 원격저장소 설정
> git remote set-url origin <저장소url>
```

