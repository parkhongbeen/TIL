**인터프리터 EX)**

우리가 자바스크립트를 이용하여 뷰포트위에 임의의 버튼을 누르면 텍스트컬러가 빨간색으로 바뀌게  하자

먼저 자바스크립트는 한줄한줄 컴파인되는  인터프리터 언어이다.

아래 코드는  "<script>" 부분이  "<body>"상단에 위치한 경우이다.

![캡처1](https://user-images.githubusercontent.com/53684676/66066711-03e10380-e585-11e9-9a3e-2e08a8ce7d4a.JPG)

이러한 경우 onclick 이벤트가 발생해도 텍스트컬러는 그대로이며 오류가 뜬다.

![캡처3](https://user-images.githubusercontent.com/53684676/66066725-09d6e480-e585-11e9-8c7b-c1b704af1ab8.JPG)

이러한 오류를 잡기위해서는 아래 그림과 같이 "<body>"하단에 위치하게 한다. 

![캡처2](https://user-images.githubusercontent.com/53684676/66066720-05aac700-e585-11e9-90bc-fc7ea1786dae.JPG)



"<script>"부분을 <"body>"의 하단에 위치하게 한다면 순차적으로 읽어서 아래와 같이 onclick이벤트가 작동된다. 



![캡처4](https://user-images.githubusercontent.com/53684676/66066732-0c393e80-e585-11e9-92e1-74675f73a059.JPG)

