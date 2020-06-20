## Iterator

collection(list, tuple, set, dict), 문자열 등은 for문을 사용해서 데이터를 하나씩 처리할 수 있습니다. 이처럼 데이터를 하나씩 처리할 수 있는 collection이나 sequence를 `Iterable Object`라고 합니다.

![image](https://user-images.githubusercontent.com/53684676/85111113-da6d2280-b24e-11ea-81eb-929e135f71e3.png)

파이썬 `built-in` 함수 `iter`는 `iterator`를 리턴합니다. `Iterator`는 `next()`를 사용하여 다음 `element`를 가져옵니다. 만약, 더이상 `next() element`가 없을 경우 `StopIteration Exception`을 발생시킵니다.

![image](https://user-images.githubusercontent.com/53684676/85110692-3edbb200-b24e-11ea-8670-8c6b83d7197a.png)

## Geneator

`Generator`는 `Iterator`를 생성하는 함수로 함수안에 `yield`를 사용하여 데이터를 하나씩 리턴합니다. `Generator`함수가 호출되면 함수 실행 중 처음 만나는 `yield`에서 값을 리턴합니다. 이 후 `Generator`함수가 호출되면 직전에 실행되었던 yield문에서부터 다음 yield문을 만날때까지 실행합니다. Generator함수를 변수에 할당하는 변수는 `Generator`객체가 됩니다.

![image](https://user-images.githubusercontent.com/53684676/85111323-20c28180-b24f-11ea-808e-5e7194d310cb.png)

### Generator표현식

Generator표현식은 List Comprehension과 유사하여 Generator Comprehension이라고도 불립니다. Generator표현식은 `()`를 사용하며 **Generator 객체를 리턴**합니다. 실행은 하지 않고 Generator표현식만 가지며 yield방식으로 `Lazy Operation(게으른 연산)`을 수행합니다.

![image](https://user-images.githubusercontent.com/53684676/85112152-2cfb0e80-b250-11ea-8dcc-544e40127677.png)

