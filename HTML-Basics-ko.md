# HTML5 기본기 총 정리

웹 개발 입문자들을 위한 HTML 태그들 총 정리

HTML을 쉽게 이해할고 올바르게 사용할수있도록 정리해봤습니다  
모든 태그들이 포함되있지는 않지만 제일 많이 사용되는 태그들을 찾아보실수 있습니다

## 목차

1. [HTML 작성 방법](#HTML-작성-방법)  
   1.1 [코멘트 (주석)](#코멘트-주석)
2. [태그 vs 요소](#태그-vs-요소)  
   2.1 [태그](#태그)  
   2.2 [요소](#요소)
3. [HTML 기본 구조 만들기](#HTML-기본-구조-만들기)  
   3.1 [doctype](#doctype-html)  
   3.2 [html](#htmlhtml)  
   3.3 [head](#headhead)  
   3.2 [body](#bodybody)
4. [텍스트 관련 태그들](#텍스트-관련-태그들)  
   2.1 [p](#pp)  
   2.2 [span](#spanspan)  
   2.2 [strong](#strongstrong)  
   2.2 [em](#emem)  
   2.2 [h1 ~ h6](#h1h6)
5. [섹션 관련 태그들](#섹션-관련-태그들)  
   5.1 [header](#headerheader)  
   5.2 [nav](#navnav)  
   5.3 [main](#mainmain)  
   5.2 [aside](#asideaside)  
   5.4 [footer](#footerfooter)
6. [그룹핑 관련 태그들](#그룹핑-관련-태그들)  
   6.1 [ul](#ulul)  
   6.2 [ol](#olol)  
   6.3 [dl](#dldl)
7. [테이블](#테이블-요소)  
   7.1 [table](#tabletable)
8. [인터렉티브 태그들](#인터렉티브-태그들)  
   8.1 [a](#aa)  
   8.1 [button](#buttonbutton)  
   8.1 [details](#detailsdetails)
9. [미디어 태그들](#미디어-태그들)  
   9.1 [img](#img)  
   9.2 [audio](#audioaudio)  
   9.3 [video](#videovideo)  
   9.4 [iframe](#iframeiframe)
10. [폼](#폼-태그들)  
    10.1 [form](#formform)  
    10.2 [fieldset](#fieldsetfieldset)  
    10.3 [input](#input)  
    10.4 [textarea](#textareatextarea)

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# HTML 작성 방법

## 코멘트 (주석)

코멘트(주석)은 개발자가 코드에대한 보충 설명을 작성할때 사용하는 방법이다  
HTML에서 코멘트는 아래와같이 할수있다

```html
<!-- HTML 코멘트 -->
```

코멘트는 브라우저가 무시하고, 브라우저에 표시되지 않는다
<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 태그 vs 요소

HTML에서 `태그`, `요소` 이 두 단어를 많이 듯게되는데, 이 두개의 차이점은

## 태그

태그는 요소를 만드는 부품이라고 생각하면 된다  
태그에는 두가지가 있는데: 1) 열림 태그, 2) 닫힘 태그  
열림 태그는 `<` 와 `>` 사이에 태그 물품을 넣어서 만든다  
닫힘 태그는 `</` 와 `>` 사이에 태그 물품을 넣어서 만든다

```html
<p><!-- 열림 태그 --></p>
<!-- 닫힘 태그 -->
```

어떤 태그는 닫힘 태그가 없다. 이런 태그는 태그가 아닌 요소로 분리되고, 셀프클로징 요소라고 불린다

```html
<input type="text" />
```

## 요소

요소는 열림 태그와 닫힘 태그 한 세트를 요소라고 한다

```html
<!-- 요소 -->
<p></p>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# HTML 기본 구조 만들기

HTML이 브라우저에서 정상적으로 작동하려면 기본 구조를 아래처럼 먼저 만들어줘야 한다

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body></body>
</html>
```

## `<!doctype html>`

이건 태그도 아니고 요소도 아닌 선언문 이다  
브라우저가 HTML문서를 HTML5 버전으로 인식하게 해주는 선언문 이다  
문서에서 제일 첫번째 줄에 작성한다

## `<html></html>`

HTML의 시작점 이다  
웹 페이지의 모든 내용들을 담는 컨테이너 이다. 루트(root) 라고도 한다

## `<head></head>`

이 요소는 메타 데이터들이 들어가는 컨테이너 이다  
`<html>` 안에 들어가고 `<body>`위에 위치한다  
메타 데이터는 HTML문서에 대한 데이터로 브라우저에 표시되지 않는다  
메타데이터 로는 문서 타이틀, 스타일, 스크립트 및 기타 정보를 정의한다

이 요소 안에 들어갈수있는 요소들

- `<title>`
- `<style>`
- `<link>`
- `<script>`
- `<meta>`

## `<body></body>`

이 요소는 페이지의 모든 콘텐츠들이 들어가는 요소이다  
텍스트, 이미지, 비디오, 오디오, 링크, 등등 모든 웹 콘텐츠들을 담고, 브라우저에 표시한다

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

<!-- 메타 데이터 title, style, link, script, meta -->

# 텍스트 관련 태그들

## `<p></p>`

일반 텍스트에 사용되는 태그이다  
성질은 블록요소로 주변 콘텐츠들은 이 태그의 위나 아래에 위치한다

```html
<p></p>
```

## `<span></span>`

일반 텍스트에 사용되는 태그이다  
성질은 인라인요소로 주변 콘텐츠들은 이 태그의 왼쪽이나 오른쪽에 위치한다  
\*주변 콘텐츠가 블록요소일경우 그 요소의 위나 아래에 위치한다  
다른 텍스트 태그와 같이 사용가능하다

```html
<span></span>
<p><span></span></p>
<a><span></span></a>
<h1><span></span></h1>
```

## `<strong></strong>`

일반 텍스트에 사용되는 태그이다  
성질은 인라인요소로 주변 콘텐츠들은 이 태그의 왼쪽이나 오른쪽에 위치한다  
\*주변 콘텐츠가 블록요소일경우 그 요소의 위나 아래에 위치한다  
다른 텍스트 태그와 같이 사용가능하다  
내용의 한 특정 정보를 강요할때 사용한다

예) 신청 기간은 <strong>8월 20일 부터 9월 15일</strong> 까지 입니다

```html
<!-- 예시 -->
<p>신청 기간은 <strong>8월 20일 부터 9월 15일</strong> 까지 입니다</p>

<strong></strong>
<p><strong></strong></p>
<a><strong></strong></a>
<h1><strong></strong></h1>
```

## `<em></em>`

일반 텍스트에 사용되는 태그이다  
성질은 인라인요소로 주변 콘텐츠들은 태그의 왼쪽이나 오른쪽에 위치한다  
\*주면 콘텐츠가 블록요소일경우 그 요소의 위나 아래에 위치한다  
다른 텍스트 태그와 같이 사용가능하다  
내용의 한 특정 부분을 강요할때 사용한다  
`<strong>`과는 다른 개념의 강요로, `<em>`은 그 문장의 뜻을 바꾼다

예)
문장: 나는 그가 돈을 훔쳤다고 말한적 없다  
뜻: 그가 돈을 훔쳤다고 내가 말하지 않았다

문장: 나는 그가 <em>돈을</em> 훔쳤다고 말한적 없다  
뜻: 그가 무언가를 훔쳤지만 그게 돈이라고 나는 말 한적 없다

```html
<!-- 예시 -->
<p>나는 그가 <em>돈을</em> 훔쳤다고 말한적 없다</p>

<em></em>
<p><em></em></p>
<a><em></em></a>
<h1><em></em></h1>
```

## `<h1>~<h6>`

헤딩을 만들때 사용하는 태그이다  
`<h1>`이 제일 큰 사이즈이고 갈수록 작아져서 `<h6>`이 제일 작다  
\*\*헤딩의 사이즈는 크게 중요하지 않다

헤딩 태그의 본래 용도는 페이지의 **제목을 정하고**, **섹션을 나누는** 용도이다  
헤딩 사용법:  
각 페이지에 하나의 `<h1>`이 존재해야 한다

- `<h1>`은 그 페이지의 제목이다. 즉, `<h1>`만으로 그 페이지의 내용을 추리할수 있어야 한다
- `<h2>`는 그 페이지의 각 섹션 제목이다
- `<h3>`은 `<h2>`섹션의 부 제목이다
- `<h2>`는 `<h3>`의 부 제목이다
- `<h5>`는 `<h2>`의 부 제목이다
- `<h6>`은 `<h5>`의 부 제목이다
- 각 페이지의 제목 깊이로 최대 `<h3>`~`<h2>`가 제일 이상적이다
- 헤딩 레벨을 건너뛰는건 기피해야 한다

예)

```html
<h1>야채 분류</h1>

<h2>뿌리 채소</h2>
<h3>당근</h3>
<h3>무</h3>

<h2>열매 채소</h2>
<h3>토마토</h3>
<h3>오이</h3>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 섹션 관련 태그들

## `<header></header>`

헤더는 웹사이트를 소개하는 부분이다  
주로 웹사이트의 제일 위에 자리한다  
헤더 랜드마크를 형성해 웹 접근성과 SEO에 도움을 준다

헤더에서 볼수있는 내용들:

- 브랜드 로고
- 검색
- 로그인
- 메뉴\*\*

\*\*: 메뉴는 헤더 안에 들어가기도 하고 바로 아래에 위치하기도 한다

헤더에 `<h1>`을 사용하는건 기피해야 한다

```html
<header>
  <!-- 헤더 내용 -->
</header>
```

## `<nav></nav>`

웹사이트의 메뉴를 만들때 사용하는 태그이다  
주로 헤더 안, 또는 헤더 아래에 위치한다  
웹사이트에 한개 이상의 메뉴를 사용해도 되지만, 너무 많이 사용하는건 추천하지 않는다  
네비게이션 랜드마크를 형성해 웹 접근성과 SEO에 도움을 준다

```html
<nav>
  <!-- 메뉴 아이템 -->
</nav>
```

## `<main></main>`

페이지의 메인 콘텐츠 섹션을 나타낸다  
예를 들자면 뉴스기사 페이지에서 뉴스내용이 메인 콘텐츠이므로 `<main>`에 들어간다  
메인 랜드마크를 형성해 웹 접근성과 SEO에 도움을 준다

```html
<main>
  <!-- 메인 콘텐츠 -->
</main>
```

## `<aside></aside>`

페이지에서 메인 내용을(`<main>`) 제외한 일부 콘텐츠를 말한다  
주로 페이지의 오른쪽에 있는걸 볼수있다  
페이지의 메인 내용과 간접적으로 연결되는 내용을 담는다  
자체적으로는 아무런 스타일이 없고, 주로 CSS를 사용해서 주 내용의 오른쪽으로 배치한다  
예를 들어서, 메인 내용이 고양이 발톱관리에 대한 내용이라면 `<aside>`에 이에 간접적이로 연결되는 내용으로  
고양이에게 발톱이 중요한 이유라던지, 발톱을 다쳤을때 응급처치라던지, 이런 내용들이 들어간다

```html
<aside>
  <!-- 메인 내용과 간접적인 내용 -->
</aside>
```

## `<footer></footer>`

웹 사이트의 바닥글로 페이지의 맨 밑에 위치한다  
일반적으로 포함하는 내용들은

- 저작권 정보
- 연락처 정보
- 사이트맵
- 맨 위로 돌아가기 링크
- 관련된 문서

```html
<footer>
  <!-- 푸터 내용 -->
</footer>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 그룹핑 관련 태그들

## `<ul></ul>`

'ul'은 'Unordered List'의 약자로, 직역하면 '정렬되지 않은 리스트'이다  
정렬되지 않은 리스트는 순서에 상관없이 나열할수있는 리스트를 말한다

`<ul>`은 정렬되지 않은 리스트 구조를 만들기만 한다  
이 요소를 완성하려면 `<li></li>`를 안에 같이 사용해야한다  
'li'는 'List Item'의 약자로 '리스트 아이템' 이다  
'li'안에 'ul'을 네스트(nest)할수있다

장 보러갈때 메모에 쓰는 리스트를 예로 들수있다  
살 물건들을 나열하는게 목적이지, 어떤 순서로 사는건 중요하지 않기때문이다

예시)

<p>장 볼것들</p>
<ul>
  <li>라면</li>
  <li>대파</li>
  <li>고기
    <ul>
      <li>살치살</li>
      <li>갈비살</li>
      <li>삼겹살</li>
    </ul>
  </li>
  <li>계란</li>
</ul>

코드)

```html
<p>장 볼것들</p>
<ul>
  <li>라면</li>
  <li>대파</li>
  <li>
    고기
    <ul>
      <li>살치살</li>
      <li>갈비살</li>
      <li>삼겹살</li>
    </ul>
  </li>
  <li>계란</li>
</ul>
```

## `<ol></ol>`

'ol'은 'Ordered List'의 약자로, 직역하면 '정렬된 리스트'이다  
'ul'과는 반대로 순서가 중요한 리스트를 만들때 사용한다  
'ol'은 기본으로 1 부터 시작한다  
'ul'과 같이 'li'를 같이 사용한다  
이케아 가구 조립 순서를 예로 들수있다

'ul'과 같이 'li'안에 'ol'을 네스트 할수있다  
네스트된 리스트의 번호를 바꾸려면 `type`속성을 사용해서 바꿀수있다  
`type`속성에 사용할수있는 값: [1, a, A, i, I]

예시)

<p>이케아 선반 조립 설명서</p>
<ol>
  <li>부품들을 확인한다</li>
  <li>필요한 공구를 준비한다</li>
  <li>
    설명서를 참고한다
    <ol type="a">
      <li>천천히 살펴본다</li>
      <li>천천히 따라해본다</li>
    </ol>
  </li>
  <li>엄마/아빠를 부른다</li>
</ol>

코드)

```html
<p>이케아 선반 조립 설명서</p>
<ol>
  <li>부품들을 확인한다</li>
  <li>필요한 공구를 준비한다</li>
  <li>
    설명서를 참고한다
    <ol type="a">
      <li>천천히 살펴본다</li>
      <li>천천히 따라해본다</li>
    </ol>
  </li>
  <li>엄마/아빠를 부른다</li>
</ol>
```

## `<dl></dl>`

'dl'은 'Description List'의 약자로 '설명 리스트'이다  
사전처럼 어떤것을 설명할때 사용한다  
'ul', 'ol'과는 다르게 같이 사용되는 태그로는 `<dt></dt>`, `<dd></dd>`가 있다  
'dt'는 'Description Term'의 약자로, 직역하면 '설명 용어'이다  
'dd'는 'Description Details'의 약자로, 직영하면 '세부 설명'이다

예시)

<dl>
  <dt>구글 크롬</dt>
  <dd>구글이만든 웹 브라우저로 모든 구글 앱을 사용하기 쉽게 만들어졌다</dd>
</dl>

코드)

```html
<dl>
  <dt>구글 크롬</dt>
  <dd>구글이만든 웹 브라우저로 모든 구글 앱을 사용하기 쉽게 만들어졌다</dd>
</dl>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 테이블 요소

## `<table></table>`

엑셀처럼 데이터를 행과 열로 표시할때 사용한다  
'ul', 'ol'처럼 테이블이라는 큰 틀을 만들뿐, 이 태그 하나로는 테이블을 만들수없다  
당연히 필수 태그이다

같이 사용되는 태그들:

- [`<caption></caption>`](#captioncaption)
- [`<thead></thead>`](#theadthead)
- [`<tr></tr>`](#trtr)
- [`<th></th>`](#thth)
- [`<tbody></tbody>`](#tbodytbody)
- [`<td></td>`](#tdtd)
- [`<tfoot></tfoot>`](#tfoottfoot)

### `<caption></caption>`

테이블의 제목/용도를 정할때 사용한다  
기본적으로 테이블에서 제일 처음으로 보이고, 가운데 정렬된다

필수 태그는 아니지만 웹 접근성에 도움이 된다  
스크린 리더와 호환되어 유저가 테이블에 도착했을때 제일먼저 읽어주는 내용이다  
스크린 리더를 사용하는 유저는 이 요소의 내용으로 테이블의 용도를 추리할수있다

예시)  
// `style="width: 100%` 는 무시해도 된다. 행과 열없이는 테이블의 넓이가 좁아서 임시로 넓이를 늘린거다

<table style="width: 100%">
  <caption>8월 지출 내역</caption>
</table>

코드)

```html
<table>
  <caption>
    8월 지출 내역
  </caption>
</table>
```

### `<thead></thead>`

테이블의 머릿말 이라고 할수있다  
각 행(세로)의 제목이 들어간다  
필수 태그는 아니다  
사용할때의 장점은 CSS로 엑셀에서처럼 첫번째 열을 고정하는걸 구현할수있다

예시)  
// `style="width: 100%` 는 무시해도 된다. 행과 열없이는 테이블의 넓이가 좁아서 임시로 넓이를 늘린거다

<table style="width: 100%">
  <caption>8월 지출 내역</caption>
  <thead>

  </thead>
</table>

코드)

```html
<table style="width: 100%">
  <caption>
    8월 지출 내역
  </caption>
  <thead></thead>
</table>
```

### `<tr></tr>`

테이블의 열(가로 줄)을 만들때 사용한다  
필수 태그이다  
'thead', 'tbody', 'tfoot'안에서 사용된다

예시)  
// `style="width: 100%` 는 무시해도 된다. 행과 열없이는 테이블의 넓이가 좁아서 임시로 넓이를 늘린거다

<table style="width: 100%">
  <caption>8월 지출 내역</caption>
  <thead>
    <tr>
    </tr>
  </thead>
</table>

코드)

```html
<table style="width: 100%">
  <caption>
    8월 지출 내역
  </caption>
  <thead>
    <tr></tr>
  </thead>
</table>
```

### `<th></th>`

행, 열의 제목을 만들때 사용한다  
필수 태그이다  
스크린 리더에서 테이블 헤딩이라고 알려준다  
이걸로 스크린 리더 유저는 각 행의 내용을 파악할수있다  
`scope`속성을 같이 사용하면 웹 접근성을 더 좋게 만들어준다

`scope`은 이 제목이 어느 구간의 제목인지를 정하는 속성이다  
이 속성의 값으로는:

<dl>
<dt>col</dt>
<dd>한 행(세로)의 제목을 뜻한다</dd>
<dt>row</dt>
<dd>한 열(가로)의 제목을 뜻한다</dd>
<dt>colgroup</dt>
<dd>여러 행의 제목을 뜻한다. `colspan`속성과 같이 사용된다</dd>
<dt>rowgroup</dt>
<dd>여러 열의 제목을 뜻한다. `rowspan`속성과 같이 사용된다</dd>
</dl>

`*span`속성

<dl>
<dt>colspan</dt>
<dd>행의 범위를 말한다. 값이 2 이면 한 행이 두 행만큼 늘어난다</dd>
<dt>rowspan</dt>
<dd>열의 범위를 말한다. 값이 2 이면 한 열이 두 열만큼 늘어난다</dd>
</dl>

사용방법)

```html
<th scope="col"></th>
<th scope="row"></th>
<th scope="colgroup" colspan="2"></th>
<th scope="rowgroup" rowspan="2"></th>
```

'th' 예시)

<table>
  <caption>8월 지출 내역</caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
</table>

코드)

```html
<table>
  <caption>
    8월 지출 내역
  </caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
</table>
```

### `<tbody></tbody>`

테이블의 본문이다  
필수 태그이다  
표시하고자 하는 데이터들을 표시한다

<table>
  <caption>8월 지출 내역</caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>

코드)

```html
<table>
  <caption>
    8월 지출 내역
  </caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>
```

### `<td></td>`

테이블 셀을 만들때 사용한다  
필수 태그이다  
'th'와 같이 `rowspan`, `colspan`을 사용할수 있다

<table>
  <caption>8월 지출 내역</caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>치킨</td>
      <td>2</td>
      <td>25200</td>
    </tr>
    <tr>
      <td>바지</td>
      <td>1</td>
      <td>50000</td>
    </tr>
    <tr>
      <td>아이스크림</td>
      <td>5</td>
      <td>25000</td>
    </tr>
  </tbody>
</table>

코드)

```html
<table>
  <caption>
    8월 지출 내역
  </caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>치킨</td>
      <td>2</td>
      <td>25200</td>
    </tr>
    <tr>
      <td>바지</td>
      <td>1</td>
      <td>50000</td>
    </tr>
    <tr>
      <td>아이스크림</td>
      <td>5</td>
      <td>25000</td>
    </tr>
  </tbody>
</table>
```

### `<tfoot></tfoot>`

테이블의 각 행을 요약할때 사용한다  
필수 태그는 아니다

<table>
  <caption>8월 지출 내역</caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>치킨</td>
      <td>2</td>
      <td>25200</td>
    </tr>
    <tr>
      <td>바지</td>
      <td>1</td>
      <td>50000</td>
    </tr>
    <tr>
      <td>아이스크림</td>
      <td>5</td>
      <td>25000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>8</td>
      <td>100200</td>
    </tr>
  </tfoot>
</table>

코드)

```html
<table>
  <caption>
    8월 지출 내역
  </caption>
  <thead>
    <tr>
      <th>물품</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>치킨</td>
      <td>2</td>
      <td>25200</td>
    </tr>
    <tr>
      <td>바지</td>
      <td>1</td>
      <td>50000</td>
    </tr>
    <tr>
      <td>아이스크림</td>
      <td>5</td>
      <td>25000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>8</td>
      <td>100200</td>
    </tr>
  </tfoot>
</table>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 인터렉티브 태그들

## `<a></a>`

링크를 만들때 사용하는 태그이다  
이 태그만 사용할수도있고, 다른 텍스트 태그와 같이 사용할수있다  
`href`는 링크 태그의 필수 속성이다  
이 속성이 있어야만 링크가 만들어진다  
속성의 값으로는:

- 웹 URL
- 다른 요소의 아이디

샘플)
구글로 가는 링크  
<a href="https://google.com">Google</a>  
<br aria-hidden="true">
다른 요소로 가는 링크  
<a href="#HTML-기본-구조-만들기">HTML 기본 구조 만들기</a>

```html
<!-- 구글로 가는 링크 -->
<a href="https://google.com">Google</a>

<!-- 다른 요소로 가는 링크 -->
<a href="#HTML-기본-구조-만들기">HTML 기본 구조 만들기</a>
```

옵션으로 `target`속성도 사용할수있다  
이 속성은 링크를 어떻게 열건지를 정하는 속성이다  
이 속성의 기본 값은 `_self`(셀프)이다. 이 값은 현재 창/탭에서 이동한다  
속성을 사용하지 않으면 자동으로 셀프값을 사용한다  
다른 값으로는 `_blank`(블랭크)가 있다. 이 값은 새로운 창/탭을 사용한다

샘플)  
현재 창/탭에서 열림  
<a href="https://google.com">Google</a>  
<a href="https://google.com" target="_self">Google</a>  
<br>
새로운 창/탭 에서 열림  
<a href="https://google.com" target="_blank">Google</a>

```html
<!-- 현재 창/탭에서 열림 -->
<a href="https://google.com">Google</a>
<a href="https://google.com" target="_self">Google</a>

<!-- 새로운 창/탭 에서 열림 -->
<a href="https://google.com" target="_blank">Google</a>
```

## `<button></button>`

버튼을 만들때 사용한다  
링크와 버튼의 차이점:

- 링크는 어딘가로 이동할때 사용 (예: 홈에서 연예 페이지로)
- 버튼은 어떠한 동작을 구현할때 사용 (예: 로그인, 폼 재출, 다크모드 온/오프, 등등)

버튼은 유저의 액션이 필요한 어디에서든지 사용가능하다  
버튼만으로는 아무것도 하지않는다. 자바스크립트로 원하는 액션을 구현해줘야한다  
버튼을 자바스크립트와 연결하려면 버튼에 이벤트속성을 사용하면 된다  
이벤트속성에는 여러종류가 있는데, 그 중에서 제일 대표적인건 클릭 이벤트이다  
클릭 이벤트는 버튼이 클릭됬을때 주어진 액션을 구현한다  
_이벤트에 대한 자세한 내용은 자바스크립트에서 확인할수있다 (작업중)_

```html
<button onclick="<!-- 자바스크립트_함수 -->">테스트</button>
```

버튼에는 세가지 타입 있다:

- button: 기본값
- reset: 폼을 리셋한다
- submit: 폼을 재출한다

버튼 타입은 `type`속성을 사용해서 정할수있다  
이 속성을 사용하지 않으면 자동으로 기본값인 button을 사용한다

```html
<button type="button">버튼 타입</button>
<button type="reste">리셋 타입</button>
<button type="submit">재출 타입</button>
```

## `<details></details>`

흔히 어코디언이라고 불리는 요소를 만들때 사용하는 태그이다  
어코디언은 버튼클릭으로 아래에있는 상세정보를 열었다 닫았다 할수있는 요소이다  
이 태그는 `<summary></summary>` 태그와 같이 사용된다  
`<details>`는 요소의 틀을 만들고 `<summary>`는 이 요소의 제목을 뜻한다
<br aria-hidden="true">
기본적으로 아무런 스타일이 없어서 CSS로 따로 스타일을 해줘야한다

샘플)

 <details>
  <summary>테스트 - 클릭해서 열어보세요</summary>
  <p>어코디언 요소입니다.</p>
 </details>

```html
<details>
  <summary>테스트 - 클릭해서 열어보세요</summary>
  <p>어코디언 요소입니다.</p>
</details>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 미디어 태그들

## `<img />`

이미지를 사용할때 사용하는 태그이다  
`src`필수 속성을 사용해서 이미지를 나타낼수있다  
이 속성의 값으로는 로컬 이미지 또는 이미지의 웹 URL을 사용할수있다

샘플)  
로컬 이미지 사용  
<img src="./img/bg.jpg">

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

이미지 URL사용  
<img src="https://picsum.photos/640/427">

```html
<!-- 로컬 이미지 사용 -->
<img src="./img/bg.jpg" />
<!-- 이미지 URL 사용 -->
<img src="https://picsum.photos/640/427" />
```

이미지에는 또다른 필수 속성인 `alt`가 있다  
이 속성은 이미지가 로드 안될때 이미지 대신에 보여지는 텍스트라고 알고있지만  
이것도 맞는 말이지만 또다른 용도는 스크린 리더 유저들을 위함이다  
스크린 리더가 이 속성의 텍스트를 읽어줌으로 유저가 이미지에 담겨있는 정보를 접할수있다

```html
<img src="..." alt="이미지를 설명하는 텍스트" />
```

## `<audio></audio>`

페이지에 오디오 플레이어를 만들때 사용하는 태그이다  
이 태그를 사용하는 방법은 두 가지가 있다

- `src` 속성 사용
- `<source>` 태그 사용

```html
<!-- src 속성 사용 -->
<audio src="/media/cc0-audio/t-rex-roar.mp3"></audio>

<!-- source 태그 사용 -->
<audio>
  <source src="horse.ogg" type="audio/ogg" />
  <source src="horse.mp3" type="audio/mpeg" />
</audio>
```

`<source>`태그를 사용할때 장점은 여러가지의 오디오 타입을 사용해서 브라우저와의 호환성을 높일수있다

<br aria-hidden="true">

오디오 태그와 같이 사용할수있는 속성들:

- `autoplay`: 오디오를 자동 재생
- `controls`: 오디오 컨트롤 UI 생성
- `loop`: 오디오 반복 재생

```html
<audio src="..." autoplay controls loop></audio>
```

## `<video></video>`

비디오 플레이어를 만들때 사용하는 태그이다  
오디오 태그와 비슷하게 여러 속성을 사용해서 여러 컨트롤을 활성화할수있다

```html
<!-- src 속성 사용 -->
<video src="..." controls autoplay loop></video>

<!-- source태그 사용 -->
<video controls autoplay loop>
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.ogg" type="video/ogg" />
</video>
```

## `<iframe></iframe>`

아이프레임, 다른 웹 컨텐츠를 내 웹 페이지에 삽입할때 사용하는 태그이다  
유튜브 영상을 내 페이지에 삽입할때 사용하는 방식이다  
사용 방식은 필수 속성인 `src`에 웹 URL을 주어 사용한다

```html
<iframe src="https://www.youtube.com/embed/qBjrBGQ-xH4"></iframe>
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 폼 태그들

## `<form></form>`

폼, 즉 양식을 만들때 사용하는 태그다  
이 태그만으로는 폼을 만들수는 없고, 다른 태그들을 같이 사용해서 여러 타입의 폼을 만들수있다

폼 태그의 필수 속성 두 가지:

- action: 폼을 재출할 URL
- method: 폼의 재출 방식 (GET [받기], POST[보내기])

```html
<form action="https://www.mysite.com/form-submit" method="POST"></form>
```

## `<fieldset></fieldset>`

폼의 여러 컨트롤들을 그룹짓는 태그이다  
유저가 작성해야하는 분야를 나눠주는 역할이다

<br aria-hidden="true">

같이 사용하는 태그로 `<legend></legend>`가 있다  
`legend`는 필드셋의 제목을 만들어준다

```html
<form action="https://www.mysite.com/form-submit" method="POST">
  <fieldset>
    <legend>개인 정보</legend>
  </fieldset>
  <fieldset>
    <legend>취미</legend>
  </fieldset>
</form>
```

## `<input>`

유저의 인풋을 받을수있는 태그이다  
인풋 태그에는 정말 많은 타입이 존재하지만 여기서는 간단하게 몇가지만 알아보겠다  
인풋 타입은 `type`속성을 사용해서 정할수있다

인풋 타입:

- text
- email
- password
- tel
- checkbox
- radio
- date
- file
- 등등

인풋 태그를 사용할때는 꼭 `<label></label>` 태그를 같이 사용해야한다  
`<label>`을 `<input>`과 연결하는 방법은 `id`와 `for`속성을 사용하는 방법이다

```html
<form action="https://www.mysite.com/form-submit" method="POST">
  <fieldset>
    <legend>개인 정보</legend>
    <label for="name">이름</label>
    <input type="text" id="name" />

    <label for="email">이메일</label>
    <input type="email" id="email" />
  </fieldset>
  <fieldset>
    <legend>취미</legend>
    <label for="game">게임</label>
    <input type="radio" id="game" name="hobbies" value="game" />
    <label for="fitness">운동</label>
    <input type="radio" id="fitness" name="hobbies" value="fitness" />
    <label for="coding">코딩</label>
    <input type="radio" id="coding" name="hobbies" value="coding" />
    <label for="travel">여행</label>
    <input type="radio" id="travel" name="hobbies" value="travel" />
  </fieldset>
</form>
```

## `<textarea></textarea>`

많은 양의 유저 입력을 받을수있는 태그이다  
여러줄의 텍스트를 입력할수있어서 리뷰나 의견등의 입력을 수집할때 사용한다

같이 사용할수있는 속성으로는

- rows: 태그의 시작 높이를 정한다
- cols: 태그의 시작 넓이를 정한다

`row`, `col` 속성을 사용하지 않고 CSS로 넓이와 높이를 정할수있다

```html
<textarea cols="50" rows="7"></textarea>
```
