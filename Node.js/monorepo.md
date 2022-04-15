## monorepo란?

- 하나의 repo가 여러 project로 구성됨

### 예시

- 하나의 repo에서 app, web을 동시에 관리할 때 (react, react-native)
- 하나의 repo에서 client, server를 동시에 관리할 때

### 장점

- 코드의 재사용
- 공통 모듈을 한 번만 설치

### 단점

- project에서 특정 버전의 package의 모듈을 필요로 하는 경우 → 충돌 발생
- 초기 설정에 시간 소요

## yarn workspace를 사용한 monorepo 설정

### 초기 설정

```json
{
  "private": true,
  "workspaces": {
    "packages": ["packages/**"],
    "nohoist": [""]
  }
}
```

### Command

- root에 module 추가, 삭제
  - `yarn add MODULE -W`
  - `yarn remove MODULE -W`
- 해당 package에 module 추가, 삭제
  - 추가한 module은 root의 node_modules로 hoist됨
  - hoist를 원하지 않을 경우 `nohoist`에 추가
    - 해당 package의 node_modules에 추가
  - `yarn workspace PACKAGE add MODULE`
  - `yarn workspace PACKAGE remove MODULE`

![https://classic.yarnpkg.com/assets/posts/2018-02-15-nohoist/monorepo-2.svg](https://classic.yarnpkg.com/assets/posts/2018-02-15-nohoist/monorepo-2.svg)

### local package 공유

- package.json에 dependencies에 추가
- root에서 install
