<h1>HTML 입력양식</h1>
<h2>Form 요소</h2>

<p>
  웹 페이지에서는 form요소를 사용하여 사용자로부터 입력을 받을 수 있음<br>
  또한, 사용자가 입력한 데이터를 서버로 보낼 때에도 form요소를 사용<br><br>
  문법: <i>&lt;form action="처리할 페이지 주소" method="get|post"&gt;&lt;/form&gt;</i><br>
  <ul>
    <li>
      action: 입력받은 데이터를 처리할 서버 상의 스크립트 파일의 주소를 명시<br>
      (이렇게 전달 받은 데이터를 처리하는 스크립트 파일을 폼 핸들러(form-handler)라고 함)
    </li>
    <li>method: 입력받은 데이터를 서버에 전달할 방식을 명시</li>
  </ul>
</p>
<blockquote>
  <h3>method 속성</h3>
  <p>
    method 속성을 통해 명시할 수 있는 form 요소의 전달 방식은 GET방식과 POST방식으로 나뉨<br>
    <h4>GET 방식</h4>
    <p> 
      주소에 데이터(data)를 추가하여 전달하는 방식<br>
      데이터가 주소 입력창에 그대로 나타남<br>
      전송할 수 있는 크기 또한 제한적임<br>
      따라서 검색 엔진의 쿼리(query)와 같이 크기가 작고 중요도가 낮은 정보를 보낼 때 주로 사용
    </p>
    <h4>POST 방식</h4>
    <p>
      데이터(data)를 별도로 첨부하여 전달하는 방식<br>
      데이터가 외부에 드러나지 않음<br>
      전송할 수 있는 데이터의 크기 또한 제한이 없음<br>
      보안성 및 활용성이 GET 방식보다 좋음<br>    
   </p>
</blockquote>

<h2>다양한 타입의 input 요소</h2>
<p>
  HTML에서는 다양한 타입의 input 요소를 사용해 사용자로부터 입력을 받을 수 있음<br>
  HTML에서 사용할 수 있는 대표적인 input 요소들
  
  <ul>
    <li>텍스트 입력(text)</li>
    <li>비밀번호 입력(password)</li>
    <li>라디오 버튼(radio)</li>
    <li>체크박스(checkbox)</li>
    <li>파일선택(file)</li>
    <li>선택 입력(select)</li>
    <li>문장 입력(textarea)</li>
    <li>버튼 입력(button)</li>
    <li>전송 버튼(submit)</li>
    <li>필드셋(fieldset)</li>
  </ul>
</p>
<blockquote>
  <h3>텍스트 입력</h3>
  <p>&lt;input&gt;태그의 type 속성값을 "text"로 설정하면, 사용자로부터 한 줄의 텍스트를 입력받을 수 있음</p>
  
  ```html
  <form action="/examples/media/request.php">
    검색할 내용을 입력하세요 :
    <input type="text" name="search">
  </form>
  ```
</blockquote>

<blockquote>
  <h3>비밀번호 입력</h3>
  <p>
    &lt;input&gt;태그의 type 속성값을 "password"로 설정하면, 사용자로부터 비밀번호를 입력받을 수 있음<br>
    비밀번호를 입력받기 때문에 화면에는 입력받은 문자나 숫자 대신 별표나 작은 원 모양이 표시
  </p>
  
  ```html
  <form>
    사용자: <br><input type="text" name="username"><br>
    비밀번호: <br><input type="password" name="password">
  </form>
  ```
</blockquote>

<blockquote>
  <h3>라디오 버튼</h3>
  <p>
    &lt;input&gt;태그의 type 속성값을 "radio"로 설정하면, 사용자로부터 여러 개의 옵션중에서 단 하나의 옵션만을 입력받을 수 있음<br>
    이때 서버로 정확한 입력을 전송하기 위해서는 반드시 모든 input 요소의 name 속성이 같아야 함
  </p>
  
  ```html
  <form>
    <input type="radio" name="lecture" value="html"> HTML <br>
    <input type="radio" name="lecture" value="css"> CSS <br>
    <input type="radio" name="lecture" value="java"> JAVA <br>
    <input type="radio" name="lecture" value="cpp"> C++ <br>
  </form>
  ```
  <i>정확한 입력값 전송을 위해서 radio 타입의 모든 input 요소가 반드시 같은 name 속성을 가지고 있어야 함</i>
  
</blockquote>

<blockquote>
  <h3>체크박스</h3>
  <p>
    &lt;input&gt;태그의 type 속성값을 "checkbox"로 설정하면, 사용자로부터 여러 개의 옵션중에서 다수의 옵션을 입력받을 수 있음<br>
    체크박스는 라디오 버튼과는 달리 여러 개의 옵션을 한 번에 입력받을 수 있음<br>
    이때 서버로 정확한 입력을 전송하기 위해서는 반드시 모든 input 요소의 name 속성이 같아야 함
  </p>
  
  ```html
  <form>
    <input type="checkbox" name="lecture" value="html" checked> HTML <br>
    <input type="checkbox" name="lecture" value="css"> CSS <br>
    <input type="checkbox" name="lecture" value="java"> JAVA <br>
    <input type="checkbox" name="lecture" value="cpp" disabled> C++
  </form>
  ```
</blockquote>
  
<blockquote>
  <h3>파일 선택</h3>
  <p>
    &lt;input&gt;태그의 type 속성값을 "file"로 설정하면, 사용자로부터 파일을 전송받을 수 있음
  </p>
  
  ```html
  <form>
    <input type="file" name="upload_file" accept="image/*">
  </form>
  ```
  <i>accept 속성을 이용해 입력받ㅇ르 수 있는 파일의 확장자 및 종류를 명시할 수 있음</i>
</blockquote>

<blockquote>
  <h3>선택 입력</h3>
  <p>
    select 요소는 여러 개의 옵션이 드롭다운 리스트(drop-down list)로 되어 있으며, 그중에서 단 하나의 옵션만을 입력받을 수 있음<br>
    option 요소는 드롭다운 리스트에서 선택할 수 있는 각각의 옵션을 명시함
  </p>
  
  ```html
  <select name="fruit">
    <option value="apple"> 사과
    <option value="orange" selected> 귤
    <option value="strawberry"> 딸기
    <option value="peach"> 복숭아
  </select>
  ```
</blockquote>
<blockquote>
  <h3>문장 입력</h3>
  
  ```html
  <textarea name="message" rows="5" cols="30">
    작성
  </textarea>
  ```
</blockquote>

<blockquote>
  <h3>버튼</h3>
  <p>
    button 요소는 사용자가 누를 수 있는 버튼을 나타냄
  </p>
   
  ```html
  <button type="button" onclick="alert('버튼을 클릭했군요!')">
    버튼을 눌러주세요.
  </button>
  ```
</blockquote> 

<blockquote>
  <h3>전송 버튼</h3>
  <p>
    &lt;input&gt;태그의 type 속성값을 "submit"으로 설정하면, <br>
    사용자로부터 입력받은 데이터(data)를 서버의 폼 핸들러로 제출하는 버튼을 만들 수 있음 <br>
    폼 핸들러(form-handler)란 입력받은 데이터를 처리하기 위한 서버 측의 웹 페이지를 의미 <br>
    이러한 폼 핸들러의 주소는 from 요소의 action 속성을 이용해 명시할 수 있음
  </p>
  
  ```html
  <form action="/examples/media/request.php">
    어릴 때 자신의 별명을 적어주세요 : <br>
    <input type="text" name="nickname" value="별명"><br><br>
    <input type="submit" value="전송">
  ```
   
</blockquote> 


<blockquote>
  <h3>필드셋(fieldset)</h3>
  <p>
    fieldset 요소는 form 요소와 관련된 데이터들을 하나로 묶어주는 역할을 함<br>
    legend 요소는 fieldset 요소 안에서만 사용할 수 있으며, fieldset 요소의 제목을 나타냄
  </p>
  
  ```html
  <form action="/examples/media/request.php">
    <fieldset>
      <legend>입력 양식</legend>
      이름: <br>
      <input type="text" name="username"><br>
      이메일: <br>
      <input type="text" name="email"><br><br>
      <input type="submit" value="전송">
    </fieldset>
  </form>
  ```
</blockquote> 
<i>HTML5 추가된 다양한 타입의 input 요소</i>

1. detalist 요소
2. keygen 요소
3. output요소

<h2>Input 요소의 속성</h2>
<p>input 요소의 여러 속성을 사용하면 사용자가 입력하는 방식을 더욱 다양하게 제어할 수 있음</p>
                                                       
