# Member

## User-signup

### POST /v1/members/signup/

- request body

```json
{
    "email": "",
    "name": "",
    "password1": "123",
    "password2": ""
}
```

- response (성공시) 
  - status : 200

```json
{
    "id": 9,
    "name": "hbyyy",
    "email": "lloasd33@naver.com"
}
```

- response (실패시)
  - status : 400

```json
{
    "email": [
        "사용자의 email은/는 이미 존재합니다."
    ],
    "status": 400,
    "code": "invalid"
}
```



## Social-User-Signup

### POST /v1/members/signup/social/

- request body

```json
{
    "id_token": ""
}
```

- response (성공시)
  - status : 200

```json
{
    "name": "허범영",
    "email": "qjaduddl94@gmail.com"
}
```



- response (실패시)
  - status : 400

```json
{
    "token": "token이 유효하지 않습니다",
    "status": 400,
    "code": "invalid"
}

or


{
    "email": [
        "사용자의 email은/는 이미 존재합니다."
    ],
    "status": 400,
    "code": "invalid"
}

```



## User-token-get

### POST /v1/members/token/

- request body

```json
{
    "email":"",
    "password":""
}

or

{
    "id_token": ""
}
```

- response (성공시)
  - statue : 200

```json
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTk2NTE2MTE1LCJqdGkiOiI0MWZiZGMzYjI0YmI0Mjk3OWMyYjEwODEzNDMwNDIwOCIsInVzZXJfaWQiOjEwfQ.0FQCglnTtmJJerdiY25DGLhLR_0D6FId2erxVz7XJac",
    "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU5NjYwMjIxNSwianRpIjoiNjZkMDUyNDNmMTM4NDRjZThmZGQwMDExOWIwZTYwM2QiLCJ1c2VyX2lkIjoxMH0.W7AJGNtwRFV4p_eysJqms0sffHB_qbam1juJv-YavtI",
    "user": {
        "id": 10,
        "email": "qjaduddl94@gmail.com",
        "name": "허범영",
        "phone_number": null
    }
}
```

- response(실패시)
  - status: 400

```json
{
    "token": "token이 유효하지 않습니다",
    "status": 400,
    "code": "invalid"
}

or

{
    "user": [
        "없는 user입니다"
    ],
    "status": 400,
    "code": "invalid"
}
```



## User-token-refresh

### POST /v1/members/token/refresh/

- request body

```json
{
    "refresh:""
}
```

- response (성공시)
  - statue : 200

```json
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTk2NTE2MTE1LCJqdGkiOiI0MWZiZGMzYjI0YmI0Mjk3OWMyYjEwODEzNDMwNDIwOCIsInVzZXJfaWQiOjEwfQ.0FQCglnTtmJJerdiY25DGLhLR_0D6FId2erxVz7XJac"
}
```

- response(실패시)
  - status: 401 Unauthorized

```json
{
    "detail": "Token is invalid or expired",
    "code": "token_not_valid",
    "status": 401
}
```

## 

