## JavaScript Engine

1. Call Stack : 함수 실행 순서를 저장
2. Memory Heap : 데이터가 저장되는 메모리 공간

- 자바스크립트는 싱글 스레드 언어 = 한 번에 하나의 작업만 처리 가능
- 비동기 작업을 블로킹하지 않고 처리하기 위해서 런타임 환경(브라우저, Node.js)에서 담당
- 자바스크립트 엔진 : 싱글 스레드 / 브라우저, Node.js : 멀티 스레드

## 브라우저의 이벤트 루프

- 브라우저가 비동기 작업을 완료하면 작업에 맞는 queue에 콜백 함수를 push

### Event Loop

- 콜 스택이 비어있다면 동작
- 우선 순위 : Microtask Queue -> Animation Frames -> Task Queue
- Microtask Queue, Animation Frames : queue에 있는 모든 작업을 처리 후 진행
- Task Queue : 하나씩만 처리

### Microtask Queue

- promise
- mutation observer

### Animation Frames

- `requestAnimationFrame()` : 브라우저에서 다음 렌더링이 발생하기 전에 콜백이 수행되는 것을 보장

### Task Queue

- `setTimeout()`, `setInterval()`
- 이벤트 핸들러
