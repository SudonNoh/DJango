<h1>Django 에서 Group by 사용 방법</h1>

<p>
  Python shell 을 실행하고, Queryset 작성
</p>

```python
# python shell 실행
>>> python manage.py shell

# Count 함수 import (Sum, Count, Max, Min, Avg 등등)
>>> from django.db.models import Count

# "screening_ab1_database" 테이블에서 "status" 필드가 "PASS"인 값들 "group" 수 확인
>>> screening_ab1_database.filter(status="PASS").values('group', 'date', 'tar_id', 'user', 'stuats').annotate(Count('group'))
```
