# CSS 기본기 총 정리

웹 개발 입문자들을 위한 CSS 총 정리

CSS를 쉽게 이해할수 있도록 최대한 심플하게 정리해봤습니다  
모든걸 포함하지는 않았지만 이것들만알면 사용하고 배우는데 문제없을거에요

# 목차

1. [CSS 사용하는 방법](#CSS-사용하는-방법)
2. [CSS 문법](#CSS-문법)
3. [선택자](#선택자)

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# CSS 사용하는 방법

CSS를 사용하는 방법은:

- [inline](#inline)
- [`<style></style>`](#stylestyle)
- [CSS 파일](#CSS-파일)

## Inline

인라인, 또는 인라인 스타일이라고도 하는데  
이 방법은 태그에서 `style`속성을 사용하는 방법이다  
이 방법의 단점은:

- 반복작업: 모든 태그에 일일이 작성해야한다
- 시간: 많은 시간이 걸리는 방법으로 효율적이지 않다

```html
<p style="padding: 1px; border: 2px solid blue; font-weight: bold"></p>
```

## `<style></style>`

이 방법은 인라인 방법보다는 편한 방법이지만 HTML문서에 많은 자리를 차지한다  
`<style>`태그는 `<head>`안에 들어간다

이 방법의 단점은:

- 반복작업: 모든 HTML문서에 일일이 복붙해야 한다
- 스타일 변형: 모든 페이지에 같은 스타일을 사용하지 않기에 스타일 변형을 일일아 찾아서 해야한다
- 자리차지: 각 페이지의 내용이 정말 간단하지 않은이상 HTML문서에서 많은 자리를 차지한다

```html
<head>
  <style>
    /* CSS 스타일 */
  </style>
</head>
```

## CSS 파일

이 방법은 CSS파일을 `<link>` 태그를 사용해서 HTML문서에 연결하는 방법이다  
위 두 방법보다 제일 효율적이고 편리한 방법이다  
`href`, `rel`은 `<link>`태그의 필수 속성이다

`href`: CSS 파일의 위치  
`rel`: HTML문서와의 관계

```html
<link href="styles.css" rel="stylesheet" />
```

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# CSS 문법

CSS에서 꼭 알아야하는 문법과 룰이 몇가지 존재한다

CSS의 문법

```css
/*
선택자 {
  스타일 속성: 스타일 값;
}
*/
p {
  font-size: 16px;
}
```

`;`은 필수이다. `;`이 없으면 CSS 파일에서 에러로 표시된다

- [적용 방식](#적용-방식)
- [우선 순위](#우선-순위)

## 적용 방식

적용 방식은 CSS 스타일이 HTML요소에 어떻게 적용하는지를 뜻한다  
이 방식은 인라인 스타일 이외의 방법을 사용했을때에 확인할수있다

CSS는 Cascadding Style Sheets의 약자로 직역하면 '계단식 스타일 시트'이다  
계단식을 정확히 설명하자면 위에서 아래 순서로 스타일이 적용되는걸 말한다  
이 말은 제일 마지막에 오는 스타일이 요소에 적용된다는 말이다

```css
p {
  color: red;
}
p {
  color: blue; /* 위 빨간 스타일을 취소하고 파랑이 요소에 적용된다 */
}
```

## 우선 순위

CSS에서 제일 중요한 부분중 하나이다  
스타일이 어떻게 작성되있는냐에따라 서로 취소하기때문이다

**아래 우선 순위는 제일 기본적인고 제일 강한 순위부터 약한순위이다**

1. 인라인 스타일
2. `<style></style>`
3. CSS 파일  
   3.1 스타일 순서: 마지막에 오는 스타일이 적용된다  
   3.2 선택자: 아이디 선택자가 클라스 선택자보다 우선 순위가 높다  
   3.3 선택자 깊이: `header a` 보다 `header nav p a` 가 우선 순위가 높다  
   3.4 선택자 방식: `:first-child`, `:not()` 등 사용된 수도 선택자에따라 우선 순위가 바뀐다

<br aria-hidden="true">
<br aria-hidden="true">
<br aria-hidden="true">

# 선택자

선택자는 요소를 선택하는 방식이다  
CSS 선택자는 그 선택자의 형태에따라서 적용 범위가 달라진다  
요소를 선택하는 방식은 여러개가 존재한다

선택자 방식:

- [태그 이름](#태그-이름)
- [아이디](#아이디)
- [클라스](#클라스)
- [관계](#관계)

## 태그 이름

태그 이름은 말 그대로 태그 이름을 사용해서 요소를 고르는 방식이다

```css
/* 모든 p 요소에 적용 */
p {
  ...;
}

/* div 안에 모든 a 요소에 적용 */
div a {
  ...;
}

/* div 안에 ul의 li의 a 요소에 적용 */
div ul li a {
  ...;
}
```

## 아이디

요소의 아이디를 사용해서 선택하는 방식이다  
아이디 선택자가 태그 이름, 클라스보다 우선 순위가 높은 이유는 한 HTML문서에서 아이디를 중복으로 사용할수 없기때문이다  
요소 아이디는 한 HTML문서에서 딱 한번만 사용할수있다  
여러 요소들이 아이디를 가질수 있지만 각 아이디가 중복될수는 없다  
CSS에서 아이디를 선택할때 `#`를 사요한다

```html
<p id="first"></p>
<p id="second"></p>
<p id="third"></p>
```

```css
#first {
  ...;
}

#second {
  ...;
}

#third {
  ...;
}
```

## 클라스

요소의 클라스를 사용해서 선택하는 방식이다  
요소 클라스는 아이디와는 달리 중복사용이 가능하다  
CSS에서 클라스를 선택할때 `.`를 사용한다

```html
<p class="green-text"></p>
<p class="green-text"></p>
<p class="green-text"></p>
<p class="large-text"></p>
<p class="large-text"></p>
<p class="large-text"></p>
<div class="green-text"></div>
<div class="green-text"></div>
<div class="green-text"></div>
<div class="large-text"></div>
<div class="large-text"></div>
<div class="large-text"></div>
```

```css
/* p와 div 모두에 적용 */
.green-text {
  ...;
}

.large-text {
  ...;
}

/* green-text클라스를 가지고있는 p요소에만 적용 */
p.green-text {
  ...;
}

/* large-text클라스를 가지고있는 div요소에만 적용 */
div.large-text {
  ...;
}
```

## 관계

요소간의 관계를 사용해서 선택하는 방식이다

`div a`: div안에 있는 모든 a 요소를 선택한다

```html
<div>
  <a>여기에 적용</a>
  <a>여기에 적용</a>
  <a>여기에 적용</a>
</div>
```

```css
div a {
  ...;
}
```

`div > a`: div의 첫번째 a 자녀 요소를 선택한다

```html
<div>
  <p></p>
  <a>여기에 적용</a>
  <a>적용 안됨</a>
</div>
```

```css
div > a {
  ...;
}
```

`p + a`: 동일한 부모요소 속에 p요소의 바로 옆 첫번째 형제인 a 요소를 선택한다. p와 a사이에 다른 요소가 있으면 적용하지 않는다

```html
<div>
  <p></p>
  <a>여기에 적용</a>
  <a>적용 안됨</a>
</div>
```

```css
p + a {
  ...;
}
```

`p ~ a`: 동일한 부모요소 속에 p요소의 모든 a 형제 요소를 선택한다. 두 요소 사이에 다른 요소가 있어도 상관없다

```html
<div>
  <p></p>
  <a>여기에 적용</a>
  <a>여기에 적용</a>
  <p></p>
  <a>여기에 적용</a>
  <a>여기에 적용</a>
</div>
```

```css
p ~ a {
  ...;
}
```

`[attr]`: 이 속성을 가진 모든 요소에 적용한다

```html
<input type="text" placeholder="text type" />
<input type="email" placeholder="email type" />
<input type="password" placeholder="password type" />
<label>
  checkbox
  <input type="checkbox" />
</label>
<label>
  radio
  <input type="radio" />
</label>
<input type="date" />
<input type="color" />
```

```css
/* type 속성을 가진 모든 요소에 적용 */
[type] {
  ...;
}
```

`[attr="value"]`: 값이 정확히 `value`이고 속성 이름이 `attr`인 요소에만 적용한다

```html
<input type="text" placeholder="text type" />
<input type="email" placeholder="email type" />
<input type="password" placeholder="password type" />
<label>
  checkbox
  <input type="checkbox" />
</label>
<label>
  radio
  <input type="radio" />
</label>
<input type="date" />
<input type="color" />
```

```css
/* type="text"를 가진 모든 요소에 적용된다 */
[type="text"] {
  ...;
}
```

`[attr~="value"]`: 값이 공백으로 구분된 단어 목록이고, 그 중 하나가 정확히 `value`이고 속성 이름이 `attr`인 요소에만 적용한다

```html
<input type="text" placeholder="text type" />
<input type="email" placeholder="email type" />
<input type="password" placeholder="password type" />
<label>
  checkbox
  <input type="checkbox" />
</label>
<label>
  radio
  <input type="radio" />
</label>
<input type="date" />
<input type="color" />

<p lang="en-us en-ca fr-ca">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Rerum ex temporibus,
  possimus id, asperiores nulla ab. Blanditiis corrupti, iure. Illum labore quod
  autem, exercitationem quaerat provident consequatur cupiditate at. Quas?
</p>
```

```css
/* lang 속성에 en-ca값을 가진 모든 요소에 적용 */
[lang="en-ca"] {
  ...;
}
```

`[attr^="value"]`: 속성 이름이 `attr`이고 그 값이 `value`로 시작하는 요소에만 적용된다

```html
<input type="text" placeholder="text type" />
<input type="email" placeholder="email type" />
<input type="password" placeholder="password type" />
<label>
  checkbox
  <input type="checkbox" />
</label>
<label>
  radio
  <input type="radio" />
</label>
<input type="date" />
<input type="color" />
```

```css
/* type속성의 값이 c로 시작하는 모든 요소에 적용된다 */
[type^="c"] {
  ...;
}
```

`[attr$="value"]`: 속성 이름이 `attr`이고 그 값이 `value`로 끝나는 요소에만 적용된다

```html
<input type="text" placeholder="text type" />
<input type="email" placeholder="email type" />
<input type="password" placeholder="password type" />
<label>
  checkbox
  <input type="checkbox" />
</label>
<label>
  radio
  <input type="radio" />
</label>
<input type="date" />
<input type="color" />
```

```css
/* type속성의 값이 d로 끝나는 모든 요소에 적용된다 */
[type$="d"] {
  ...;
}
```
