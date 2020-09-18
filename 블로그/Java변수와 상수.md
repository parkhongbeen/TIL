## Java 변수와 상수

### 변수

- 변수 = 변하는 수

프로그램이 실행되면 메모리를 사용하여 정보를 기억시킵니다. 메모리에 변수를 할당하고 필요할때마다 가져와서 사용합니다. 컴퓨터는 모든 신호를 숫자로 인지합니다.(컴퓨터는 1, 0 밖에 읽을 수 없습니다.)

**Java는 변수를 선언할 때 선언할 변수안에 형태를 지정해줘야 합니다**

![image](https://user-images.githubusercontent.com/53684676/93217087-83baaa80-f7a3-11ea-8257-7efd42de71a9.png)

### 상수

- 변할 수 없는 수

변하 앞의 final을 붙여주면 상수로 변합니다.**상수는 값이 변하면 안되는 경우에 사용합니다.**

![image](https://user-images.githubusercontent.com/53684676/93217353-ea3fc880-f7a3-11ea-89c1-14d4a95e68d4.png)

### String과 Char의 차이점

`String`: `""` 사이에 문자열을 적어줍니다. -> 한글자, 여러글자 모두 사용가능합니다.

`char`: `''` 사이에 문자를 적어줍니다. -> 한글자만 사용가능합니다.

**string도 문자 하나를 표현할 수 있지만, 가장 작은 단위로 해주는 것으로 설계되어 있어서 보통 한 글자를 표현할때는 char를  사용해줍니다.**

**또, 예약어(java에서 먼저 사용하고 있는 변수들)는 변수이름으로 사용할 수 없습니다.**

![image](https://user-images.githubusercontent.com/53684676/93218606-5cfd7380-f7a5-11ea-8c1e-2e293d357726.png)

### 논리변수

true / false 두가지로만 표현

true는 1 / false는 0 표현

![image](https://user-images.githubusercontent.com/53684676/93223687-4a863880-f7ab-11ea-82f2-2d16c972c5b5.png)

### 기타변수

`byte`는 1바이트로 표시해줍니다. 한글은 1바이트가 아니므로 오류입니다.

![image](https://user-images.githubusercontent.com/53684676/93224753-6dfdb300-f7ac-11ea-87a9-0eb94e1f9c7d.png)