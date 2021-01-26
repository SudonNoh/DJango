### "a href" 를 활용한 Template 이동

button에 onclick으로 href를 넣는 방법 등을 우선적으로 활용해보았으나,  
알아본 결과 button 에 onclick 으로 넣어서 사용하는 것은 추천하지 않는다고 한다.  
Bootstrap 에서도 a 태그를 활용한 방법을 설명하고 있다.

```html
<a href="#" class="btn btn-primary btn-lg disabled" tabindex="-1" role="button" aria-disabled="true">Primary link</a>
<a href="#" class="btn btn-secondary btn-lg disabled" tabindex="-1" role="button" aria-disabled="true">Link</a>
```

1) View 작성
  ```python
  import django.views.generic import TemplateView
  import django.shortcuts import render
  
  
  class PurchaseView(TemplateView):
  
      # html의 위치를 을 입력한다. 이 부분은 template 를 지정하기 위함이며 render와 크게 관련이 없다.
      template_name = 'purchase_template.html'
      
      
      def purchase_render(request):
      
          # 'purchase_template.html'은 purhcase_render가 실행되었을 때 불러올 html 을 입력한다.
          return render(request, 'purchase_template.html')
   ```
  
  
  
2) url 작성
  ```python
  import .views import PurchaseView
  
  urlpatterns = [
  
      # path의 두번째 인수인 PurchaseView.purchase_render 는 view에 있는 purchase_render 함수를 불러온다.
      # name은 템플릿 작성시 url을 호출할 때 사용할 이름이다.
      path('purchase/', PurchaseView.purchase_render, name='purchase')
      
      ]
  ```
  
  
3) 템플릿 작성

  ```html
  <a href="{% url 'purchase' %}" class="btn-1" type="button">Purchase</a>
  
  <!-- 추가적으로 다른 앱에 있는 html 을 불러오고 싶을 경우 -->
  <a href="{% url 'appname:name' %}" class="btn-1" type="button">Purchase</a>
  ```
