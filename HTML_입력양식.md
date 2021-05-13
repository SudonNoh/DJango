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
  
<h2>Input 요소의 속성</h2>
<p>input 요소의 여러 속성을 사용하면 사용자가 입력하는 방식을 더욱 다양하게 제어할 수 있음</p>
