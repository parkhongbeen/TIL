### Screen 명령어

screen은 여러 쉘과 프로그램을 사용할 수 있습니다.또한 세션관리 기능도 지원합니다.**세션관리 기능**은 상당히 유용합니다.예를 들면, 터미널을 통해 원격 서버에 접속하여 작업을 하다가 네트워크 장애로 연결이 끊어진 경우 매우 난감할 수 있습니다. 이때 screen을 사용해서 작업중이였다면 세션을 유지할 수 있기 때문에 해당 작업은 로컬에서 계속진행되고 있으며 언제든지 다시 해당 세션을 통해 작업을 계속 할 수 있습니다. 더불어 하나의 서버에 여러명의 사용자가 접속하여 해당 스크린을 공유하여 같은 **화면을 공유**할 수도 있습니다. 이 포스팅의 아래에서는 야매?로 서버를 유지하는 예제를 보여드리겠습니다.

`$ screen` screen시작

`$ screen -S 세션명` 세션명으로 screen시작

`$ screen -R 세션명` 세션명의 scrren으로 복원. 세션이 하나일 경우 세션명을 주지 않아도 무관하며, 여러 개 존재하는 경우 세션 목록을 보여줌

`$ screen -list` 켜져있는 스크린 list를 보여줌

#### screen실행 중 명렁어

**모든 명령어는 `Ctrl + a` 이후 입력**

`c` 새 셸 생성 후 해당 셀로 이동

`a` 바로 전 셸로 이동

`n` 다음 셸로 이동

`p` 이전 셀로 이동

`번호` 번호에 해당하는 셸로 이동

`'` 셸 번호 또는 셸 이름으로 이동

`''` 셸 번호를 보여줌

`A`  현재 셸의 이름을 수정

`W` 셸 리스트를 아래에 출력

`esc` Visual모드로 전환

`[` 구간복사, 스페이스바를 눌러 시작과 끝을 지정

`]` 붙여넣기

`,` 명령행 모드로 전환

`d` 현재 작업을 유지하며 screen세션을 빠져나옴

`x` Lock screen

`s` 셀을 나눔

`tab` 나눠진 셸의 다른 영역으로 이동

`Q` 현재 영역을 제외한 나머지 숨김

### 스크린 사용해서 간단하게 서버띄우기

먼저 서버안에서 runser를 실행시키겠습니다

`$ sudo python3 manage.py runserver 0:80`

<img width="568" alt="image-20200609165520539" src="https://user-images.githubusercontent.com/53684676/84123072-4c39b500-aa74-11ea-8e59-0b93a6851dc9.png">

그리고 ip로 접근하면

<img width="1277" alt="image-20200609165621162" src="https://user-images.githubusercontent.com/53684676/84123085-50fe6900-aa74-11ea-8b6c-ea18bb306df2.png">

당연히 runserver가 켜져있습니다. 하지만 이상태에서 runserver를 끈다면 연결이 끊깁니다.

![image](https://user-images.githubusercontent.com/53684676/84123094-552a8680-aa74-11ea-991e-c6cd5ca7ff51.png)

<img width="1270" alt="image-20200609165716368" src="https://user-images.githubusercontent.com/53684676/84123108-5a87d100-aa74-11ea-89dc-10eb6c16ab28.png">

**그래서 간단하게 screen을 이용해서 서버를 유지시켜보려고 합니다.**

`screen -S runserver(세션명)` 접속 후

<img width="496" alt="image-20200609170027013" src="https://user-images.githubusercontent.com/53684676/84123146-66739300-aa74-11ea-9df4-d11980d92ea1.png">

확인해보면 screen이 돌아간다는 것을 알려줍니다.

<img width="565" alt="image-20200609170113760" src="https://user-images.githubusercontent.com/53684676/84123348-b0f50f80-aa74-11ea-88e4-133d8416da31.png">

다시 서버에 들어가서

<img width="568" alt="image-20200609170244742" src="https://user-images.githubusercontent.com/53684676/84123365-b5212d00-aa74-11ea-91df-2dc41e0972d4.png">

켜준 뒤 실행했던 셸을 닫아도 서버는 유지됩니다.

<img width="1275" alt="image-20200609170328719" src="https://user-images.githubusercontent.com/53684676/84123379-bb170e00-aa74-11ea-81c1-fe08834b8116.png">

이렇게 야매?로 서버를 켜보았습니다

#### -END