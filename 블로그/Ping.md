## Ping개념, 사용법

### Ping(Paket InterNet Groper)이란?

ping명령의 기본적인 작동 원리는 네트워크 상태를 확인하려는 대상컴퓨터를 향해 일정 크기의 패킷(packet)을 보낸 후 대상 컴퓨터가 이에 대해 응답하는 메시지를 보내면 이를 수신, 분석하여 대상 컴퓨터가 작동하는지, 또는 대상 컴퓨터까지 도달하는 네트워크 상태가 어떠한지 파악할 수 있습니다.

ping명령은 **TCP/IP 프로토콜 중 ICMP를 통해 동작**하므로, 이 프로토콜을 지원하지 않는 기기를 대상으로 ping수행할 수 없습니다. 또한 보안의 이유로 ICMP사용을 차단하는 기기 역시 ping요청에 대응하지 않습니다.

이해를 위해 간단한 예제를 정리해볼건데, 운영체제마다 조금씩 측정하는 방법이 다르므로 전 맥 OS에서 Ping테스트 방법으로 정리해보겠습니다.

<!-- more -->

1. 기본 게이트웨이 주소를 알아보기 위해서는 명령어`netstat -nr`

![image](https://user-images.githubusercontent.com/53684676/85018216-c4f0ed80-b1a7-11ea-8029-f570ddf3b0fa.png)

해당 명령어를 실행하면 라우팅 테이블의 정보가 표시됩니다. 스크린샷과 같이 default라고 적힌 줄의 게이트웨이가 기본 게이트웨이의 주소입니다.

2. 수신상태 측정 `ping 목적지 옵션`

<img width="568" alt="image-20200618211014983" src="https://user-images.githubusercontent.com/53684676/85018744-aa6b4400-b1a8-11ea-9794-54c79c328fd3.png">

스크린샷을 설명해드린 반복해서 google.co.kr에 통신을 시도합니다. 가장 마지막에 나오는 time은 응답시간을 나타내며 숫자가 낮을수록 빠른 속도를 의미합니다. 팁으로 `Control + C`를 누르면 종료되며 최종 통계를 출력합니다.

이 외 방법으로 맥 OS에서는 네트워크 유틸리티를 통해 상태를 알아볼 수 있습니다. 먼저 Spotlight 에서 `네트워크 유틸리티`를 검색한 후 들어가봅니다.

<img width="643" alt="image-20200618211331581" src="https://user-images.githubusercontent.com/53684676/85018766-b1925200-b1a8-11ea-9b49-a78ae92a151d.png">

첫화면 입니다. 여기서 상단바 세번째에 있는 Ping을 누른 후 네트워크 주소를 입력해봅니다.

![image](https://user-images.githubusercontent.com/53684676/85018849-d4246b00-b1a8-11ea-8665-8671401e2b5f.png)

터미널에서 보았던 것과 동일한 결과값을 볼 수 있습니다.