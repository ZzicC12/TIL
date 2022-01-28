## promise

- 비동기 작업의 최종적인 결과를 담고 있는 객체다.
- 프라미스 객체 생성 시 resolve, reject 콜백을 인수로 가지는 함수를 전달
- 작업이 성공적으로 끝났을 경우 -> resolve 호출

```javascript
new Promise((resolve, reject) => {
  // 작업의 결과
  const result = "";
  resolve(result);
});
```

- 에러 발생 시 reject 호출

```javascript
new Promise((resolve, reject) => {
  // 작업 도중 에러 발생
  reject(new Error("error"));
});
```

- resolve, reject 호출 시 이후의 코드 무시
- then(onFulfilled, onRejected) : 전달된 값으로 동기적으로 프라미스를 해결
- catch(onRejected) = then(null, onRejected)
