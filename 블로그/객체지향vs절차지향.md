# 절차지향 vs 객체지향

## 절차지향(Procedural Programming)

**절차지향 프로그래밍**은물이 위에서 아래로 흐르는 것처럼 **순차적인 처리**가 중요시 되고 프로그램 전체가 유기적으로 연결되도록 만드는 프로그래밍 기법을 말합니다. 대표적인 절차지향 언어에는 C언어가 있는데, 이는 컴퓨터의 작업 처리 방식과 유사하기 때문에 객체지향 언어를 사용하는 것에 비해 더 빨리 처리되어 시간적으로 유리하다고 볼 수 있습니다. 옛날에는 하드웨어와 소프트웨어의 개발속도 차이가 크지 않았다면 지금은 하드웨어의 개발속도가 소프트웨어의 속도를 따라오지 못하는 상황이 발생합니다.이는 **객체지향 언어**가 나타나면서 이러한 현상이 존재하게 되었습니다.

### 장점

- 컴퓨터의 처리구와 유사해 실행속도가 빠르다.
- 메모리를 직접 조작할 수 있다.
- 복잡도가 단순하다.

### 단점

- 유지보수가 어렵다.
- 많은 지역변수를 사용한다.
- 원하는 기능의 코드를 가져와서 복붙하면 오류가 발생한다.

### 언어

C언어, 베이직

## 객체지향(Object Oriented Programming)

**객체지향**은 절차지향 언어와 달리 실제 세계를 모델링하여 소프트웨어를 개발할 수 있습니다. 우리가 흔히 보는 의자 책상 등을 하나의 객체로 프로그래밍할 수 있다는 것입니다. 객체지향 프로그래밍에서는 데이터와 절차를 하나의 덩어리로 묶어서 생각해야 되고 마치 컴퓨터 부품을 하나씩 모아서 조립하는 것처럼 각 기능들을 불러와서 자신이 원하는 소프트웨어를 개발하는 것입니다.

1. **캡슐화**
   - 캡슐화란 관련된 데이터와 알고리즘(코드)이 하나의 묶음으로 정리된 것으로 이러한 기능을 이용하여 개발가 직접 개발하기 보다는 기존에 만들어져 있던 정형화된 코드들을 가져옵니다. 관련된 코드와 데이터가 묶여있고 오류가 없어 사용이 편리합니다. 또한 데이터를 감추고 외부 세계와의 상호작용은 메소드를 통하는 방법인데, 라이브러리로 만들어 업그레이드하면 쉽게 바꿀 수 있습니다.
2. **상속**
   - 상속이란 이미 작성된 클래스들을 이어받아서 새로운 클래스를 생성하는 기법으로 위에서 말했던 기존의 자신이 필요로하는 코드들을 **재활용**하여 사용하는것을 말합니다. 이것이 **절자지향과 비교되는 객체지향방법의 가장 큰 장점 중 하나로 볼 수 있습니다**.
3. **다향성**
   - 다향성이란 **하나의 이름으로 많은 상황에 대처하는 기법**을 말한다.개념적으로 동일한 작업을 하는 함수들에 똑같은 이음을 부여할 수 있고 코드가 더 간단해지는 효과를 볼 수 있다.

### 장점

- 신뢰성있는 소프트웨어를 쉽게 작성할 수 있다.
- 재사용성 및 확장이 용이하다.
- 유지보수에 유리하다

### 단점

- 처리 속도가 절차지향보다 느리다.
- 설계가 다소 어렵다

### 언어

C++, Javascript, Python, JAVA 등

## 객체지향과 절차지향의 차이점

객체지향의 반대는 절차지향이 아니고 절차지향의 반대 역시 객체지향이 아닙니다. 위에서 설명한 것처럼 절차지향은 순차적으로 실행에 초점이 되어 있고 객체지향은 객체간의 관계조직에 초점을 두고 있습니다.

![](https://user-images.githubusercontent.com/53684676/79070178-e9939980-7d0e-11ea-85ab-61889a1be6cb.png)

객체 지향 역시 순서도를 보면 절차지향적으로 프로그래밍이 실행되는걸 볼 수 있습니다. 다만 절차지향은 데이터에 초점을 두고 실행되지만, 객체지향은 기능을 중점으로 실행되는 것을 볼 수 있습니다.각 함수마다 하는 역할들이 나눠져 있기 때문입니다.