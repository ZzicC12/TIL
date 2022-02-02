## 변수

- 값을 저장하기 위한 메모리 공간을 가리키는 이름
- 값이 아니라 메모리 주소를 기억
- 할당 : 변수에 값을 저장하는 것
- 참조 : 변수에 저장된 값을 읽어 들이는 것
- 선언 : 메모리 공간을 확보하고 식별자와 연결
- 초기화 : 변수가 선언된 이후 최초로 값을 할당하는 것

## 호이스팅

- 변수 선언이 코드의 상단으로 이동한 것처럼 동작
- `var`, `let`, `const`, `function`, `class` 키워드 사용 -> 호이스팅
- 선언문이 런타임 이전 단계에서 먼저 실행

## var

- 선언 : 호이스팅
- 초기화 : 선언과 동시에 `undefined`로 초기화
- 선언 이전에 참조 -> `undefined`

```javascript
console.log(hello); // undefined
var hello = "hello";
```

## let, const

- 선언 : 호이스팅
- 초기화 : 런타임에 구문을 평가할 때
- 선언 이전에 참조 -> ReferenceError

```javascript
console.log(hello); // ReferenceError
const hello = "hello";
```
