## 프로세스(Process)란?

> 실행중인 프로그램, 작업, 테스크라고도 부름

### 프로세스와 프로그램의 차이

프로그램자체는 생명이 없습니다.프로그램은 보조 기억장치(하드디스크, SSD)에 존재하며 실행되기를 기다리는 명령어(코드)와 정적인 데이터의 묶음입니다. 이 프로그램의 명령어와 정적 데이터가 메모리에 적재되면 생명이 있는 프로세스가 됩니다.

### 프로세스 구조

- **Text**: 코드, 기계어
- **Data**: 변수/초기화된 데이터
- **Heap**: 코드에서 동적으로 만들어지는 데이터
- **Stack** : 임시 데이터

![image](https://user-images.githubusercontent.com/53684676/83714280-45bad000-a665-11ea-8a1f-1b2e3eaa8dbd.png)

> 위 그림에서 보면 Heap과 Stack사이에 빈 공간을 설명해드리면, 컴파일타임에 지역변수를 얼마나 사용할지 미리 계산할 수 없기 때문에 런타임에 지역변수 선언 순서에 따라 스택영역은 위쪽으로 주소 값을 매기고 동적 할당될 때 힙영역은 아래쪽으로 주소값을 매깁니다.

### PCB (Process Control Block)

프로세스에 대한 정보는 **PCB**에 저장됩니다. PCB는 크게 다음과 같은 정보를 담고 있습니다.

- **PID(Process IDentification)**: 프로세스 식별번호
- **프로세스 상태**: CPU 프로세스를 빠르게 교체하면서 실행하기 때문에 실행중인 프로세스도 있고 대기중인 프로세스도 있습니다. 

- **PC(Program Counter)**: 다음 실행할 코드의 주소
- **SP(Stack Pointer)**: 스택 최상단 주소
- **스케줄링 우선순위**: 여러개의 프로세스가 CPU에서 실행되는 순서를 결정하는 것을 스케줄링이라고 합니다.

![image](https://user-images.githubusercontent.com/53684676/83718776-b0bdd400-a670-11ea-90d1-db7047bfb4f2.png)

위 그림은 리눅스예시의 PCB

### 정리

- 프로세스 구조
  - Stack, Heap, Data(BSS, Data), Text(Code)
- PCB
  - 프로세스 상태 정보 - PC, SP, 메모리, 스케줄링 정보 등

## IPC(InterProcess Communication)

> 프로세스들 간에 데이터 및 정보를 주고받기 위한 메커니즘

### 프로세스간 커뮤니케이션

프로세스는 다른 프로세스 공간에 접근할 수 없습니다.

### 프로세스간 통신의 필요성

성능을 높이기 위해 여러 프로세스를 만들어서 동시에 실행합니다.이 때 프로세서간 상태 확인 및 데이터 송수신이 필요합니다.

### 다양한 IPC기법

File사용, MessegeQueue, SharedMemory, Pipe, Signal, Semaphore, Socket

![image-20200219193905433](https://user-images.githubusercontent.com/53684676/83717693-54f24b80-a66e-11ea-9b00-a06aad9f0bef.png)

### 정리

여러 프로세스를 동시에 실행을 통한 성능 개선, 복잡한 프로그램을 위해 프로세스간 통신이 필요하다. 하지만 프로세스간의 공간이 분리되어 있다. 프로세스간 통신을 위해 특별한 기법은 IPC(InterProcessCommunication)이다. 대부분의 IPC기법은 결국 커널공간을 활용하는 것이다. / 이유는 커널 공간은 공유하기 때문이다.