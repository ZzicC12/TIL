## client side js module

- client side의 모듈 시스템 존재 X
- script tag를 사용하여 js 파일을 사용
  - 파일마다 독립적인 스코프를 갖지 않고 전역 객체를 공유 -> 스코프 오염
- `type="module"` -> ESM 모듈 시스템 사용 가능
  - `import`, `export` 사용 가능
- 모듈 번들러 사용으로 문제 해결 (webpack 등)

## script type="module"

- 로컬에서는 동작하지 않음 / HTTP OR HTTPS에서만 동작
- 엄격 모드로 실행
- 독립적인 스코프를 가짐
- defer 속성을 가진 script와 동일하게 동작
  - HTML 파싱을 블록하지 않고 파싱이 완전이 끝난 후에 실행
