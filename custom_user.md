## AbstractUser를 이용한 Custom User Field 확장 방법
   
다른 여러 블로그 등을 찾아보았지만 장고를 이제 막 시작한 나한테는 설명을 이해하기가 쉽지 않았다.   
아래 내용은 장고의 User 모델을 사용하면서 User Field 확장을 쉽게 하는 법을 설명한다.
해당 내용은 장고의 공식 문서를 참고해서 작성하였다.
조건은 현재 CreateView를 통해 UserCreateView를 생성했다는 가정 하에 작성한다.
1) 새로운 app 생성
User의 Field를 관리할 앱을 생성한다.   
   
```python
python manage.py startapp account
```
2) models.py 작성  
User 필드에 추가할 내용을 작성한다.
   
```python
from django.db import models
from django.contrib.auth.models import AbstractUser

class User(AbstractUser):

  A = models.CharField(max_length=10)
  B = models.CharField(max_length=5)

```
3) admin.py 작성  
관리자 페이지에서 확인할 내용들을 작성한다.
```python
from django.contrib import admin
from .models import User

@admin.register(User)
class UserAdmin(admin.ModelAdmin):

  # username 은 장고에서 제공하는 User 모델의 필드 내에 있는 컬럼명
  # 관리자 페이지에서 리스트를 보여줄 때 열로 활용
  list_display = ('username', 'email', 'A', 'B')
  list_filter = ('username',)
```
4) forms.py 작성  
settings.py 파일이 있는 폴더에 forms.py 파일을 만들어 내용을 작성한다.

```python
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth import get_user_model

# UserCreationForm 을 상속받아 user 를 생성할 때 사용하는 모델을 바꿔준다.
class CustomUserCreationForm(UserCreationForm):

    class Meta(UserCreationForm):
        ~~models = get_user_model()~~
        model = get_user_model()
        fields = UserCreationForm.Meta.fields
```
5) views.py  
settings.py 파일이 있는 폴더에 views.py 파일을 만들어 내용을 작성한다.
   
```python
from .forms import CustomUserCreationForm

class UserCreateView(CreateView):
  form_class = CustomUserCreationForm
```
6) settings.py  
몇 가지 옵션을 추가한다.
   
```python
INSTALLED_APPS = [
    # 생략
    
    'account.apps.AcountConfig' # 추가
    ]
    
AUTH_USER_MODEL='account.User'
```
끝.
