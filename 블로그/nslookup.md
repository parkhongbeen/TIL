## nslookup

> name server loopup의 약자입니다. 네임 서버에 질의하는 프로그램입니다. IP주소를 아는데 도메인을 모르거나, 도메인은 아는데 IP주소를 모를 때 알기 위해 사용합니다.

### 1. 정방향 조회

도메인명을 명령줄에 입력하면 IP주소 값을 얻은 수 있습니다. set type 기본값이 A(호스트) 조회이기 때문에 별다른 옵션을 주지 않아도 정방향 조회는 기본으로 가능합니다.

![스크린샷 2020-06-23 오후 10 28 28](https://user-images.githubusercontent.com/53684676/85410002-82615380-b5a1-11ea-83c1-2bb9503b85e8.png)

### 2. 서버 변경

DNS에 쿼리를 하는 서버를 변경할 수 있습니다. 이는 다른 DNS에 쿼리를 할 필요가 있을 때 유용합니다.

![스크린샷 2020-06-23 오후 10 29 08](https://user-images.githubusercontent.com/53684676/85410009-84c3ad80-b5a1-11ea-8540-1778b1e363c8.png)

<!-- more -->

### 3. 역방향(PTR) 조회

PTR에 등록된 값을 확인 할 수 있습니다. 이 옵션을 주어야만 Reverse DNS에 정상적으로 등록 되어 있는지 확인이 가능합니다.

![스크린샷 2020-06-23 오후 10 29 45](https://user-images.githubusercontent.com/53684676/85410019-868d7100-b5a1-11ea-85f1-4190de0e60ef.png)

### 4. MX 조회

메일 익스체이저(MX)값을 조회 할 수 있습니다. 이는 다시 말하면 메일서버 IP주소 및 호스트명을 확인 할 때 유용합니다.

![스크린샷 2020-06-23 오후 10 30 17](https://user-images.githubusercontent.com/53684676/85410029-88573480-b5a1-11ea-8616-429ff8b0a5e2.png)

### 5. SPF 조회

SPF값을 조회 할 수 있습니다.

![스크린샷 2020-06-23 오후 10 30 54](https://user-images.githubusercontent.com/53684676/85410034-8a20f800-b5a1-11ea-95dc-c2f189073fe3.png)

### 6. 네임서버 조회

네임서버(ns)를 조회 할 수 있습니다.

![스크린샷 2020-06-23 오후 10 31 31](https://user-images.githubusercontent.com/53684676/85410040-8beabb80-b5a1-11ea-8fba-3e14baa14df7.png)

### 7. 모든 값 조회

Any옵션을 주면 조회 할 수 있는 모든 값을 한번에 조회가 가능합니다.

![스크린샷 2020-06-23 오후 10 32 29](https://user-images.githubusercontent.com/53684676/85410051-8f7e4280-b5a1-11ea-9b03-27f9d70b54bb.png)