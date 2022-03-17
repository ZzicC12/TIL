## webpack

- entry point를 시작으로 의존적인 모듈들을 찾아 하나의 결과물로 합쳐주는 번들러

### install

```
 npm install -D webpack webpack-cli
```

### config

- entry : entry point를 시작으로 디펜던시 그래프를 생성
- output : 번들을 내보낼 위치, 번들 파일의 이름 지정
  - default : `dist/main.js`
  - 경로 지정 시 절대 경로 사용
- loader : js 파일이 아닌 리소스를 이해하기 위한 설정
  - module.rules 배열에 { test, use } loader 추가
  - test : 파일을 식별하기 위한 정규 표현식
  - use : loader name
- plugin
- mode
  - `process.env.NODE_ENV` 값
  - default : production
- devServer :
