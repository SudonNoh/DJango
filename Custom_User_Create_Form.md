# Custom User Create Form

<b>1. account/models.py 파일에서 custom한 user 모델 필드 변경</b>

```python
# account/models.py

from django.db import models
from django.contrib.auth.models import AbstractUser
from django.contrib.auth.models import User


# Create your models here.

class customUser(AbstractUser):

    username = models.CharField('ID', max_length=5, primary_key=True)
    team = models.CharField('Team', max_length=20)
    email = models.EmailField()
    first_name = models.CharField('Name', max_length=10)
    last_name = models.CharField('Comment', max_length=10, blank=True)
```
  
  
<b>2. form 작성</b>

```python
# settings.py과 같이 있는 곳의 forms.py

from django import forms
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth import get_user_model



class CustomUserCreationForm(UserCreationForm):

    # 입력 받을 값들을 위한 폼 생성
    username = forms.CharField(label='ID', max_length=5)
    password1 = forms.CharField(label='PW')
    password2 = forms.CharField(label='Check PW')
    first_name = forms.CharField(label='Name')
    email = forms.EmailField(label='Email')
    team = forms.CharField(label='Team')


    class Meta(UserCreationForm):
        model = get_user_model()
        # custom 한 필드를 추가해주어야 함
        # UserCreationForm의 기본 세팅은 username, password1, password2 임
        # 이 세팅을 안해주면 유저 등록을 했을 때 해당 테이블에 입력되지 않음
        fields = UserCreationForm.Meta.fields + ('team', 'email', 'first_name',)
```
