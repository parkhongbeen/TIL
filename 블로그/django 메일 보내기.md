# Django mail 보내기

개인이나 기업이 SMTP서버를 설치해서 이를 통해 메일을 발송할 수 있습니다.

하지만 요즘은 구글, 마이크로소프트 등의 기업에서 SMTP 서버를 오픈하기 때문에 이를 통해서 메일을 전송할 수 있습니다. 오늘은 GMail의 SMTP 서버를 이용해서 메일을 전송해보겠습니다.

<!-- more -->

## GMail SMTP서버

Gmail의 SMTP서버를 사용하기 위해 설정을 해야합니다.

- [다른 이메일 크라이언트에서 GMail을 확인할 수 있도록 IMAP 사용 설정](https://support.google.com/mail/answer/7126229?hl=ko&rd=3&visit_id=1-636281811566888160-3239280507#ts=1665018)
- [보안 수준이 낮은 앱 및 Google 계정 허용](https://myaccount.google.com/lesssecureapps?pli=1)(이 설정을 하지 않으면 계정이 틀렸다고 나옵니다.)

두가지 설정을 마치게 되면 SMTP 서버를 이용할 수 있습니다.(주의: 해당 계정의 비밀번호가 유출되지 않도록 잘 관리해주셔야 합니다.)

## Django 설정

```python
settings.py

EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = "smtp.gmail.com"
EMAIL_HOST_USER = 'user-ID@gmail.com'
EMAIL_HOST_PASSWORD = 'user-PW'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
DEFAULT_FROM_EMAIL = EMAIL_HOST_USER
```

- EMAIL_BACKEND: 메일을 전송에 쓰는 백엔드 설정
- EMAIL_PORT: 587포트는 Gmail의 권장 사항
- EMAIL_USE_TLS: TLS(Transport Layer Sercurity)는 통신 내용을 암호화하는 통신 규약이다.

## Django 메일 송신

django에서는 pythond의 내장 모듈인 stmplib를 통해 메일을 방송합니다.

### Basic 메일 전송

```python
from django.core.mail import send_mail

send_mail(
    'Subject here',         # 제목
    'Here is the message.', # 내용
    'from@example.com',     # 보내는 이메일  (settings에 설정했다면 작성하지 않아도 됩니다.)
    ['to@example.com'],     # 받는 이메일 리스트
    fail_silently=False,    # send_mail에서 오류가 발생하면 smtplib.SMTPException을 발생시킵니다.
)
```

### EmailMessage 클래스

```python
from django.core.mail import EmailMessage

email = EmailMessage(
    'Hello',                # 메일 제목
    'Body goes here',       # 내용
    'from@example.com',     # 보내는 이메일 (settings에 설정했다면 작성하지 않아도 됩니다.)
    to=['to1@example.com', 'to2@example.com'],  # 받는 이메일 리스트
)
```



참고글: [공식문서](https://docs.djangoproject.com/en/3.0/topics/email/), [블로그](https://velog.io/@ground4ekd/django-send-mail)