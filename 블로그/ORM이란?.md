## SQL ORM(Object Relational Mapping)

![image](https://user-images.githubusercontent.com/53684676/90131200-b5a4af80-dda6-11ea-84a2-09d2afd52654.png)

### ORM이란?

데이터베이스와 객체 지향 프로그래밍 언어(Python, node JS 등)간의 호환되지 않는 데이터를 변환, 맵핑하는 프로그래밍 기법입니다.

객체 지향 프로그래밍언어(OOP)는 클래스라는 개념이 있고, RDBMS에는 테이블이라는 개념이 있습니다.

OOP를 사용해서 작성된 클라이언트 프로그램이 압도적으로 많습니다. OOP를 사용하는데 제약을 받지 않고, RDBMS를 이용하기 위한 프레임워크로 이해하면 됩니다.

예를 들면, 클래스로 스키마(Schema)를 매핑하고, 메소드(Method)로 쿼리(Query)를 작성하면, 객체로 이루어진 테이블을 가져올 수 있습니다.

### ORM 장, 단점

#### 장점

1. 별도 SQL을 사용하지 않고 OOP언어 그대로를 사용할 수 있습니다.
2. DBMS에 대한 종속성을 줄일 수 있습니다.

#### 단점

1. 직접 SQL을 사용하는 것보다 복잡할 수 있습니다.(자동으로 생성되는 쿼리 때문)
2. 속도나 생산성이 저하될 수 있습니다.

### ORM액세스용 드라이버(for MS SQL Server)

| C#      | Entity Framework Core                           |
| ------- | ----------------------------------------------- |
| Java    | Hidernate ORM                                   |
| PHP     | Elpquent ORM, Laravel 설치에 포함되어 있습니다. |
| Node.js | Sequelize ORM                                   |
| Python  | Django                                          |
| Ruby    | Ruby on Rails                                   |

