<h1>Input 요소</h1>
<h2>HTML에서 추가된 다양한 타입의 input 요소</h2>
<p>HTML5에서 새롭게 추가된 다양한 타입의 input 요소는 다음과 같음</p>

<li>datalist 요소</li>
<li>keygen 요소</li>
<li>output 요소</li>

<h2>datalist 요소</h2>
<p>
  datalist 요소는 input 요소에 대해 미리 정의된 옵션 리스트를 명시해 주는 요소<br>
  사용자는 텍스트를 바로 입력해도 되고, 드롭다운 메뉴에서 미리 정의한 옵션 중의 하나를 골라도 됨<br><br>
  단, input 요소의 list 속성값이 datalist 요소의 id 속성값과 반드시 일치해야 연결됨
</p>
  
```html
<form action="/examples/media/request.php">
    <input list="lectures" name="lecture">
        <datalist id="lectures">
            <option value="HTML">
            <option value="CSS">
            <option value="JAVA">
            <option value="C++">
        </datalist>
    <input type="submit" value="전송">
</form>
```

<h2>keygen 요소</h2>
<p>
  keygen 요소의 목적은 사용자가 인증할 수 있는 안전한 방법을 제공하는 것<br><br>
  
  keygen 요소는 사용자가 입력한 데이터를 암호화하여 서버로 전송<br>
  이때 생성된 키(key)를 가지고 서버는 해당 사용자의 인증을 수행  
</p>
  
```html
<form action="/examples/media/request.php">
    사용자 : <br>
    <input type="text" name="username"><br>
    암호화방법 : <br>
    <keygen name="security"><br>
</form>
```

<h2>output 요소</h2>
<p>
  output 요소는 스크립트(script) 등으로 실행된 계산의 결과를 바로 표시해주는 요소<br><br> 
</p>
  
```html
<form action="/examples/media/request.php"
    oninput="total.value=parseInt(value01.value)/parseInt(value02.value)">
    <input type="number" id="value01" name="input01" value="20">
    /
    (0
    <input type="range" id="value02" name="input02" value="50" min="0" max="100">
    100 )= <output name="total" for="value01 value02"></output><br><br>
</form>
```
