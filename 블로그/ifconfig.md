## ifconfig(configure a network interface)

> 네트워크 인터페이스 관련 정보를 조회 및 수정 할 수 있는 명령어입니다. 최근에는 ifconfig를 사용하기 보다 **ip**명령어를 쓰는 방향을 권고하고 있습니다.

### 환경 및 조건

- Linux
- Bash shell(/bin/bash)

### 예시

- 아래는 제가 ifconfig의 출력결과입니다.

![image](https://user-images.githubusercontent.com/53684676/85515449-1a118100-b638-11ea-827b-45e66acf4795.png)

### ifconfig 항목 설명

#### lo

- Network Interface들의 이름으로 여기에는 NIC, Bridge, Tacp Interface 그리고 Tunneling Interface와 같은 부분들의 이름이 표시됩니다.

#### Link encap

- 전송을 할 때 캡슐화 되는 방식을 의미합니다. 즉, 해당 인터페이스로 보내지는 패킷의 종류라고 생각하면 될 것 같습니다. Ethernet의 경우에는 이더넷 프레임으로 캡슐화 되어서 보내진다는 것이며 해당 캡슐화 종류를 통해 인터페이스의 종류도 유추가 가능합니다.(위의 경우 eth0는 Ethernet)

<!-- more -->

#### HWaddr

- Layer2에서 사용하는 하드웨어 주소로 일반적으로 아는 MAC주소로 되어있습니다.

### inet addr, inet6 addr

- 각각 IP주소를 나타내며 `inet addr`은 IPv4의 주소이고, `inet6 addr`은 IPv6의 주소입니다. `inet6 addr`에서 뒤에 표시된 `/`는 CIDR을 의미합니다.

#### Bcast

- broadcast 요청을 날릴 주소입니다.

#### Mask

- Network Mask(Subnet Mast)의 형식입니다.

#### Scope

- 해당 인터페이스가 어느 수준에서 접근가능하며 유효하냐는 의미입니다.`Global`의 경우 외부 네트워에서 접근이 가능한 범위이며 `Link`의 경우 현재 인터페이스가 속한 `LAN`안에서만 접근이 가능하고 유효하며 `Host`의 경우는 현재 인터페이스가 속해있는 호스트에서만 유효하고 접근이 가능합니다.

#### UP

- 네트워크 인터페이스가 켜져있음을 의미합니다. 켤 때는 `ifconfig [네트워크 인터페이스 이름] up`을 사용하고 끌 때는 `ifconfig [네트워크 인터페이스 이름] down`을 사용합니다.

#### Broadcast

- 브로드캐스트 패킷을 처리할 수 있음을 의미하며 해당 기능을 통해 DHCP서버로부터 IP주소를 받을 수 있습니다.

#### Running

- 네트워크 인터페이스가 정상 작동하며 트래픽(TX 및 RX)이 발생할 수 있음을 의미합니다.

#### Multicast

- 멀티캐스트 패킷을 처리할 수 있음을 의미합니다.

#### Mtu

- 해당 프로토콜이 해당 레이어에서 전송할 수 있는 최대의 단위로 이더넷의 기본값은 1500으로 설정됩니다.

#### Metric

- 우선순위를 나타내는 항목으로 0의 값부터 증가하면서 하나씩 사용할 수 있으며 낮을수록 우선순위가 높습니다. 라우팅을 할 때 여러 인터페이스 카드가 있다면 Metric이 낮은 인터페이스 카드로 라우팅을 하게 됩니다.

#### TX, RX

- 인터페이스를 통해 보내고 받은 패킷의 수를 의미합니다.

#### TX, RX errors

- 보내고 받을 때 생성되는 오류 패킷의 총 양을 의미합니다.

#### TX, TX dropped

- 여러 이ㅠ로 보내고 받는 중에 버려진 패킷의 수를 의미합니다.

#### TX, RX overruns

- 보내고 받는 버퍼에 overflow가 나서 추가하지 못한 패킷의 수를 의미합니다.

#### RX frame

- 프레임 구조에 맞지 않은 패킷의 수를 의미합니다.8bit로 프레임이 구성되어 있다고 가정할 때 이러한 프레임의 구조가 틀리거나 다를 때 버려지는 패킷의 수를 의미합니다.

#### txqueuelen

- Transmission queue의 크기를 의미합니다.

#### cllisions

- 네트워킹에서 패킷 충돌이 일어난 패킷의 수를 의미하며 정상적이라면 0이어야 합니다.

#### TX bytes, RX bytes

- 보내고 받은 데이터의 총 크기를 의미합니다.



참고자료: https://twpower.github.io/145-brief-explanation-about-ifconfig