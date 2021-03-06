# JavaScript 기초 정리

비전공 입문자를 위한 자바스크립트 기초 정리.

<br>

## 목차

1. [소개](#intro)
2. [1부 - 데이터 타입](#data-type)
3. [2부 - 데이터 조작](#data-manipulation)
4. [3부 - DOM 조작](#dom-manipulation)
5. [4부 - 루프(Loops)](#loops)
6. [5부 - 조건문/비교 연산](#conditionals)
7. [6부 - 함수](#function)
8. 7부 - API 사용 (작성중)

---

<h2 id="intro">소개</h2>

자바스크립트는 웹 사이트를 동적으로 만들어주는 웹 개발 언어입니다.  
브라우저에서 실행되고, 주로 DOM을 조작할때 사용합니다.

자바스크립트는 `<script>` 요소나 `.js` 파일로 사용할수있습니다.  
`.js` 파일을 사용하려면 `<link href='script.js'>` 로 HTML 파일과 연결할수 있습니다.

어떤 방법을 사용하던 자바스크립트는 HTML의 바디 마지막에 사용하는것을 추천합니다.

```html
    <script>
        ...
    </script>
</body>
</html>

-----------------------------------------

    <script href="script.js">
</body>
</html>
```

다른 프로그래밍 언어들처럼 자바스크립트도 여러 버전들을 거쳐왔습니다.  
현재 자바스크립트의 버전은 ECMAScript 2021 으로 2021년 6월에 릴리스 됐습니다.  
저는 현재 버전인 ECMAScript 2021을 기준으로 정리해 보았습니다.

<br>
<br>
<br>

<h2 id="data-type">1부 - 데이터 타입</h2>

자바스크립트에서는 여러 종류의 데이터 타입들을 사용할수 있습니다.  
데이터 타입을 알아보기전 어떻게 사용할수 있는지 알아보겠습니다.

자바스크립트에는 다른 언어들처럼 변수라는 것이 있습니다.  
변수는 어떤 데이터를 담는 컨테이너라고 생각하시면 됩니다.  
이 변수를 사용해서 여러 데이터들을 사용해서 여러가지 기능들을 만들수 있습니다.

변수는 `let` 과 `const` 를 사용해서 만들수 있습니다.

<br>

`let` 은 변수의 값을 바꿀수는 있지만 같은 변수를 재선언할수는 없습니다.

```js
let x = 10;

x = 20; //✔변수 값 변경 가능

let x = 20; //❌변수 재선언 불가능
```

<br>

`const` 는 변수의 값을 바꾸거나 재선언은 불가능하지만  
상수 배열의 요소 변경,  
상수 객체의 속성 변경 은 가능 합니다

```js
const PI = 3.14159265359;
PI = 3.14; //❌변수 값 변경 불가능
const PI = 3.14; //❌변수 재선언 불가능

const fruits = ["apple", "banana", "kiwi"];
fruits[0] = "orange"; //✔상수 배열 요소 변경 가능
fruits = ["orange", "pineapple", "melon"]; //❌상수 배열 요소 재선언 불가능

const car = { brand: "Audi", color: "black", type: "sedan" };
car.color = "white"; //✔상수 객체의 속성 변경 가능

car = { brand: "Kia", color: "white", type: "coupe" }; //❌상수 객체 재선언 불가능
```

<br>
<br>

데이터 타입 종류들

- 숫자
- 텍스트
- 객체
- 배열

<br>
<br>

**숫자**  
숫자는 정수(1, 2, 3, 4, 5 ...)와 소수점(0.2, 3.3, 4.4 ...) 모두 사용 가능합니다.

```js
let x = 10; //정수
let xa = -10; //정수

let y = 10.0; //소수점
let ya = -10.0; //소수점
```

<br>

**텍스트**  
텍스트는 `''` 또는 `""` 로 작성합니다.

```js
let name = '아무개';
let address = "서울 어딘가";
```

<br>

**객체**  
객체, 오브젝트(object), 는 여러 속성을 하나의 변수에 저장하는 데이터 형식입니다.  
주로 물건, 사람 같은 어떠한 형체를 데이터화 할때 사용합니다.  
객체 속성의 값으로 숫자, 텍스트, 배열, 또는 객체를 사용할수 있습니다.  
객체는 `{}` 를 사용해서 만들수 있습니다.

```js
let book = {
  title: "",
  author: {
    name: "",
    books: [],
  },
  iso: "",
  year: "",
  pages: 0,
};
```

<br>

**배열**  
배열은 여러개의 데이터를 하나의 변수에 저장하는 데이터 형식입니다.  
언뜻 들으면 객체와 비슷하지만, 객체에는 속성이 존재한다면 배열은 인덱스를 사용합니다.  
배열은 한 데이터 타입을 여러개 저장하거나, 여러 데이터 타입을 여러개 정장할수이 있습니다.  
배열에 배열을 저장할수도 있습니다.
배열은 `[]`을 사용해서 만들수 있습니다.

```js
//한가지 데이터 타입 배열
let numbers = [1, 2, 3, 4, 5, 6, 7, 8];

//여러 데이터 타입 배열
let mixed = [
  123, //숫자
  "hello", //텍스트
  { brand: "Samsung", product: "mobile", model: "Galaxy", price: 400000 }, //객체
  [4, 5, 6, 7, 8], //배열
];
```

<br>
<br>
<br>

<h2 id="data-manipulation">2부 - 데이터 조작</h2>  

**수학**  
자바스크립트에서는 간단한 산수부터 좀더 복잡한 수학까지 여러 공식들을 사용할수 있습니다.  
수학 공식은 `Math` 클라스를 이용해 사용할수있습니다.  
이 클라스는 자바스크립트에 기본으로 포함되있습니다.  

```js
// 간단한 산수
10 + 10
10 - 10
10 * 10
10 / 10
10 % 2 // 모듈로는 나눗셈의 나머지를 돌려줍니다

// 지름 공식
let circle = 10 // 원주
let diameter = cirle / Math.PI // 원의 지름 3.18

// 루트
Math.sqrt(64) // 64의 루트인 8을 돌려줍니다

// 사인
Math.sin(90 * Math.PI / 180) // 90도 각도의 사인값(1)을 돌려줍니다

// 반 올림/내림
Math.round(4.9) // 5로 반올림 합니다
Math.round(4.4) // 4로 반내림 합니다

// 반 올림
Math.ceil(4.9) // 5로 반올림 합니다
Math.ceil(4.5) // 5로 반올림 합니다
Math.ceil(4.3) // 5로 반올림 합니다

// 반 내림
Math.ceil(4.9) // 4로 반내림 합니다
Math.ceil(4.5) // 4로 반내림 합니다
Math.ceil(4.3) // 4로 반내림 합니다
```

자세한 정보는 [W3School 에서 확인할수 있습니다](https://www.w3schools.com/js/js_math.asp)  

<br>

**텍스트**  
텍스트(스트링)의 정확한 데이터 타입은 캐릭터배열 입니다.  
즉 `Hello` 는 `['H', 'e', 'l', 'l', 'o']` 를 합친 결과입니다.  
그래서 배열에 사용할수있는 함수들을 텍스트에도 사용할수 있습니다.  
이 섹션에서는 텍스트에만 적용되는 조작법들을 알아보겠습니다.  
*배열관련 함수들은 아래 배열에서 확인할수 있습니다.*  

```js
let str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

// 부분 문자열
str.substring(x, y) // x=시작점, y=끝나는점
str.substring(3, 6) // DEF

str.substr(x, y) // x=시작점, y=부분 문자의 길이
str.substr(3, 6) // DEFGHI

// 문자 바꾸기
str.replace(x, y) // x=바꾸려는 문자, y=새로운 문자
str.replace("DEF", "888") // ABC888GHIJKLMNOPQRSTUVWXYZ

// 대/소문자
str.toUpperCase() // 대문자로
str.toLowerCase() // 소문자로

// n의 위치에 있는 글자
str.charAt(x) // x=위치(인덱스)
str.charAt(4) // E

// n의 위치에 있는 글자의 코드
str.charCodeAt(x) // x=위치(인덱스)
str.charCodeAt(6) // 71(G). 이 코드는 ASCII 코드입니다

// 텍스트 나누기
str.split(x) // x=구분자
let txt = "Hello World, this is some text"
txt.split(" ") // ['Hello', 'World,', 'this', 'is', 'some', 'text']
```

자세한 정보는 [W3School 에서 확인할수 있습니다](https://www.w3schools.com/js/js_string_methods.asp)  

<br>

**배열**  
배열은 인덱스를 사용합니다.  
배열의 인덱스는 0 에서 시작합니다.  
```js
//배열:   ["Banana", "Orange", "Apple", "Mango"]
//인덱스: [    0        1         2        3   ]
```

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[2] // Apple

// 배열을 텍스트로
fruits.toString() // Banana,Orange,Apple,Mango

// 배열을 텍스트로 (구분자 사용)
fruits.join("*") // Banana*Orange*Apple*Mango

// 배열에 추가하기 (뒤에)
fruits.push("Kiwi") // ["Banana", "Orange", "Apple", "Mango", "Kiwi"]

// 배열에 추가하기 (앞에)
fruits.unshift("Melon") // ["Melon", "Banana", "Orange", "Apple", "Mango", "Kiwi"]

// 배열에서 빼내기 (뒤에서)
fruits.pop() // Kiwi - ["Melon", "Banana", "Orange", "Apple", "Mango"]

// 배열에서 빼내기 (앞에서)
fruits.shift() // Melon - ["Banana", "Orange", "Apple", "Mango"]

// 배열속 요소 바꾸기
fruits[0] = "Pear" // ["Pear", "Orange", "Apple", "Mango"]

// 배열에 원하는 위치에 추가하기
fruits.splice(2, 0, "Lemon", "Pineapple") // ["Pear", "Orange", "Lemon", "Pineapple", "Apple", "Mango"]
// 첫번째 매개변수 2는 추가할 위치
// 두번째 매개변수 0은 지울 배열요소의 수
// 나머지 ("Lemon", "Pineapple")은 새로 추가되는 요소들

// 배열 자르기
// ["Pear", "Orange", "Lemon", "Pineapple", "Apple", "Mango"]
fruits.slice(x, [y]) // x=인덱스/시작점, y=끝나는점
fruits.slice(2) // ["Lemon", "Pineapple", "Apple", "Mango"]
fruits.slice(2, 4) // ["Lemon", "Pineapple"]

// 두번째 매개변수를 제공하지 않으면 그 인덱스부터 끝까지 잘라냄니다
// 두번째 매개변수를 제공하면 첫번째 인덱스부터 두번째 인덱스까지 (두번째 인덱스는 포함안됨) 잘라냄니다
```

자세한 정보는 [W3School 에서 확인할수 있습니다](https://www.w3schools.com/js/js_array_methods.asp)  

<br>

**객체**  
객체는 키-값 데이터 타입이라고도 합니다.  
키는 속성을 뜻합니다.  
객체 속성을 사용하는 방법은 두가지입니다.  
```js
const car = {
  brand: "Fiat",
  model: "500",
  color: "white"
}

car.brand // Fiat
car["brand"] // Fiat

// 객체 속성의 값 바꾸기
car.brand = "Kia"
car.model = "K5"
car // {brand: "Kia", model: "K5", color: "white"}
```

<br>
<br>
<br>

<h2 id="dom-manipulation">DOM 조작</h2>  

HTML이 브라우저에 로드되면 브라우저는 DOM(Document Object Model)을 만듭니다.  
DOM은 자바스크립트로 동적인 HTML을 만드는데 필요한 모든 기능을가지고 있습니다.  
`document`를 통해 HTML요소들에 접근할수있습니다.  

```js
// HTML요소 찾기
document.getElementById() // 요소의 id를 사용 document.getElementById('container') => div#main
document.getElementsByClassName() // 요소의 class를 사용, 같은 class를 가진 모든 요소들을 배열형태로 반환
// document.getElementsByClassName('left') => [div.left, div.left, div.left]

document.getElementsByTagName() // 요소의 태그 이름을 사용, 주어진 모든 태그를 배열형태로 반환
// document.getElementsByTagName('p') => [p.intro, p, p, p, p, p]

document.querySelector() // CSS 선택자를 사용; 선택자에 맞는 첫번째 요소를 반환 
// document.querySelector('.left') => div.left

document.querySelectorAll() // CSS 선택자를 사용; 선택자에 맞는 모든 요소들을 배열형태로 반환 
// document.querySelectorAll('.left') => [div.left, div.left, div.left, div.left]

// HTML 요소 만들기
document.createElement() // 태그 이름을 사용해서 요소를 만듬
document.createElement('p') // <p></p>
document.createElement('div') // <div></div>

// HTML 요소 추가하기
let div = document.createElement('div')
let p = document.createElement('p')
div.appendChild(p) // <div> <p></p> </div>

// HTML 요소 지우기
let img = document.querySelector('img')
img.remove()

// HTML 자녀 요소
let header = document.querySelector('header')
let children = header.children // 요소의 직속 자녀(들)을 배열형태로 반환

// HTML 요소 내용 가져오기
let div = document.querySelector('div')
div.innerHTML // div 안의 모든 HTML을 텍스트형태로 반환
div.innerText // div 안의 모든 텍스트를 텍스트형태로 반환
div.innerHTML = "<a href='...'>link</a>" // <div> <a href='...'>link</a> </div>
div.innerText = "some random text" // <div> some random text </div>

// HTML 요소 스타일
// style 속성
document.querySelector('h2').style // 모든 스타일을 객체형태로 반환
document.querySelector('h2').style.fontSize // 폰트 사이즈를 반환
document.querySelector('h2').style.fontSize = "20px" // 폰트 사이즈를 20px으로 지정

// CSS 스타일
let h2 = document.querySelector('h2')
let styles = window.getComputedStyle(h2)
styles.fontSize // 폰트 사이즈를 반환
styles.color // 폰트 색상을 반환

// 부모 요소
let a = document.querySelector('.link')
a.parentNode

// 형제 요소
document.querySelector('li').nextElementSibling //오른쪽 형제 요소
document.querySelector('li').previousElementSibling // 왼쪽 형제 요소

// 요소 class/id
document.querySelector('a').id // id 확인
document.querySelector('a').id = "main-button" // id 지정


document.querySelector('a').className // class 확인
document.querySelector('a').className = "mystyle" // class 지정
document.querySelector('a').className = "mystyle" // class 지정
document.querySelector('a').classList.add() // 한개 이상의 class를 지정 
// classList.add('myclass'), classList.add('myclass', 'dark-mode')

document.querySelector('a').classList.remove() // 요소에서 한개 이상의 class 빼기 
// classList.remove('myclass'), classList.remove('myclass', 'dark-mode')
```

자세한 정보는 [W3School 에서 확인할수 있습니다](https://www.w3schools.com/jsreF/dom_obj_all.asp)

<br>
<br>
<br>

<h2 id="loops">루프(Loops)</h2>  

루프는 조건에 따른 반복 작업을 수행할때 사용되는 간단한 알고리즘 입니다.  
루프는 주어진 조건이 충족됬을때 종료합니다.  
자바스크립트에는 4가지의 루프들이 존재합니다  
- [for loop](#for)
- [while loop](#while)
- [for in loop](#forin)
- [for of loop](#forof)
- [do while loop](#dowhile)

---

<h3 id="for">for loop</h3>  

`for` 루프의 조건은 횟수 입니다.  
이 루프는 `루프 컨트롤 변수`, `루프 조건`, 그리고 `증가/감소 조건`을 사용해 주어진 작업을 반복적으로 수행합니다.  

```js

// for 루프 작성법
   /*루프 컨트롤 변수     루프 컨트롤 변수     증가 조건*/
for (let i = 0;           i < 10;             i++) /*루프 선언문*/ 
{ /*루프 바디*/

  // 수행할 작업
  console.log(i)
}

++ 는 하나씩 증가. i = i + 1 과 같음

output:
0
1
2
3
4
5
6
7
8
9

// 배열 사용
let links = document.querySelectorAll('a') // 모든 링크 요소들
for(let i = 0; i < links.length; i++) {
  
  // links[i]
}
```

**루프 설명**  

| 반복 횟수 | i | i++ | 조건 충족 |
|---|---|---|---|
| 1 | 0 | 1 | ✔ 계속 |
| 2 | 1 | 2 | ✔ 계속 |
| 3 | 2 | 3 | ✔ 계속 |
| 4 | 3 | 4 | ✔ 계속 |
| 5 | 4 | 5 | ✔ 계속 |
| 6 | 5 | 6 | ✔ 계속 |
| 7 | 6 | 7 | ✔ 계속 |
| 8 | 7 | 8 | ✔ 계속 |
| 9 | 8 | 9 | ✔ 계속 |
| 10 | 9 | 10 | ❌ 끝 |

---

<h3 id="while">while loop</h3>  

`while` 루프의 조건은 조건의 값 입니다.  
조건의 값이 `true` 일 경우에만 작동합니다.  
`while` 루프의 종료는 주어진 조건이 `false` 일때입니다.  
`for` 루프와 비슷해 보이지만, `while` 루프의 루프 컨트롤은 루프 내에서 수동으로 변경되고  
`for` 루프의 경우 루프 컨트롤은 루프 선언문에서 자동으로 변경됩니다

**_NOTE_**  
조건의 값이 항상 `true` 일 경우 `while` 루프는 무한대로 실행되며 프로그램을 충돌시킵니다.  

```js
// while 루프 작성법
let i = 0
while(i < 10) {

  // 루프 컨트롤 변경
  i++
}

// 배열 사용
let links = Array.from(document.querySelectorAll('a')) // 모든 링크 요소들
while(links.length)
{
  let node = links.shift() // links 에서 첫번째 요소 꺼내오기

  ...
}
```

**배열 사용 설명**  

프로그래밍에서 `0` 은 `false` 와 같은 의미입니다.  
루프의 바디에서 `links.shift()` 로 `links` 배열의 첫번째 요소를 꺼내면  
`links` 의 길이는 하나 감소합니다.  
이렇게 반복적으로 `links` 배열에서 요소를 꺼내면 언젠가는 `links` 배열의 길이는 `0` 이되고  
그러면 `while` 루프의 조건은 `false` 가 되며, 그때 루프는 종료됩니다.  

예시:  
```js
let links = Array.from(document.querySelectorAll('a'))
links.length // 5
```

| `link` 길이 | `links.shift()` | `links` 길이 | 조건 충족 |
|---|---|---|---|
| 5 | 5 - 1 | 4 | ✔ 계속 |
| 4 | 4 - 1 | 3 | ✔ 계속 |
| 3 | 3 - 1 | 2 | ✔ 계속 |
| 2 | 2 - 1 | 1 | ✔ 계속 |
| 1 | 1 - 1 | 0 | ❌ 끝 |

---

<h3 id="forin">for in loop</h3>  

`for in` 루프는 `for`, `while` 과는 다르게 객체 속성을 반복할때 사용됩니다.  
객체의 마지막 속성에 다다르면 루프는 종료됩니다.  

```js
let object = {
  a: 1,
  b: 2,
  c: 3,
  d: 4
}

for(const key in object) {
  console.log(key + "::" + object[key])
}

output:
a::1
b::2
c::3
d::4
```

---

<h3 id="forof">for of loop</h3>  

`for of` 는 반복 가능한 객체, 즉 배열, 스트링, 맵, 노드리스트 같은 배열 형태에 사용됩니다.  

```js
let links = document.querySelectorAll('a')

for(const link of links) {
  console.log(link.href)
}

let str = "hello"
for(const letter of str) {
  console.log(letter)
}

output:
h
e
l
l
o
```

---

<h3 id="dowhile">do while loop</h3>  

`while` 루프와 비슷하지만 다른점은 루프 내의 작업 실행 순서 입니다.  
`while` 루프 플로우:  
조건 확인 -> 조건 충족 -> 작업 실행 -> 반복  
&nbsp; &nbsp; &nbsp; &nbsp; ↪  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 조건 미충족 -> 루프 종료  
`do while` 루프 플로우:  
작업 실행 -> 조건 확인 -> 조건 충족 -> 반복  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ↪ &nbsp; &nbsp; &nbsp; &nbsp; 조건 미충족 -> 루프 종료  

```js
let i = 0
let result = []
do {
  result.push(i**2) // i의 제곱
  i++
} while(i < 0)

console.log(result) // [0]
```

조건이 처음부터 충족되지 않음에도 `result` 에 `0` 이 추가되었습니다.  
이것을 `while` 루프로 해보면  

```js
let i = 0
let result = []
while(i < 0) {
  result.push(i**2)
  i++
}

console.log(result) // []
```

조건이 먼저 확인되면서 조건이 충족되지 않는게 확인, `result` 에는 아무것도 추가되지 않습니다.  

<br>
<br>
<br>

<h2 id="conditionals">조건문/비교 연산</h2>  

**조건문**  

조건문은 말 그대로 조건에따라 작업을 실행할때 사용됩니다.  
조건은 만드는 방법은  

1. `true/false` 값을 사용
2. 비교 연산을 사용

이렇게 두가지 방법이 있습니다.  

<br>
<br>

```js
// 조건문 if...else
if(true) {
  console.log('true')
} else {
  console.log('false')
}
output: true


if(5 > 3) {
  console.log('true')
} else {
  console.log('false')
}
output: true


const user = {
  username: 'iamuser',
  isAdmin: false
}

if(user.isAdmin) {
  console.log('true')
}else {
  console.log('false')
}
output: false
```

`if` 는 주어진 조건이 `true` 일때 실행됩니다.  
`else` 는 if 의 조건이 `false` 일때 실행됩니다.  

`if`의 조건에는 주로 비교 연산을 같이 사용합니다.  

<br>
<br>

```js
// 조건문 switch
let val = 5

switch(val) {
  case 5:
    console.log("correct")
    break;
  case 10:
    console.log("wrong")
    break;
  default:
    console.log("unknown")
}
output: "correct"


val = '5'

switch(val) {
  case 5:
    console.log("correct")
    break;
  case 10:
    console.log("wrong")
    break;
  default:
    console.log("unknown")
}
output: "unknown"
```

`switch` 는 주어진 조건에 맞는 케이스의 작업을 실행합니다.  
`default` 는 맞는 케이스가 없는경우 실행됩니다.  
케이스는 항상 `break` 로 끝나야 합니다. 그렇지 않으면 `break` 가 있는 케이스를 만날때까지 각 케이스의 작업을 실행순서대로 실행합니다.  

```js
let val = 5

switch(val) {
  case 5:
    console.log("correct")
  case 10:
    console.log("wrong")
    break;
  default:
    console.log("unknown")
}
output: "correct wrong"
``` 

---

**비교 연산**  

비교 연산은  

* equal (==/===) (동일 비교 연산)
* not equal (!=/!==) (비동일 비교 연산)
* greater than (>)
* greater than or equal (>=)
* less than (<)
* less than or equal (<=)
* and (&&)
* or (||)
* not (!)

이렇게 9가지가 있습니다.  

`==` vs `===`  
`==` 은 좌우를 같은 타입으로 변환해서 비교합니다. 타입 변환후 값이 같으면 `true` 를 반환합니다.  

```js
5 == '5' => true
```  

<br>

`===` 은 좌우의 타입을 변환하지 않습니다. 오직 타입과 값이 같을경우에만 `true` 를 반환합니다.  

```js
5 === '5' => false  
```

<br>

`!=` 와 `!==` 은 비동일 연산으로 좌우가 다를때 `true` 를 반환합니다.  

```js
4 != 5 => true  
5 !== '5' => true
```

<br>

`&&` 연산  

* `true && true` => true
* `true && false` => false
* `false && true` => false
* `false && false` => false

<br>

`||` 연산  

* `true || true` => true
* `true || false` => true
* `false || true` => true
* `false || false` => false

<br>

`!` 연산  

* `!true` => false
* `!false` => true

<br>
<br>
<br>

<h2 id="function">함수</h2>  

함수는 여러 단계를 거치는 작업을 하나의 명령으로 묶는 방법입니다.  
함수를 만들때 기억해야할 두가지는  

- 함수는 한가지 작업만 합니다
- 함수는 재사용할수 있어야합니다

첫번째, 함수는 한가지 작업만 한다  
말 그대로 입니다  
예를들어 초를 시간(시, 분)으로 계산하는 함수가 있다고 해볼께요  
그러면 이 함수내의 작업은 초를 시,분 계산만해야지  
날짜계산도하면 두가지 작업을 하게되는거죠  

<br>

두번째, 함수는 재사용할수 이어야한다  
위 시간를 계산하는 함수를 다시 예로 들어보자면  
함수를 여러번 다른값으로 사용할수있어야 합니다  
좀더 쉽게 설명하자면 이 함수를 사용해서 300초, 5894초, 102938초, 등등  
이렇게 여러번 다른값으로 사용할수있어야 합니다  

<br>

그러면 이제 함수를 만드는 방법을 알아봐야겠죠  
함수를 작성하는 방법은 두가지 입니다  

```js
// 함수 작성법 1번 - 네임드(Named) 함수
function add(a, b) {
  let total = a + b
  return total
}

// 함수 작성법 2번 - 애로우(Arrow) 함수
const add = (a, b) => {
  let total = a + b
  return total
}
```

`네임드` 을 살펴보면  
`function` 은 자바스크립트의 키워드로 함수를 만들때 사용합니다  
`add` 는 함수 이름입니다  
`(a, b)` 는 함수가 받아 사용할수있는 값(들) 입니다  
만약 함수에 값이 필요없는경우 그냥 `()` 이렇게  
만약 함수가 하나의 값만 사용하면 `(a)` 이렇게 작성하면 됩니다  
`{   }` 안에는 함수가 실행해야할 작업을 작성합니다  
`return` 은 결과를 반환하는 키워드 입니다  
함수가 결과를 반환하지않는경우 사용하지 않습니다  

<br>

`애로우` 을 살펴보면  
`add` 는 함수 이름입니다  
`=` 는 변수를 만들때 봤던것과 같은 할당 연산자 입니다  
`(a, b)` 는 함수가 받아 사용할수있는 값(들) 입니다  
`=>` 는 함수를 만드는 연산자로 ES6에서 새로 소개되었습니다  
`{   }` 안에는 함수가 실행해야할 작업을 작성합니다  
`return` 은 결과를 반환하는 키워드 입니다  
함수가 결과를 반환하지않는경우 사용하지 않습니다  

<br>

그러면 `네임드` 와 `애로우` 의 차이점은 뭘까요?  
차이점은 `this` 키워드입니다  
`this` 는 함수를 실행시킨 객채를 가르키는 키워드입니다  
이 키워드가 기본적으로 가르키는 객채는 최상위에있는 객채로써  
브라우저에서는 `window` 객채를 가르키고, NodeJS 에서는 `global` 객채를 가르킵니다  

<br>

`네임드` 함수에서 사용되는 `this` 키워드는 함수의 문맥에따라  
가르키는 객채가 달라집니다  

```js
function foo() {
  console.log(this) // window
}

let person = {
  name: 'Bob',
  sayHello: function(){
    console.log(this) // person{name: 'bob', sayHello: function}
  }
}
// sayHello 는 객채함수입니다

let person = {
  name: 'Bob',
  languages: ['C++', 'Python', 'JavaScript', 'Java'],
  sayHello: function(){
    console.log(this) // {name: 'bob', sayHello: sayHello()}
  },
  iKnow: function() {
    this.languages.forEach(function(lang) {
      console.log(this) // window
    })
  }
}
// forEach() 에서 실행된 function(lang){} 은 이름없는 함수입니다.
// 이름없는 함수는 최상위 객채에서 실행됨으로 여기서 this는 window가 됩니다
```

`애로우` 함수에서 사용되는 `this` 키워드는 렉시컬(lexical) 스콥으로  
가르키는 객채가 달라집니다  
렉시컬 스콥을 쉽게 이해하는 방법은 건물을 생각해보면 되겠습니다  
건물의 1층이 실행된 함수이고 위로 올라갈수록 글로벌 객채에 가까워지는거죠  
한층 한층 가면서 `this` 가 있는지 확인하고 없으면 다음층으로 올라가는   
그래서 결국엔 글로벌 객채까지 가게됩니다  

```js
let foo = () => {
  console.log(this) // window
}

let person = {
  name: 'Bob',
  sayHello: () => {
    console.log(this) // window
    // 사실 애로우 함수의 사용 용도 한계중 하나가 객채함수로 사용하지 않는것입니다
    // 이 예시는 사실 틀린 예시입니다
  },
  iKnow: function() {
    this.languages.forEach((lang) => {
      console.log(this) // {name: 'Bob', sayHello: sayHello(), iKnow: iKnow()}
    })
  }
}
```