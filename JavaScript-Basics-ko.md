# JavaScript 기초 정리

비전공 입문자를 위한 자바스크립트 기초 정리.

<br>

## 목차

1. [소개](#intro)
2. [1부 - 데이터 타입](#data-type)
3. [2부 - 데이터 조작](#data-manipulation)
   - 수학
   - 텍스트
   - 배열
   - 객체
4. 3부 - DOM 조작 (작성중)
5. 4부 - 함수 (작성중)
6. 5부 - API 사용 (작성중)

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