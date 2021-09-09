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
