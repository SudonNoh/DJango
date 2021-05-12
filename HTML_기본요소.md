<h1>HTML 공부 2</h1>

<p> 이 부분에서는 html 에서 style 및 링크, 이미지 등 tag 에 들어가는 속성 설정을 배운다.<p>
  
<hr>
<blockquote>
  <h2>HTML 스타일(Style)</h2>
  <p>HTML 요소의 style 속성을 이용하면 CSS 스타일을 HTML 요소에 직접 설정 가능.<br>
    하지만 이러한 style 속성을 이용한 방법은 오직 하나의 HTML 요소에만 스타일을 적용.</p>

  ```html
  <!-- 문법 -->
  <태그이름 style="속성이름:속성값">
  ```

  <hr>
  <h3>배경색 변경</h3>

  ```html
  <!-- 배경색 -->
  <h1 style="background-color:white">
    style 속성을 이용한 배경색 변경
  </h1>
  ```

  <hr>
  <h3>글자색 변경</h3>

  ```html
  <!-- 글자색 -->
  <h1 style="color:maroon">
    style 속성을 이용한 글자색 변경
  </h1>
  ```

  <hr>
  <h3>글자 크기 변경</h3>

  ```html
  <!-- 글자 크기 변경 -->
  <h1 style="font-size:250%">
    style 속성을 이용한 글자 크기 변경
  </h1>
  ```

  <hr>
  <h3>문단 정렬 변경</h3>

  ```html
  <!-- 문단 정렬 변경 -->
  <h1 style="text-align:center">
    style 속성을 이용한 문단 정렬 변경
  </h1>
  ```

  <hr>
  <h3>여러 스타일 설정</h3>
  <p>         style 속성값에 사용되는 CSS 속성과 속성값들은 세미콜론(;)을 이용하여 구분 <br>
          CSS 속성을 하나만 사용할 때나, 여러 개의 CSS 속성 중 맨 마지막 CSS 속성은 세미콜론(;)을 생략할 수 있음</p>

  ```html
  <!-- 여러 스타일 설정 -->
  <h1 style="background-color:white; color:maroon; font-size:150%; text-align:center">
    style 속성을 이용하여 한 번에 스타일링 하기
  </h1>
  ```
</blockquote>

<hr>
  <blockquote>
  <h2>HTML 배경(Background)</h2>
  <p>
    HTML 문서의 기본 배경은 흰색<br>
    또한, HTML 요소들도 각자 자신만의 배경을 가지고 있음<br>
    <br>
    HTML에서는 이러한 배경을 다음과 같이 변경할 수 있음
    <br>
    <br>
    1. 배경을 다른 색으로 변경<br>
    2. 배경을 다른 이미지로 변경
  </p>

  <h3> 배경을 다른 색으로 변경</h3>
  <p> HTML5 이전까지는 bgcolor 속성을 이용해 HTML 요소의 배경색을 다른 색으로 변경할 수 있었음<br>
    하지만 HTML5 부터는 bgcolor 속성을 더이상 지원하지 않고, CSS를 이용해 배경색을 변경하도록 하고 있음</p>

  ```html
  <style>
    body { background-color:lightblue; }
    h1 { background-color:red; }
    p { background-color:yellow; }
  </style>
  ```

  <h3> 배경을 다른 이미지로 변경</h3>
  <p>
  &nbsp;&nbsp;&nbsp;&nbsp;문법
  &nbsp;&nbsp;<태그이름 background="이미지 주소">
  </p>

  ```html
  <body background="/examples/images/background.png">
    ...
  </body>
  ```

  <hr>
  <h2> HTML 링크(link)</h2>

  ```html
  <!-- a 태그 -->
  <a href="/html/intro">
    <h2>이 링크를 클릭하세요</h2>
  </a>
  ```

  <h3> target 속성</h3>
  <p>&lt;a&gt;태그의 target 속성은 링크로 연결된 문서를 어디에서 열지를 명시합니다.<br>
  <br>
  _blank:링크로 연결된 문서를 새 창이나 새 탭에서 오픈<br>
  _self:링크로 연결된 문서를 현재 프레임(frame)에서 오픈(기본 설정)<br>
  _parent:링크로 연결된 문서를 부모 프레임(frame)에서 오픈<br>
  _top:링크로 연결된 문서를 현재 창의 가장 상위 프레임(frame)에서 오픈<br>
  프레임(frame) 이름: 링크로 연결된 문서를 지정된 프레임(frame)에서 오픈</p>

  ```html
  <h2><a href="/html/intro" target="_blank">blank</a></h2>
  <h2><a href="/html/intro" target="_self">self</a></h2>
  <h2><a href="/html/intro" target="_parent">parent</a></h2>
  <h2><a href="/html/intro" target="_top">top</a></h2>
  <h2><a href="/html/intro" target="myframe">myframe</a></h2>

  <iframe name="myframe" style="width:50%; height: 330px"></iframe>
  ```

  <h3> 링크의 상태 </h3>
  <p> HTML 링크의 상태는 다음과 같이 네 가지로 구분할 수 있음<br><br>
    link: 아직 한 번도 방문한 적이 없는 상태 (기본 설정)<br>
    visited: 한 번이라도 방문한 적이 있는 상태<br>
    hover: 링크 위에 마우스를 올려놓은 상태<br>
    active: 링크를 마우스로 누르고 있는 상태<br>

    text-decoration 속성을 none 으로 설정시 밑줄이 없는 상태로 나타남
  </p>

  ```html
  <style>
    a:link { color: teal; text-decoration: none }
    a:visited { color: maroon; text-decoration: none }
    a:hover { color: yellow; text-decoration: none }
    a:active { color: red; text-decoration: none }
  </style>
  ```

  <h3> 페이지 책갈피 </h3>
  <p> &lt;a&gt;태그의 name 속성을 이용하면 간단한 책갈피를 만들 수 있음.<br>
    우선 책갈피를 통해 가고 싶은 위치에 &lt;a&gt;태그를 만들고 name 속성을 작성한다.<br>
    그 다음에 작서한 name 속성값을 이용하여 다른 &lt;a&gt;태그에서 링크를 걸면 된다.
  </p>

  ```html
  <a href="#bookmark"><p>제목 3으로 이동</p></a>
  ...
  <h2><a name="bookmark"></a>제목 3</h2>
  ```
</blockquote>

<hr>
  <blockquote>
  <h2>HTML 이미지</h2>

  <h3>이미지 삽입</h3>
  <p> 
    문법&nbsp;&nbsp;&lt;img src="이미지 주소" alt="대체문자열"&gt;<br>
    src 속성은 이미지가 저장된 주소의 URL 주소를 명시
    alt 속성으로 이미지가 로딩될 수 없는 상황에서 이미지 대신 나타날 문자열을 설저할 수 있음
  </p>

  ```html
  <!-- 이미지 삽입 -->
  <img src="/img_html5_logo.png" alt="이미지가 없습니다.">
  ```

  <h3>이미지 크기 설정</h3>
  <p>
    HTML 에서는 style 속성으로 이미지의 크기를 설정할 수 있음<br>
    또한, width와 height 속성을 이용하면, 이미지의 너비와 높이를 각각 픽셀(pixel) 단위로 설정할 수 있음<br><br>
    위의 두 가지 방법 모두 HTML 표준에는 적합한 방법이지만, 나중에 배우게 될 CSS를 이용한 내부 스타일 시트나 외부 스타일 시트와 상관없이 이미지의 원래 크기를 유지하려면 style 속성을 사용하는 것이 좋음
  </p>

  ```html
  <style>
    img {
      width: 100%
      border: 1px solid black;
    }
  </style>

  <img src="/examples/images/img_flag.png" alt="html size" width="320" height="214">
  <img src="/examples/images/img_flag.png" alt="style size" style="width:320px; height:214px">
  ```

  <h3>이미지의 테두리(border) 설정</h3>

  ```html
  <img src="/examples/images/img_flag.png" alt="이미지 테두리" 
       style="width:320px; height:214px; border:3px solid black"
  ```

  <h3>이미지에 링크 설정</h3>

  ```html
  <a href="/html/into" target="_blank">
    <img src="/examples/images/img_flag.png" alt="flag" style="width:320px; height:214:px">
  </a>
  ```

  <h3>이미지맵 만들기</h3>
  <p>이미지 맵(image map): 이미지의 일부를 클릭할 수 있도록 만들어서 버튼처럼 사용하는 기능을 의미함<br><br>
    &lt;img&gt;태그의 usemap 속성을 &lt;map&gt;태그의 name 속성과 연결하면 이미지와 맵 사이의 관계가 설정됨<br>
    &lt;map&gt;태그는 하나 이상의 &lt;area&gt;태그를 가지며, 이 &lt;area&gt;태그가 바로 버튼과 같은 역할을 함</p>

  ```html
  <img src="/examples/images/img_flag.png" alt="진실혹은거짓" usemap="#vending" style="width:320px; height:240px" />
  <map name="vending">
    <area shape="rect" coords="90,60,180,130" alt="거짓"
          href="##link##">
    <area shape="rect" coords="210,200,70,130" alt="진실"
          href="##link##">
  </map>
  ```
</blockquote>
