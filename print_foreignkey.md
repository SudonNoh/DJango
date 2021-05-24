<h1>Foreign Key를 이용해 정보 가져오는 방법</h1>
<p>
  item 테이블에 있는 외래키를 이용해 vendor 의 정보를 가져오는 방법<br><br>
  template에서 print 하는 방법
</p>

<h2>1. Model 구성</h2>
<p>
  모델은 판매자 정보를 가지고 있는 vendr 와 물품의 정보를 가지고 있는 item 으로 구성
</p>

```python
# models.py
from django.db import models


class vendor(models.Model):
    
    ven_id = models.AutoField('Vendor ID', primary_key=True)
    ven_name = models.CharField('Vendor Name', max_length=50, unique=True)
    

class item(models.Model):

    it_id = models.AutoField('Item ID', primary_key=True)
    ven_id = models.ForeignKey('Vendor_info', related_name='vendor_id', on_delete=models.PROTECT, db_column='ven_id')
    order = models.BooleanField(default=True)
    
```

<h2>2. View 구성</h2>
<p>
  object_list에 ordered_item을 저장
</p>

```python
# views.py
from .models import vendor, item
from django.db.models import Q
from django.shortcuts import render

class order_dv(ListView):

    model = item
    template_name = 'templates/template_dv.html'
    
    def get(self, request, *args, **kwargs):
        
      ordered_item = item.objects.all()
      context['object_list'] = ordered_item
      
      return render(request, self.temlate_name, context)
```

<h2>3. HTML 구성</h2>
<p>
  아래서 valye.ven_id.ven_name을 해야 ven_id를 타고가서 ven_name을 검색할 수 있음<br>
  또한 value.ven_id.ven_id를 해주는 이유는 value.ven_id 만 작성할 경우 "vendor object(1)"과 같은 형태로 나타남
</p>

```html
<!-- template_dv.html -->

{% for value in object_list %}

  {{ value.it_id }}
  {{ value.ven_id.ven_id }}
  {{ value.ven_id.ven_name }}
  {{ value.price }}

{% endfor %}
```
