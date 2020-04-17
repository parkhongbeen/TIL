## select_related, prefatch_related

하나의 QuerySet 객체를 가져올 때 **연관있는 Model들을 같이 가져오게**해주는 메서드이다.

다만 두 메서드를 사용할 타이밍은 각 각 다르다.

SQL에서 JOIN구문은 하나의 쿼리에서 여러개의 테이블에 접근해서 다양한 값들을 얻는다. selected_related와 prefetch_related도 마찬가지다.(내부적으로 JOIN구문을 사용한다.)다만, 표현방식이 좀 더 ORM스럽게 바뀐 것 뿐이다.이렇게 두 메서드 모두 DB에 접근하는 횟수,즉 쿼리의 개수를 줄임으써 성능향상을 할 수 있다.

```python
# 예제모델
from django.ab import models

class Person(models.Model):
  name = models.CharField(max_length=16)
  
  def __str__(self):
    return self.name

class Car(models.Model):
  name = models.CharField(max_length=32)
  owner = models.ForeignKey(Person)
  
  def __str__(self):
    return self.name
```

### ForeignKey는 select_related

**Select_related**는 `1:1`의 관계에서 사용할 수 있고,혹은 `1:N`관계에서 N이 사용할 수 있다. 위에 만든 코드에서는 `Car`기준으로 사용할 수 있다.

```python
# 1
car = Car.objects.get(id=1)
owner = car.owner
```

```python
# 2
car = Car.objects.select_related('owner').get(id=1)
owner = car.owner
```

위 두개의 코드는 그렇게 큰 차이는 없다.

하지만 1번 코드의 쿼리 개수는 총 2개, 2번코드의 쿼리 개수는 총 1개이다.1번 코드는 `Car`모델에서 `car`를 `id`로 `get`하기 위한 쿼리1개 + 그 `car`의 `owner`를 찾기 위한 쿼리 1개 해서 총 2개이다.

그에 비해 2번 코드는 `Car`모델에서 `car`를 `id`로 `get`함과 동시에 Person모델에서 `car`의 `owner`를 찾아둔다.

N(여기서는 Car 모델)의 입장에서 바라볼 때 1은 1개밖에 없다.

이런 경우에 `select_related`를 사용한다.

### ManyToManyField는 prefatch_related

**prefetch_related**는 반대로 `M:N`에 관계에서 사용할 수 있고,`1:N`의 관계에서 1이 사용할 수 있다.

한 Person인스턴스가 가진 car들을 가져오고 싶을 때의 예시이다.

```python
owner = Person.objects.prefetch_related('car_set').get(id=1)

for  car in owner.car_set.all():
  print(car.name)
```

위에 코드는 `owner`라는 `Person`인스턴스 하나가 가진 `car`들의 이름을 전부 출력해주는 간단한 코드이다.

`prefetch_related`메서드는 위처럼 `1:N`의 관계의 1의 입장에서 쓰기 수월하다.

