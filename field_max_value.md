<h1>테이블의 한 열에서 조건에 맞는 값들 중 최대 값을 구하는 방법</h1>

<p>
  <b>A_table</b> (검색하고자 하는 Model)<br><br>
  조건 : <b>date</b> 열에서 입력받은 <b>input_date</b> 와 동일한 값<br>
  출력 : 위의 조건을 만족하는 <b>count</b>열의 최대값 +1<br>
</p>
  
```python
from django.db.models import Max

row_list = A_table.objects.filter(date=input_date)
output_count = row_list.aggregate(Max('count'))['count__max']
```
