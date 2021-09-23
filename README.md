# JavaScript_nomadcoders
# 노마드코더 자바스크립트 강의

## 항상 끝에 **;** 기억

### 변수 상수
```javascript
const a = 5; // 변하지 않는 값
let b = 5; // 변해도 되는 값
```

### 콘솔
```javascript
console.log(); // 콘솔에 띄워줌
```
log는 print랑 똑같이 생각하면 됨

### 배열(Array)
```javascript
const dayOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"];
console.log(dayOfWeek); // 콘솔에 배열인 dayOfWeek가 출력

// 배열 안에 있는 것을 출력하고 싶으면
console.log(dayofWeek[4]);  // 배열에서 fri이 출력

// 배열 안에 값을 추가하려면
dayOfWeek.push("sun");  // "sun" 추가

// 추가 됬는지 확인해보면
console.log(dayOfWeek); // ["mon", "tue", "wed", "thu", "fri", "sat", "sun"]
```
**여기서 궁금한 점 const는 상수이기 때문에 값을 변경할 수 없는데 왜 배열에서 const를 사용해도 추가가 될까?**

이것을 이해하기 위해서 하나의 박스를 생각하시면 좋을 것 같습니다.
예를 들어 const a = 2; 이렇게 있으면 a = 4; 이렇게 바꾸는건 안됩니다.
하지만 배열과 같은 경우에는 내용물 안의 요소들은 변경이 가능합니다.
이게 박스로 생각하면 const daysOfWeek = ["mon", "tue", "wed", "thu", "fri", "sat"]; 이렇게 선언을 하면 이후에 daysOfWeek = ["hi"]; 이렇게 수정하는건 불가능합니다. 
왜냐하면 박스 그 통째로 바꾸려고 하기 때문입니다.
하지만 그 박스 안의 내용물들을 추가하거나 삭제할 수는 있습니다.

### Objects
object는 property를 가진 데이터를 저장해주며, { } 를 사용한다.
property를 불러오는 방법은 2가지가 있다.
1. console.log(player.name); => "mango"
2. console.log(player["name"]); => "mango"
```javascript
const player = {
  name: "mango",
  color: "orange",
  food: true,
};

console.log(player);
// property를 변경하거나 추가하는 방법
// 변경
player.color = "yellow";
console.log(player.color);
// 추가
player.price = 5000;
console.log(player.price);
```

**중요!!**
설명이 필요하지 않은 데이터 리스트들은 array로,
설명이 필요한 정보가 담긴 데이터 리스트들은 object로!

### 함수(function)
console.log() 와 같은 기능
function 명을 설정하고 그 안에 코드를 여러게 넣고 function 이름 설정한 것을 호출하면 안에 있던 코드가 다 실행됨
```javascript
// 이름
function sayHello(name, age) {
  console.log("Hello my name is" + name + " and I'm " + age);
}
sayHello("mingu", 21);

// 더하기와 나누기
function plus(a, b) {
  console.log(a + b);
}
plus(5, 3);

function divide(a, b) {
  console.log(a / b);
}
divide(10, 2);
```

**Object 안에서 function 실행 방법**
예시
```javascript
const player = {
  name: "mingu",
  // 밑에 부분
  hello: function (otherName) {
    console.log("hi " + otherName);
  },
};

console.log(player.name);
player.hello("bu");  // => hi bu
```

### return
함수(function) 안에서 return 이용법
위에서는 함수인에 console.log()을 사용하여 출력을 하였다.
이번에는 console.log()를 쓰지 않고 return을 사용하여 출력할 것이다.
```javascript
const calculator = {
  add: function (a, b) {
    return a + b;
  },
  minus: function (a, b) {
    return a - b;
  },
  divide: function (a, b) {
    return a / b;
  },
  multiply: function (a, b) {
    return a * b;
  },
  square: function (a, b) {
    return a ** b;
  },
};

const plusResult = calculator.add(2, 3);
const minusResult = calculator.minus(plusResult, 10);
const multiplyResult = calculator.multiply(10, minusResult);
const divideResult = calculator.divide(multiplyResult, plusResult);
const squareResult = calculator.square(divideResult, minusResult);
```
function안에서 return과 추가작업을 입력하면 return만 작업하고 추가 수행은 이뤄지지 않는다.
만약 return 앞에 기타작업이 있다면 이 작업은 수행된다.
즉, "return"까지만 수행된다.

### 조건문(if-else)

```javascript
// prompt() = alert처럼 창을 띄운 후 입력 받을 수 있게 하는 함수
const age = parseInt(prompt("몇 살이야?"));
// parseInt() = String을 num으로 전환시키는 함수(String(숫자만 처리가능))
console.log(isNaN(age));
// isNaN() = 이 함수를 사용하면 boolean으로 알려줌 true와 false를 반환
// NaN(Not a Number)이 아니면 false 맞으면  true

if (isNaN(age)) { // true
  console.log("숫자만 써줘");
} else {  // false
  console.log("고마워");
}
```

나이를 입력받는 프로그램

```javascript
const age = parseInt(prompt("나이를 입력하세요"));

if (isNaN(age) || age < 0) { //  OR 연산자 = ||
  console.log("양의 숫자를 입력하세요");
} else if (age < 18) {
  console.log("너무 어려");
} else if (age >= 19 && age <= 50) { // AND 연산자 = &&
  console.log("술을 마실 수 있는 나이");
} else {
  console.log("몸 관리에 신경써야하는 나이 입니다.");
}
```

AND 연산자는 둘 다 true이면 true가 되고,
OR 연산자는 둘 중 하나만 true이면 true가 된다.
OR 연산자가 false가 되려면은 둘 다 false가 되어야한다. 


age === 100 // age가 100랑 같다면
age !== 100 // age가 100이 아니라면
이 추가된 코드
```javascript
else if (age === 100) { // 값이 같다는 것을 확인 할 때 ===
  console.log("와우");
}
```

### document
document는 모든 것의 시작점이라고 생각하면 됨
document는 JavaScript에서 HTML에 접근할 수 있는 방법
이번 시간에 짧게 배운 것
```javascript
document.title  // HTML에 있는 title의 값을 불러옴
document.title = "HI" // HTML에 있는 title 수정
```
document 함수에 있는 getElementByID()를 사용하면 HTML에서 id를 통해 Element를 찾아줌
console.log() 함수보다 더 자세하게 보여주는 함수 console.dir()이 있다.
```javascript
const title = document.getElementById("title");

console.log(title);
console.dir(title);

title.innerText = "Got you";  // HTML에 있는 title이란 id를 가진 텍스트를 변경
// element를 더 자세하게 보여주는 console.dir()
```

### querySelector
querySelector은 Element를 css 방식으로 검색할 수 있다.
querySelector은 하나의 Element만 가져올 수 있고
querySelectorAll은 같은 class의 tag가 있거나 같은 아이디가 있으면 배열로 전부 가져올 수 있다.

예를 들어 const title = document.querySelector(".hello h1"); = hello란 클래스 안에 h1 Tag를 가져오고
class가 아니라 id라면 #id이름 을 사용하면 첫 번째 Element만 가져온다.

document.querySelector(“#hello”);
document.getElementById(“hello”);
위에 id를 찾는 코드는 같지만 getElementById은 하위요소를 가져오지 못한다.

### Events
```javascript
const title = document.querySelector("div.hello:first-child h1");
// HTML에 있는 id의 하위 요소를 title에 저장시킴
function handTitleClick() {
  console.log("title was clicked!");
  title.style.color = "blue";
}
// 함수를 만듬
title.addEventListener("click", handTitleClick);
// title를 클릭하면 이벤트를 발생시켜 handTitleClick이라는 함수를 호출시킴
```
JavaScript가 document로 html을 불러올 수 있고 수정 추가도 가능하다.

1.불러오는 함수
querySelector / querySelectorAll 이 유용하다.
2. 사용자의 Event를 listen해서 반응
addEventListener("event", function);
**이때 function에 실행 하는 () 기호는 쓰지 않는다. 우리가 원하는 것은 이벤트 발생 시 함수가 실행되는 것이기 때문에 ()를 임의로 사용하면 이벤트 발생 전에 실행된다.**
3. 바꿀 수 있는 property 중 style도 있다.
title.style.color = "blue";
function handTitleClick() {
  console.log("title was clicked!");
  title.style.color = "blue";
}
title.addEventListener("click", handTitleClick); 처럼 쓸 수 있다.

### 이벤트 리스너 팁
console.dir(이름); 을 사용하여 콘솔에서 이벤트 리스너를 찾을 수 있다.
이벤트 리스너는 property 앞에 on이 붙어 있다.
자세한 설명은 MDN 사이트를 참조하자.
콘솔에서 on이 붙어있는 이벤트 리스너를 사용할 때는 on을 빼고 사용해야한다.

### Event part Two
```javascript
const title = document.querySelector("div.hello:first-child h1");
// HTML에 있는 id의 하위 요소를 title에 저장시킴
function handTitleClick() {
  console.log("title was clicked!");
  title.style.color = "blue";
}
function handMouseEnter() {
  title.innerText = "Mouse is here!";
}
function handMouseLeave() {
  title.innerText = "Mouse is gone!";
}
console.dir(title);
// 이벤트 리스너 확인 가능(앞에 on이라고 붙어져 있는 것)
// 사용할 때는 on 빼고 사용

// 함수를 만듬
title.addEventListener("click", handTitleClick);
// title를 클릭하면 이벤트를 발생시켜 handTitleClick이라는 함수를 호출시킴
title.addEventListener("mouseenter", handMouseEnter);
// mouseenter은 마우스를 올렸을 때 발생
title.addEventListener("mouseleave", handMouseLeave);
// mouseleave은 마우스를 올렸다 내렸을 때 발생
```

### More Events
document의 body,head,title 이런것들은 중요하기 때문에
document.body.style~의 명령이 허용되지만, div같은것들은 호출이 안됨
나머지 element들은 querySelector나 getElementById로 불러와야됨

window는 보여지는 창(인터넷 화면)을 뜻함.

추가 된 코드만 올림
```javascript
function handWindowResize() {
  document.body.style.backgroundColor = "tomato";
}
function handWindowCopy() {
  alert("copier");
}
function handWindowOffline() {
  alert("SOS no WIFI");
}
function handWindowOnline() {
  alert("ALL GOOOD");
}

window.addEventListener("resize", handWindowResize);
// resize 화면 사이즈가 변할 때 발생

window.addEventListener("copy", handWindowCopy);
// ctrl + c 복사 했을 때 발생하는 이벤트

window.addEventListener("offline", handWindowOffline);
// WIFI를 껏을 때 발생하는 이벤트

window.addEventListener("online", handWindowOnline);
// WIFI가 켜졌을 때 발생하는 이벤트
```

### CSS in Javascript
h1태그를 클릭했을 때 색이 파랑색과 토마토색으로 변하게 하는 js
```javascript
const h1 = document.querySelector("div.hello h1");
// 하위 클래스를 찾아줌

// 이벤트 정의
function handleTitleClick() {
  const currentColor = h1.style.color;
  let newColor;
  if (currentColor === "blue") {
    newColor = "tomato";
  } else {
    newColor = "blue";
  }
  h1.style.color = newColor;
}

// 이벤트 실행
h1.addEventListener("click", handleTitleClick);
```
#### 설명문
현재 상태의 색깔값을 currentColor라는 이름의 변수에 저장해주고, 클릭했을 때 바뀌게 될 새로운 색깔값을 newColor라는 이름의 변수에 저장해줄거고 
이걸로 글자색(h1.style.color)을 바꿔줄거죠? 
(const currentColor = h1.style.color; 라고 했다고 이제부터 현재상태의색깔은 h1.style.color다! 이게 아니다.)
여기서 컴퓨터는 newColor가 무슨용도인지 모르고 그냥 이름으로써 알고 있는 것이기 때문에
다시 코드로 돌아가보면 어쨋든 지금 currentColor에 h1.style.color로 현재데이터를 넣어줬으니 조건문을 통과하면서 비어있던(undefined상태) 변수newColor에는 tomato가 들어가게됩니다.
근데 여기까지만으로는 컴퓨터가 이게 글자색을 바꾸라는 뜻인지를 모릅니다. 
사람은 변수이름 지을 때 이미 의도를 갖고있었기 때문에 자연스럽게 알고있겠지만 컴퓨터는 newColor라는 변수에 tomato를 넣긴 했는데 뭐 어쩌라는건지 모르고있다는거죠. (newColor에 데이터만 들어가고 끝! 인 상태)
그래서 반복문이 끝나는 바로 다음 줄에 h1.style.color = newColor;를 써줌으로써 글자색을 바꾸도록 해주어야합니다.

js 순서
1. element 찾기
2. event를 실행할 것을 정의하고
3. 그 event를 정의한다.
