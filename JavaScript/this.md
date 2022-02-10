## 전역 객체

- global scope에 항상 존재하는 객체
- 코드 실행 이전 자바스크립트 엔진에 의해서 생성
- 브라우저 : window 객체
- Node.js : global 객체

## this

- this 바인딩은 **함수 호출 방식**에 의해 동적으로 결정됨

### 1. 전역 호출

```javascript
console.log(this);
```

|             | 브라우저 |    CommonJS    |    ESM    |
| :---------: | :------: | :------------: | :-------: |
| 엄격 모드 O |  window  | module.exports | undefined |
| 엄격 모드 X |  window  | module.exports | undefined |

### 2. 일반 함수 호출

- 일반 함수로 호출된 모든 함수(중첩 함수, 콜백 함수 포함) 내부의 this에는 전역 객체가 바인딩
- 엄격 모드일 경우 : `undefined` 바인딩

```javascript
function strict() {
  "use strict";
  return this;
}
console.log(strict());
```

```javascript
function print() {
  return this;
}
console.log(print());
```

|             | 브라우저  | CommonJS  |    ESM    |
| :---------: | :-------: | :-------: | :-------: |
| 엄격 모드 O | undefined | undefined | undefined |
| 엄격 모드 X |  window   |  global   | undefined |

### 3. 메서드 호출

- this는 메서드를 소유한 객체가 아닌 **메서드를 호출한 객체**에 바인딩

```javascript
const obj = {
  name: "hello",
  method() {
    return this;
  },
};
console.log(obj.method());
```

### 4. 생성자 함수 호출

- 생성자 함수 내부의 this에는 생성자 함수가 생성할 인스턴스가 바인딩

### 5. call, apply

- 함수를 호출하면서 첫번째 인수로 전달한 객체를 함수의 this에 바인딩

```javascript
function print() {
  return this;
}
const obj = { key: "value" };

console.log(print.apply(obj));
console.log(print.call(obj));
```

### 6. bind

- 첫번째 인수로 전달한 객체를 함수의 this에 바인딩
- `call`, `apply`와 다르게 함수를 호출하지 않음

```javascript
function print() {
  return this;
}
const obj = { key: "value" };

print.bind(obj);
```
