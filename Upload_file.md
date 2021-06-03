<h1>Upload file</h1>

<h2>1. 모델없이 업로드하는 방법</h2>
<p>
  간단한 방법으로 하나의 파일을 업로드 할 때 사용한다.
  urls 파일은 간단히 view를 실행시킬 수 있을 정도만 설정해준다.
</p>

<blockquote>
  <h3>1. template</h3>

  ```html
  <h1>Save File</h1>

  <form method="post" enctype="multipart/form-data">
      {% csrf_token %}
      <input type="file" name="myfile" accept=".ab1">
      <button type="submit">Upload</button>
  </form>
  ```
  <p>
    <b>enctype="multipart/form-data"</b> : 이 의미는 form에서 받는 모든 정보를 모두 인코딩하지는 않는다는 뜻<br>
    &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
    &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
    &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp만약 이 부분을 설정하지 않는다면 form 에서 filename 정도만 받아오게 됨<br>
    <b>accept=""</b> : "" 한에 파일 확장자가 들어간다. 이 부분을 설정하면 해당 확장자만 보여지게 됨<br>
    <b>name='myfile'</b> : 입력받은 파일을 myfile 이란 이름으로 view에 넘겨줌
  </p>
</blockquote>
<blockquote>
  <h3>2. view</h3>
  
<h3> views 전체 코드</h3>

```python
    
def simple_upload(request):
    if request.method == 'POST' and request.FILES['myfile']:
        myfile = request.FILES['myfile']
        fs = FileSystemStorage(location='media/screening_ab1', base_url='media/screening_ab1')
        FileSystemStorage.save(file_name, file_content)
        filename = fs.save(myfile.name, myfile)
        uploaded_file_url = fs.url(filename)
        return render(request, 'screening_analysis/analysis_ab1_reader.html', {
            'uploaded_file_url': uploaded_file_url
        })
    return render(request, 'screening_analysis/analysis_ab1_reader.html')
```  
  
  
  <h4>1) myfile 에 request 받은 file을 저장</h4>
  
  ```python
  def simple_upload(request):
    if request.method == 'POST' and requsest.FILES['myfile']:
        myfile = request.FILES['myfile']
  ```
  
  <h4>2) FileSystemStorage 설정</h4>
  <p>
    location : 파일을 저장할 곳<br>
    base_url : 파일을 불러올 때 불러오는 곳
  </p>
  
  ```python
        fs = FileSystemStorage(location='media/screening_ab1', base_url='media/screening_ab1')
  
  ```
  
  <h4>3) 파일을 경로에 저장</h4>

 <p>
    FileSystemStorage.save(file_name, file_content)
 </p>
     
  
   ```python
        filename = fs.save(myfile.name, myfile)
   ```
  
  <h4>4) 파일이 저장된 URL을 반환</h4>
    
  
```pyhton
    uploaded_file_url = fs.url(filename)
```

  
<h4>5) return render</h4>
<p>
  uploaded_file_url 로 업로드된 파일의 local 주소를 알 수 있음</p>

```python
    return render(request, 'screenging_analysis/analysis_ab1_reader.html',{
        `uploaded_file_url': uploaded_file_url'

    })
  return render(request, 'screenging_analysis/analysis_ab1_reader.html')

```
  
      
<h4>그 밖에 검색할 수 있는 내용</h4>  

```python

    print('myfile read:', myfile.read()) # file 읽기
    print('myfile size:', myfile.size) # file 읽기
    print('myfile content_type:', myfile.content_type)
    print('myfile open:', myfile.open())
    myfile_read = myfile.read()
    print('myfile read type:', type(myfile_read))

    from .module import ab1_file_controller

    ab1_control = ab1_file_controller()
    seq = ab1_control.ab1_seq
    print(seq(uploaded_file_url))
```
</blcokquote>
