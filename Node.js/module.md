## 모듈이 필요한 이유

- 자바스크립트는 전역 범위에서 실행된다 -> 스코프 오염의 위험성 -> 즉시 실행 함수(IIFE)를 사용하여 캡슐화 가능

## CommonJS

### 핵심

- Node.js는 기본적으로 CommonJS를 사용
- require : 로컬 파일 시스템으로부터 모듈을 임포트하게 해줌
- exports, module.exports : 현재 모듈에서 공개될 기능들을 내보내기 위해 사용
- module은 exports 속성을 가지는 객체다.
- this -> module.exports

### require 과정

1. 이름을 바탕으로 모듈의 경로를 탐색 `require(MODULE_NAME)`

   1. `/` OR `./` 로 시작하는 경우 : 절대 경로 OR 상대 경로를 탐색
   2. 코어 Node.js 모듈 내에서 탐색
   3. 요청 모듈의 경로에서 시작하여 탐색하여 올라가면서 `node_modules` 디렉토리를 찾고 그 안에서 일치하는 모듈을 계속 찾음

2. 캐시된 모듈이 있을 경우 캐시된 모듈 사용
3. 빈 객체 리터럴을 통해 초기화 된 exports 속성을 갖는 module 객체 생성

```
Module {
  exports: {},
}
```

4. 최초 로드 후 module 객체 캐시
5. 해당 파일의 코드를 평가
6. module.exports의 값을 public API로 사용 가능

### exports와 module.exports의 차이점

- exports는 module.exports의 초기 값에 대한 참조일 뿐이다.
- exports 변수에 값을 직접 할당할 경우 참조를 잃고 더 이상 module.exports에 추가되지 않음
- exprots 변수가 참조하는 객체에 속성을 추가해야 함
- 올바른 사용 `exports.wow = "wow"; exports.hello = "hello"`
- 잘못된 사용 `exports = "wow"`

### 문제점

- 모듈이 처음 로드될 때만 평가되고 이후는 캐시된 객체를 반환함
- `require()`는 동기적으로 동작
- 캐시 + 동기적 -> 모듈의 완전하지 않은 상태를 load할 가능성 -> 순환 종속성 문제

### 모듈 정의 패턴

1. exports 지정하기
   - `exports.log = console.log("wow")`
   - 할당 된 모든 값이 외부에서 사용 가능
2. 함수 내보내기
   - module.exports 변수 전체를 함수로 재할당
   - `module.exports = () => console.log("wow")`
   - 단일 기능을 제공
3. 인스턴스 내보내기
   - 캐싱을 통해 동일한 객체를 제공 (싱글톤 패턴과 유사)
   - 모든 경우에서 전체 애플리케이션에서 고유성을 보장하지는 않음
4. 몽키 패치
   - 런타임 시에 기존 객체를 수정하거나 동작을 변경하는 것

## ESM

### 핵심

- 임포트가 모든 모듈의 가장 상위 레벨과 제어 흐름 구문의 바깥쪽에 기술
- `"type": "module"` 추가
- 파일의 확장자를 반드시 명시해야 함
- this -> undefined

### 과정

- CommonJS : 종속성 그래프가 탐색되기 전에 모든 파일들을 실행
- ESM : 종속성 그래프가 완성되기 전까지 어떠한 코드도 실행되지 않음

1. 파싱 : 오직 import 문만 찾음. 깊이 우선적으로 종속성 그래프 탐색.
2. 인스턴스화 : 종속성 그래프에서 얻은 트리 구조의 역순에서 각 모듈에서 익스포트된 속성을 찾는다.
3. 평가 : 종속성 그래프에서 후위 깊이 우선 탐색으로 모듈을 평가
