## Asterisk(*)

파이썬에서 **Asterisk(*)**는 다음과 같이 크게 4가지 경우가 있습니다.

- 곱셈 및 거듭제곱 연산으로 사용할 대
- 리스트형 컨테이너 타입의 데이터를 반복 확장하고자 할 때
- 가변인자를 사용하고자 할 때
- 컨테이너 타입의 데이터를 Unpacking 할 때

### 1. 곱셈 및 거듭 제곱 연산으로 사용할 때

많이들 알고 계시지만 곱셈 연산, 거듭제곱 연산까지 내장 기능으로 지원하고 있습니다.

![image](https://user-images.githubusercontent.com/53684676/85656672-00ca0c80-b6ec-11ea-873a-67277d2b509f.png)

### 2. 리스트형 컨테이너 타입의 데이터를 반복 확장하고자 할 때

숫자형 데이터 뿐만 아니라 리스트형 컨테이너 타입에서 데이터를 반복적으로 확장하기 위해 사용할 수도 있습니다.

![image](https://user-images.githubusercontent.com/53684676/85656925-543c5a80-b6ec-11ea-805c-4700698e1eaf.png)

### 3. 가변인자를 사용하고자 할 때

우리는 종종 어떤 함수에서 가변인자를 필요로 할 때가 있습니다. 예를 들어, 들어오는 인자의 갯수를 모른다거나, 그 어떤 인자라도 모두 받아서 처리해야하는때가 있습니다.

파이썬에서는 인자의 종류가 두가지 있는데 하나는 positional arguments이고, 하나는 keyword arguments입니다. 전자는 말그대로 위치에 따라 정해지는 인자이며, 후자는 키워드를 가진 즉, 이름을 가진 인자를 말합니다.

![image](https://user-images.githubusercontent.com/53684676/85659665-bc407000-b6ef-11ea-8fff-c2bab7d53300.png)

위의 함수는 `first`, `second`라는 두 개의 positional arguments를 받으며,`third`, `fourth`라는 두 개의 keyword arguments를 받고 있습니다. Positional arguments의 경우 생략이 불가능하며 갯수대로 정해진 위치에 이자를 전달해야 합니다. 그러나 keyword arguments의 경우 함수 선언시 디폴트값을 설정할 수 있으며, 만약 인자를 생략할 시 해당 디폴트 값이 인자의 값으로 들어갑니다. 즉, 이 형태의 인자는 생략이 가능합니다.따라서 여기서 알 수 있는건 keyword arguments의 경우 생략이 가능하기 때문에, positional arguments이전에 선언될 수는 없습니다.

13번 line을 보시면 positional arguments가 3개, keyword arguments가 1개 전달되고 있습니다. keyword arguments의 경우 선언된 위치만 동일할 경우 키워드를 제외하고 positional arguments형태로 전달이 가능합니다. 즉, 위에서 `mike`는 자동적으로 `third`라는 키로 전달이 됩니다.

만약, 최대 4명의 주자가 아닌 10명 또는 그 이상의 정해지지 않은 주자가 있다고 가정해보겠습니다. 특히, 주자의 수가 미정일 경우 위와 같은 형태로는 처리가 불가능합니다. 이 때 사용하는게 바로 **가변인자(Variadic Arguments**)입니다.  가변인자는 좀 전에 위에서 설명한 positional arguments와 keyword arguments에 모두 사용할 수 있으며, 사용 방법은 다음과 같습니다.

#### positional arguments만 받을 때

![image](https://user-images.githubusercontent.com/53684676/85659813-e2fea680-b6ef-11ea-9d95-0225223f289e.png)

#### positional arguments와 keyword arguments를 모두 받을 때

![image](https://user-images.githubusercontent.com/53684676/85660171-42f54d00-b6f0-11ea-84b7-264987c473ff.png)

위에서 `args`는 임의이 갯수의 positional arguments를 받음을 의미하며, `**kwargs`는 임의의 갯수의 keyword arguments를 받음을 의미합니다. 이 때 `*args`,  `**kwargs` 형태로 가변인자를 받는걸 **packing**이라고 합니다.

위의 예시에서 볼 수 있듯이, 임의의 갯수와 임의의 키값을 갖는 인자들을 전달하고 있습니다. positional형태로 전달되는 인자들은 `args`라는 **tuple**에 저장되며, keyword형태로 전달되는 인자들은 `kwargs`라는 **dict**에 저장됩니다.

#### 컨테이너 타입의 데이터를 Unpacking할 때

이는 3번과 유사한 원리로, 종종 사용할만한 기능(연산)입니다. 가장 쉬운 예로, 다음과 같이 우리가 *list*나 *tuple*형태의 데이터를 가지고 있고 어떤 함수가 가변인자를 받는 경우에 사용할 수 있습니다.

![image](https://user-images.githubusercontent.com/53684676/85678239-41815000-b703-11ea-80e7-d812c594eb55.png)

`product()`함수가 가변인자를 받고 있기 때문에 우리는 리스트의 데이터를 모두 unpacking하여 함수에 전달해야 합니다. 이 경우 함수에 값을 전달할 때 `*primes`와 같이 전달하면 `primes`리스트의 모든 값들이 unpacking되어 `number`라는 리스트에 저장되빈다. 만약 이를 `primes`그대로 전달한다면 이 자체가 하나의 값으로 쓰여 `numbers`에는 `primes`라는 원소가 하나 존재하게 됩니다.