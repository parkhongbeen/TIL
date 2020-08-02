## Celery

- 비동기 작업 대기열
- 비동기적으로 실행해야 하는 모든 것에 사용 가능

## RabbitMQ

- Celery와 함께 사용하는 메시지 브로커
- Redis도 사용할 수 있지만 celery공식문서에서는 rabbitmq를 추천

### Broker

- Broker(RabbitMQ)는 작업 큐 생성, 일부 라우팅 규칙에 따라 작업 큐에 작업발송, 작업 큐에서 worker로 작업 전달을 담당합니다.
- 브로커가 필요한 이유는 Celery는 실제로 메시지 큐 자체를 구성하는 것은 아니기 때문에 이 작업을 수행하려면 추가 메시지 전송(Broker)이 필요합니다. Celery는 메시지 브로커를 감싸는 래퍼로 생각할 수 있습니다.
- 실제로 RabbitMQ, Redis 또는 DB(Django 데이터베이스)와 같은 몇 가지 브로커 중에서 선택할 수 있습니다.

### Consumer(Celery worker)

작업을 수행하는 하나 이상의 Celery Worker이니다. UseCase에 따라 많은 worker를 시작할 수 있습니다.

### Result BackEnd

작업 결과를 저장하는데 사용합니다. 필수요소는 아니기 때문에 설정에 포함시키지 않으며, 작업 결과에 액세스 할 수 없습니다.

### Install Celery

가상환경에서 `celery`를 설치해보겠습니다.

```
$ pip install celery
```

### Install RabbitMq

```
$ brew install rabbitmq
```

