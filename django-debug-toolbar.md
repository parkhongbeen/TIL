## django-debug-toolbar

`<body>`태그가 있어야만 `django-debug-toolbar`가 작동합니다.

### 1. 설치

```
$ pip install django-debug-toolbar
```

### 2. 설정(settings.py)

- `django-debug-toolbar`는 주로 `middleware`에서 동작합니다.
- `django-debug-toolbar`를 이용하면 내부상황을 다 볼 수 있습니다.
- 따라서, 특정IP에서만 사용할 수 있도록 권한을 관리해 주어야 합니다.

```python
INSTALLED_APPS = [
    # ...
    'django.contrib.staticfiles',
    # ...
    'debug_toolbar',
]

STATIC_URL = '/static/'

MIDDLEWARE = [
    # ...
    'debug_toolbar.middleware.DebugToolbarMiddleware',
    # ...
]

# The Debug Toolbar is shown only if your IP is listed in the INTERNAL_IPS setting.
INTERNAL_IPS = ['127.0.0.1']
```

### 3. 프로젝트 레벨 URL설정(urls.py)

- 반드시 `settings.DEBUG = True`일 때만 사용하는 것을 추천합니다.

```python
if settings.DEBUG:
    import debug_toolbar
    urlpatterns = + [
        path('__debug__/', include(debug_toolbar.urls)),

        # For django versions before 2.0:
        # url(r'^__debug__/', include(debug_toolbar.urls)),

    ]
```

### 4. django-debug-toolbar실행

- 