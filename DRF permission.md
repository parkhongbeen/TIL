## permission

> 인증이나 식별  그 자체만으로는 정보나 코드에 액세스하기에 충분하지 않습니다.이를 위해서는 액세스를 요청하는 권한이 있어야 합니다.

권한은 인증 및 제한과 함꼐 요청에 액세스 권한을 부여할지 거부할지를 결정합니다.가장 간단한 권한 스타일은 인증 된 사용자에 대한 액세스를 허용하고 인증되지 않은 사용자에 대한 액세스를 거부하는 것입니다. REST 프레임 워크의 IsAuthenicated 클래스에 해당합니다.

조금 더 권한을 준다면 IsAuthenticatedOrReadOnly 클래스에 해당합니다. 인증 된 사용제에게 전체 액세스를 허용하지만 인증되지 않은 사용자에게는 읽기 전용 액세스를 허용하는 것입니다.

### 권한 결정 방법

----

Rest프레임워크의 권한은 항상 권한 클래스목록으로 정의됩니다.

권한 검사에 실패하면 예외가 발생합니다.PermissionDenied 또는 exceptions.NotAuthenticated 예외가 발생하고 보기의 본문이 실행되지 않습니다.

### 권한 설정

---

`DEFAULT_PERMISSION_CLASSES` 설정을 사용하여 전체적으로 설정할 수 있습니다.

```python
#setting.py/
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
    'rest_framework.permissions.IsAuthenticated',
    ]
}
```

지정하지 않으면 설정은 기본적으로 무제한 액세스를 허용합니다.

```python
'DEFAULT_PERMISSION_CLASSES': [
   'rest_framework.permissions.AllowAny',
]
```

**Note**: 클래스속성 또는 데코레이터를 통해 새 권한 클래스를 설정하면 settings.py 파일에 설정된 기본 목록을 무시하도록 뷰에 지시합니다.

### API 참조

----

#### AllowAny

AllowAny 권한 클래스는 **요청의 인증 여부에 관계없이** 무제한 액세스를 허용합니다. 권한 설정에 빈 목록이나 튜플을 사용하여 동일한 결과를 얻을 수 있기 때문에 이 권한은 꼭 필요한 것은 아니지만 의도를 명시적으로 나타내기 때문에 이 클래스를 지정하면 유용할 수 있습니다.

#### IsAuthenticated

IsAuthenticated 권한 클래스는 인증되지 않은 사용자에 대한 권한을 거부하고 그렇지 않으면 권한을 허용합니다. 이 권한은 등록 된 사용자만 API에 액세스할 수 있도록 하려는 경우에 적합합니다.

#### IsAdminUser

IsAdminUser 권한 클래스는 user.is_staff가 True 인 경우 권한이 허용되지 않는 한 모든 사용자에 대한 권한을 거부합니다.

#### IsAuthenticatedOrReadOnly

IsAuthenticatedOrReadOnly는 인증 된 사용자가 모든 요청을 수행 할 수 있도록합니다. 승인되지 않은 사용자에 대한 요청은 요청 방법이 "안전한"방법 중 하나 인 경우에만 허용됩니다. 이 권한은 이경 사용자에게 읽기 권한을 허용하고 인증 된 사용자에게 쓰기 권한만 허용하도록 API에 원하는 경우에 적합합니다.

#### DjangoModelPermissions

이 권한 클래스는 Django의 표준 django.contrib.auth 모델 권한과 연결됩니다. 이 권한은 .queryset 속성이 설정된 뷰에만 적용해야합니다. 인증은 사용자가 인증되고 관련 모델 권한이 할당 된 경우에만 부여됩니다.

```python
# ex
from rest_framework.permissions import IsAuthenticated
from rest_framework.permissions import Response
from rest_framework.permissions import APIView

class ExampleView(AIPView):
  permission_classes = [IsAuthenticated]
  
  def get(self, request, fromat=None):
    content = {
      'status': 'request was permitted'
    }
    return Response(content)
```

