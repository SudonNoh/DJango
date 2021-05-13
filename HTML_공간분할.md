<h1>블록과 인라인</h1>

<h2>HTML 요소의 타입</h2>
<p>
  HTML의 모든 요소는 해당 요소가 웹 브라우저에 어떻게 보이는가를 결정짓는 display 속성을 가짐<br>
  대부분의 HTML 요소는 이러한 display 속성값으로 다음 두 가지 값 중 하나를 가지게 됨<br><br>
  1. 블록(block)<br>
  2. 인라인(inline)
</p>

<blockquote>
  <h3>블록(block)타입의 요소</h3>
  <p>display 속성값이 블록(block)인 요소는 언제나 새로운 라인(line)에서 시작하며, 해당 라인의 모든 너비를 차지<br>
    <i>&lt;p&gt;, &lt;div&gt;, &lt;h&gt;, &lt;ul&gt;, &lt;ol&gt;, &lt;form&gt;</i>요소는 display 속성값이 블록(block)인 대표적인 요소
  </p>
  
  ```html
  <p style="border: 3px solid red">
    p요소는 display 속성값이 블록인 요소
  </p>
  ```
  
  <h3>&lt;div&gt;요소</h3>
  <p>
    &lt;div&gt;요소는 다른 HTML 요소들을 하나로 묶는 데 자주 사용되는 대표적인 블록(block) 요소<br>
    &lt;div&gt;요소는 주로 여러 요소들의 스타일을 한 번에 적용하기 위해 사용
  </p>
  
  ```html
  <div style="background-color:lightgrey; color:green; text-align:center">
    <h1>div 요소를 이용한 스타일 적용</h1>
    <p>이렇게 div요소로 여러 요소들을 묶은 다음에 style 속성과 클래스 등을 이용하여 한 번에 스타일을 적용할 수 있음</p>
  </div>
  ```
</blockquote>
<blockquote>
  <h3>인라인(inline)타입의 요소</h3>
  <p>
    display 속성값이 인라인(inline)인 요소는 새로운 라인(line)에서 시작하지 않음<br>
    또한, 요소의 너비도 해당 라인 전체가 아닌 해당 HTML 요소의 내용(content)만큼만 차지<br>
    <i>&lt;span&gt;, &lt;a&gt;, &lt;img&gt;</i>요소는 display 속성값이 인라인(inline)인 대표적인 요소
  </p>
  
  ```html
  <p>
    <span style="background-color:grey; color:orange">span태그</span>는 display 속성값이 인라인인 요소
  </p>
  ```
  
  <h3>&lt;span&gt;요소</h3>
  <p>
    &lt;span&gt;요소는 텍스트(text)의 특정 부분을 묶는 데 자주 사용되는 인라인(inline)요소<br>
    &lt;span&gt;요소는 주로 텍스트의 특정 부분에 따로 스타일을 적용하기 위해 사용
  </p>
  
  ```html
  <p>이렇게
    <span style="border: 3px solid red">span요소로 텍스트의 일부분</span>
    만을 따로 묶은 후에 스타일을 적용할 수 있습니다.
  </p>
  ```
</blockquote>
    
    
<hr>
<h1>iframe 요소</h1>
<blockquote>
  <h3>iframe 요소</h3>
  <p>
    iframe이란 inline frame의 약자<br>
    iframe요소를 이용하면 해당 웹 페이지 안에 어떠한 제한 없이 또 다른 하나의 웹페이지를 삽입할 수 있음<br><br>
    문법: <i>&lt;iframe src="삽입할페이지주소"&gt;&lt;/iframe&gt;</i><br><br>
    iframe 요소는 frame 요소와는 달리 종료 태그가 존재<br>
    또한, iframe 요소는 명시된 크기로 삽입되는 창의 크기가 고정
  </p>
    
  ```html
  <iframe src="/css/intro" style="width:100%; height:300px">
  </iframe>
  ```
  
  <h3>iframe 요소의 테두리 변경</h3>
  <p>
    iframe 요소는 기본적으로 검정색 테두리(border)를 가짐<br>
    이러한 테두리의 스타일은 style 속성에서 border 속성을 이용하면 변경할 수 있음
  </p>
  
  ```html
  <iframe src="/css/intro" style="width:100%; height:300px; border: 3px dashed maroon">
  </iframe>
  ```
  
  <p>
    테두리를 표현하고 싶지 않으면 style 속성에서 border 속성값을 none으로 설정하면 됨
  </p>
  
  ```html
  <iframe src="/css/intro" style="width:100%; height:300px; border:none">
  </iframe>
  ```
  
  <h3>iframe 요소의 페이지 변경하기</h3>
  <p>
    &lt;a&gt;태그를 이용하면 iframe 요소의 최초 페이지를 중간에 변경할 수 있음<br>
    &lt;a&gt;태그의 target 속성과 iframe 요소의 name 속성을 연결하면, &lt;a&gt;태그를 통해 iframe요소의 홈페이지를 변경할 수 있음
  </p>
      
  ```html
  <iframe src="/css/intro" name="frame_target" style="width:100%; height:400px; border:none"></iframe>
  <p>
    <a href="/php/intro" target="frame_target">PHP 수업 확인하러 가기 =></a>
  </p>
  ```
  
  <h3>프레임셋(frameset)</h3>
  <p>
    프레임셋(frameset)을 이용하면 하나의 브라우저 창에 둘 이상의 페이지를 표시할 수 있음<br>
    이러한 프레임셋은 iframe 요소와는 달리 하나 이상의 페이지를 동시에 가질 수 있음<br>
    또한, <b>noresize 속성을 명시하지 않으면, 사용자가 마음대로 페이지의 크기를 조절할 수 있음</b><br><br>
    프레임셋에서 각각의 페이지는 frame 요소로 표현<br>
    frame 요소는 iframe 요소와는 달리 종료 태그를 가지지 않음<br><br>
    noframes 요소는 해당 브라우저가 frame 요소를 지원하지 않을 때 보여지는 문자열을 저장<br><br>
  </p>
  <i>"frameset, frame, noframes 요소를 HTML5 표준 권고안에서 더는 지원하지 않음<br>
  따라서 하나의 브라우저 창에 여러 페이지를 표현하고 싶을 때는 iframe 요소를 사용하거나 CSS를 이용하여 표현해야함"</i>
  
  <h3>수직 프레임셋</h3>
  <p>수직 프레임셋은 하나의 브라우저 창을 세로 방향으로 분리하여 표현</p>
  
  ```html
  <frameset cols="25%,*,25%">
  <frame name="left" src="/html/intro"/>
  <frame name="center" src="/css/intro"/>
  <frame name="right" src="/php/intro"/>
  <noframes>
    <body> 이 브라우저는 frame태그를 지원하지 않습니다!</body>
  </noframes>
  </frameset>
  ```
  
  <h3>수평 프레임셋</h3>
  <p>수평 프레임셋은 하나의 브라우저 창을 가로 방향으로 분리하여 표현</p>
  
  ```html
  <frameset rows="20%,60%,20%">
  <frame name="top" src="/html/into" noresize="noresize" />
  <frame name="center" src="/css/intro" noresize="noresize" />
  <frame name="bottom" src="/php/intro" noresize="noresize" />
  <noframes>
    <body>
      이 브라우저는 frame 태그를 지원하지 않습니다!
    </body>
  </noframes>
  </frameset>
  ```
</blockquote> 

<hr>
<h1>HTML 레이아웃(Layout)</h1>
<p>
  레이아웃(Layout)이란 특정 공간에 여러 구성 요소를 보기 좋게 효과적으로 배치하는 작업<br>
  웹 페이지의 레이아웃은 웹 사이트의 외관을 결ㄹ정짓는 매우 중요한 요소<br><br><br>
  HTML에서는 다음과 같은 방법으로 레이아웃을 작성할 수 있음<br>
  1. div 요소를 이용한 레이아웃
  2. HTML5 레이아웃
  3. table 요소를 이용한 레이아웃
</p>
<blockquote>
  <h3>div 요소를 이용한 레이아웃</h3>
  <p>div 요소는 CSS 스타일을 손쉽게 적용할 수 있으므로, 레이아웃을 작성하는데 자주 사용</P>
  
  ```html
  <div id="header"><h2>Header 영역</h2></div>
  <div id="nav"><h2>Nav 영역</h2></div>
  ```
  
  <h3>HTML5 레이아웃</h3>
  <p>
    HTML5에서는 웹페이지의 레이아웃만을 위한 별도의 새로운 요소들을 제공<br>
    이러한 요소들을 의미(semantic)요소라고 함
  </p>
  <table>
    <tr>
      <th>의미 요소</th>
      <th>설명</th>
    </tr>
    <tr>
      <td>&lt;header&gt;</td>
      <td>HTML 문서나 섹션(section) 부분에 대한 헤더(header)를 정의함</td>
    </tr>
    <tr>
      <td>&lt;nav&gt;</td>
      <td>HTML 문서의 탐색 링크를 정의함</td>
    </tr>
    <tr>
      <td>&lt;section&gt;</td>
      <td>HTML 문서에서 섹션(section) 부분을 정의함</td>
    </tr>
    <tr>
      <td>&lt;article&gt;</td>
      <td>HTML 문서에서 독립적인 하나의 글(ariticle) 부분을 정의함</td>
    </tr>
    <tr>
      <td>&lt;aside&gt;</td>
      <td>HTML 문서에서 페이지 부분 이외의 콘텐츠(content)를 정의함</td>
    </tr>
    <tr>
      <td>&lt;footer&gt;</td>
      <td>HTML 문서나 섹션(section) 부분에 대한 푸터(footer)를 정의함</td>
    </tr>
  </table>
  
  ```html
  <header><h2>Header 영역</h2></header>
  <nav><h2>Nav 영역</h2></nav>
  <section><p>Section 영역</p></section>
  <footer><h2>Footer 영역</h2></footer>
  ```
  
  <h3>table 요소를 이용한 레이아웃</h3>
  <p>
    table 요소를 이용해 레이아웃을 작성하는 방법은 오래전에 사용하던 방식으로, 현재는 거의 사용하지 않음<br>
    table 요소는 레이아웃을 만들기 위해 설계된 요소가 아니기 때문에, 테이블로 작성된 레이아웃은 수정이 매우 어려움
  </p>
  
  ```html
  <table width="100%" style="text-align:center; border:none">
      <tr>
          <td colspan="2" style="background-color:lightgrey"><h2>Header 영역</h2></td>
      </tr>
      <tr>
          <td style="background-color:#339999; color:white; width:20%"><h2>Nav 영역</h2></td>
          <td style="height:200px; text-align:left"><p>Section 영역</p></td>
      </tr>
      <tr>
          <td colspan="2" style="background-color:#FFCC00"><h2>Footer 영역</h2></td>
      </tr>
  </table>
  ```
  
</blockquote>
