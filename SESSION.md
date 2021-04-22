## Django 에서 세션 유지시간 설정하기

settings.py

1. 세션의 시간을 시간을 조정하고 싶은 경우
    - 브라우저가 닫힐 때 초기화 하고 싶은 경우: <b>SESSION_EXPIRE_AT_BROWSER_CLOSE = True</b> (default는 False)
    - 직접 시간을 정하고 싶은 경우
        - 데이터의 수정/삭제가 있는 경우: <b>SESSION_COOKIE_AGE = 43200</b> (초 단위: 60 * 60 * 12 의 형태(초 * 분 * 시간)로 가능)
        - 데이터의 수정/삭제가 없이 사이트의 요청만으로 유지시간이 갱신되는 경우: <b>SESSION_SAVE_EVERY_REQUEST</b> (default는 False)

2. 세션의 시간을 영구적으로 유지하고 싶은 경우
    - 설정을 하지 않는 경우 2주간 세션이 유지 된다.
