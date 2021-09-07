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
