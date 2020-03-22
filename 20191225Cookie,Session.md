# Cookie와 Session

### 쿠키(cookie)란?

- 웹 서버가 브라우저에게 지시하여 사용자의 로컬컴퓨터에 파일 또는 메모리에 저장하는 작은 기록정보 파일
- 파일에 담긴 정보는 인터넷 사용자가 같은 웹사이트를 방문할 때마다 읽히고 수시로 새로운 정보로 바뀔 수 있음

### 쿠키구성요소

#### Name

- 쿠키의 이름

#### Value

- 쿠키의 저장된 값

#### Expires

- 쿠키가 언제 삭제되는지 결정
- ex) `exprires = "Wdy, DD-Mon-YYYY HH:MM:SS GMT"`
  - ​	쿠키에 만료일이 포함되어 있으면 영구적 쿠키로 간주.
  - `Max-Age` 를 통해 지정된 만료일에 되면 디스크에서 쿠키가 제거.

#### Domain

- 쿠키가 사용되는 도메인을 지정
- ex) domain=hongbeen.github.io
  - 이 값이 현재 탐색중인 도메인과 일치하지 않을 경우,"다사 쿠키"로 간주되며 브라우저에서 거부
  - 이렇게하여 한 도메인에서 다른 도메인에 대한 쿠키를 사용하지 못하게 설정

#### path

- 쿠키를 반환할 경로를 결정
- ex) path=/
  - 도메인의 루트 경로로 이동할 경우 쿠키가 전송

#### Secure

- 보안 연결 설정

-------

### 세션(HTTP Session)이란?

- HTTP Session id를 식별자로 구별하여 데이터를 사용자의 브라우저에 쿠키형태가 아닌 접속한 서버 DB에 정보를 저장합니다.
- 클라이언트는 HTTP Session id를 쿠키로 메모리 저장된 형태로 가지고 있습니다.
- 메모리에 저장하기 때문에 브라우저가 종료되면 사라집니다.

#### 세션절차

1. 클라이언트가 서버에 Resource를 요청합니다.
2. 서버에서는 HTTP Request를 통해 쿠키에서  Session id를 확인을 한 후에 없으면 Set-Cookie를 통해 새로 발행한 Session-id를 보냅니다.
3. 클라리언트는 HTTP Request 헤더에 Session id를 포함하여 원하는 Resource를 요청을 합니다.
4. 서버는 Session id를 통해 해당 세션을 찾아 클라이언트 상태 정보를 유지하며 적절한 응답을 합니다.

![No Image](https://nesoy.github.io/assets/posts/20170317/5.PNG)