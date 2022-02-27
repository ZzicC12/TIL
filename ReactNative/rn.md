## React Native

- rn

## Threading Model

### Main Thread

- application이 실행되는 스레드
- UI를 변경할 수 있음

### Shadow Thread

- 레이아웃을 생성 및 계산
- Yoga 엔진 사용

### JS Thread

- Javascript 코드가 실행
- JSC 엔진 사용

## Architecture

### Bridge

- Javascript와 Native는 직접 통신하지 않고 bridge에 의존(데이터를 JSON 형태로 변환하여 통신)
- 대용량 데이터 전송시 속도 느림
- 스레드간 메모리를 공유하지 않기 때문에 불필요한 데이터 복사 필요
- 모든 것이 비동기적으로 동작
  - 동기적으로 데이터 접근이 필요한 Native Api 사용 불가

### Fabric

- UI layer를 담당
- C++ 사용하여 Shadow tree 관리

### JSI

- Native와 Javascript 간 bridge의 필요성을 제거
- 자바스크립트를 사용하여 C++ 호스트 객체를 참조하거나 메서드 실행 가능
