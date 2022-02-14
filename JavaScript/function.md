## 함수

- 함수는 **호출할 수 있는 객체**다

### 함수 호이스팅

- `function` 키워드를 사용해서 함수를 선언한 경우
- 함수 선언문을 평가할 때 함수 객체를 생성
- 함수 이름과 동일한 이름의 식별자를 암묵적으로 생성 후 생성된 함수 객체를 할당
- 함수 선언문 이전에 호출하여도 함수 호이스팅에 의해 호출 가능
- 함수 표현식의 경우 변수 호이스팅 발생

### 화살표 함수

- 기존 함수의 this 바인딩 : 함수 호출 방식에 따라 동적으로 결정
- 화살표 함수의 this : 항상 상위 스코프의 this에 바인딩 `lexical this`
- 화살표 함수가 정의될 때 this 값이 정적으로 결정