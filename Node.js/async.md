## async, await

### async 함수

- 항상 프라미스를 반환

### await

- async 함수 내에서 사용
- await 표현에서 함수의 실행이 보류, 상태 저장 후 제어가 이벤트 루프로 반환
- 프라미스가 처리된 후 제어가 async 함수로 반환
- 프라미스 객체 생성자를 await 없이 호출할 경우 `pending` 상태의 객체 반환

## async, await error handle

1. throw new Error()
2. reject()

- 두 가지의 상황 모두 try, catch를 사용하여 error handle 가능

```javascript
async function handle(condition) {
  try {
    if (condition) throw new Error("Throw new Error");
    await new Promise((_, reject) => reject(new Error("Promise Rejected")));
  } catch (error) {
    console.log(error);
  }
}

handle(true);
//handle(false);
```

## return, return await

1. 프라미스 객체를 await 없이 return 할 경우

- `pending` 상태의 프라미스 객체를 반환하므로 error를 async 함수 내부에서 catch 불가

```javascript
async function handle() {
  try {
    return new Promise((_, reject) => reject(new Error("Promise Rejected")));
  } catch (error) {
    console.log("function catch", error);
  }
}

handle().catch((error) => console.log("outside catch", error));
// outside catch에서 error가 catch
```

2. 프라미스 객체를 await를 사용하여 return 할 경우

- `fulfilled` OR `rejected` 상태의 프라미스 객체를 반환하므로 error를 async 함수 내부에서 catch 가능

```javascript
async function handle() {
  try {
    return await new Promise((_, reject) =>
      reject(new Error("Promise Rejected"))
    );
  } catch (error) {
    console.log("function catch", error);
  }
}

handle();
```
