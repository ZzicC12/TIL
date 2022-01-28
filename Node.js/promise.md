## promise

- promise 객체는 비동기 작업의 최종 결과를 담고 있는 객체다.
- promise 객체는 `pending`, `fulfilled`, `rejected` 중 하나의 상태를 갖는다.
- 프라미스 객체 생성 시 resolve, reject 콜백을 인수로 가지는 함수를 전달
- 작업이 성공적으로 끝났을 경우 -> `fulfilled` 상태, resolve 호출, 작업의 결과 값을 반환

```javascript
new Promise((resolve, reject) => {
  // 작업의 결과
  const result = "";
  resolve(result);
});
```

- 작업이 에러와 함께 종료됐을 경우 -> `rejected` 상태, reject 호출, error를 반환

```javascript
new Promise((resolve, reject) => {
  // 작업 도중 에러 발생
  reject(new Error("error"));
});
```

- promise가 이행되거나 거부되면 결정된 것으로 간주
- then(onFulfilled, onRejected) : 전달된 값으로 동기적으로 프라미스를 해결
- catch(onRejected) = then(null, onRejected)
