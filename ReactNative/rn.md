## React Native

## Architecture

### Main Thread

- application이 실행되는 스레드
- UI를 변경할 수 있음

### Shadow Thread

- 레이아웃을 생성 및 계산
- Yoga 엔진 사용

### JS Thread

- Javascript 코드가 실행

### bridge

- Javascript와 Native는 직접 통신하지 않고 bridge에 의존(데이터를 JSON 형태로 통신)
- 대용량 데이터 전송시 속도 느림
- 모든 것이 비동기적으로 동작
  - 동기적으로 데이터 접근이 필요한 Native Api 사용 불가

### fabric

- JSON으로 통신하는 bridge와 달리 Javascript Interface를 사용
