<h1>블록과 인라인</h1>

<h2>HTML 요소의 타입</h3>
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
</blockquote>
    
