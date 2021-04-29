## 자동완성 끄기
```html
# templates.py

<form autocomplete="off">
</form>

```

## session logout
```python
# settings.py

# SESSION LOGOUT SETTING
# BROWSER를 닫으면 SESSION 만료, 로그아웃
SESSION_EXPIRE_AT_BROWSER_CLOSE = True

# 60초 X 15 = 15분동안 동작(입력, 삭제, 수정)이 없으면 자동 로그아웃
SESSION_COOKIE_AGE = 60*15

# 이 부분을 켜놓으면 입력, 삭제, 수정이 없더라도 동작할 때 SESSION 저장
# SESSION_SAVE_EVERY_REQUEST = True
```
