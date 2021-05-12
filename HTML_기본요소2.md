<h1>HTML 공부 3</h1>

<h2>HTML 리스트</h2>

<h3>1. 순서가 없는 리스트(unordered list)</h3>
<p>
  순서가 없는 리스트는 &lt;ul&gt;태그로 시작하며, 여기에 포함되는 각각의 리스트 요소는 &lt;li&gt;태그로 시작<br>
  각각의 리스트 요소 앞에는 기본 마커(marker)로 검정색의 작은 원(bullet)이 위치함<br><br><br>
  CSS의 list-style-type 속성을 사용하면 리스트 요소 앞에 위치하는 마커(marker)를 다른 모양으로 변경할 수 있음<br><br>
  - disc: 검정색 작은 원 모양(default)<br>
  - circle: 흰색 작은 원모양<br>
  - square: 사각형 모양<br>
  
</p>

```html
<ul style="list-style-type: circle">
  <li>사과</li>
  <li>멜론</li>
  <li>바나나</li>
</ul>
```

<h3>2. 순서가 있는 리스트(ordered list)</h3>
<p>
  순서가 있는 리스트는 &lt;ol&gt;태그로 시작하며, 여기에 포함되는 각각의 리스트 요소는 &lt;li&gt;태그로 시작<br>
  각각의 리스트 요소 앞에는 기본 마커로 아라비아 숫자가 위치<br><br><br>
  CSS의 list-style-type 속성을 사용하면 리스트 요소 앞에 위치하는 마커(marker)를 다른 모양으로 변경할 수 있음<br><br>
  - decimal: 숫자(default)<br>
  - upper-alpha: 영문 대문자<br>
  - lower-alpha: 영문 소문자<br>
  - upper-roman: 로마 숫자 대문자<br>
  - lower-roman: 로마 숫자 소문자<br>

```html
<ol style="list-style-type:upper-alpha">
  <li>수박</li>
  <li>참외</li>
  <li>옥수수</li>
</ol>
```

<h3>3. 정의 리스트(definition list)</h3>
<p>
  정의 리스트는 용어와 그에 대한 정의를 모아놓은 리스트로 &lt;dl&gt;태그로 시작<br>
  &lt;dt&gt;태그에는 용어의 이름이 들어가고, &lt;dd&gt;태그에는 해당 용어에 대한 정의가 들어감
</p>

```html
<dl>
  <dt>호박</dt>
  <dd>- 박과의 한해살이 덩굴성 채소</dd>
  <dt>상추</dt>
  <dd>- 국화과의 한해살이 또는 두해살이풀</dd>
</dl>
```

<hr>
<h2>HTML 테이블</h2>
<h3>1. HTML 테이블</h3>
<p>
  테이블(table)이란 여러 종류의 데이터(data)를 보기 좋게 정리하여 보여주는 표를 의미함<br>
  HTML에서는 &lt;table&gt;태그를 사용하여 이러한 테이블을 작성할 수 있음<br><br><br>
  &lt;table&gt;태그는 다음과 같이 구성<br><br>
  1. &lt;tr&gt;태그는 테이블에서 열을 구분<br>
  2. &lt;th&gt;태그는 각 열의 제목을 나타내며, 모든 내용은 자동으로 굵은 글씨가 적용되고 정렬은 가운데 정렬<br>
  3. &lt;td&gt;태그는 테이블의 열을 각각의 셀(cell)로 나누어 줌
</p>
<p>
  CSS의 border 속성을 이용하여 테이블에 테두리를 표현할 수 있음<br>
  border 속성값을 따로 명시하지 않으면, 해당 테이블은 언제나 빈 테두리를 가지게 됨<br><br>
  
  border만 설정하면 테두리가 두 줄씩 나타나는데, 이유는 &lt;table&gt;태그와 &lt;th&gt;태그, &lt;td&gt;태그가 모두 자신만의 테두리를 가지고 있기 때문<br><br>
  
  이런 경우 두 줄로 표현되는 테두리를 한 줄로 설정하려면 border-collapse 속성을 사용해야 함  
</p>

```html
<style>
  table, th, td { 
  border: 1px solid black;
  border-collapse: collapse }
  }
</style>

<table style="width:100%">
  <tr style="background-color:lightgrey">
    <th>참치</th>
    <th>고래</th>
  </tr>
  <tr>
    <td>상어</td>
    <td>문어</td>
  </tr>
  <tr>
    <td>오징어</td>
    <td>고등어</td>
  </tr>
</table>
```

<h3>2. HTML 테이블 열 합치기</h3>
<p>colspan 속성을 이용하면 테이블의 열(column)을 합칠 수 있음</p>

```html
<table style="width:100%">
  <tr>
    <td colspan="2">참치</td>
    <td>고래</td>
  </tr>
  <tr>
    <td>상어</td>
    <td>문어</td>
    <td>꽁치</td>
  </tr>
</table>
```

<h3>3. HTML 테이블 행 합치기</h3>
<p>rowspan 속성을 이용하면 테이블의 행(row)을 합칠 수 있음</p>

```html
<table style="width:100%">
  <tr>
    <td rowspan="2">참치</td>
    <td>고래</td>
    <td>날치</td>
  </tr>
  <tr>
    <td>상어</td>
    <td>문어</td>
  </tr>
</table>
```

<h3>4. HTML 테이블 캡션(caption)설정</h3>
<p>&lt;caption&gt;태그를 사용하면 테이블 상단에 제목이나 ㅉ랍은 설명을 붙일 </p>

```html
<table style="width:100%">
  <caption>해양 생물</caption>
  <tr>
    <td>참치</td>
    <td>고래</td>
    <td>상어</td>
  </tr>
</talbe>
```

