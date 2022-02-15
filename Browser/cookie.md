## Cookie

- HTTP는 Stateless -> 클라이언트의 상태를 기억하기 위해 쿠키를 사용
- 클라이언트에서 데이터를 저장하고 있음
- 쿠키는 자바스크립트로 접근 가능 -> XSS 위험성
  - `HttpOnly` : 브라우저만 쿠키에 접근 가능하게 함

## Session

- 클라이언트는 sessionId만 가지고 있음 / 세션의 데이터는 서버에 저장
- 서버가 여러 대일 경우 세션 관리를 위해 추가 처리 필요

## JWT

- Header, Payload, Signature로 구성
- 각 부분은 점으로 구분
- JWT는 URL 파라미터로 사용할 수 있도록 Base64URL 인코딩 사용
  - Base64 : 인코딩 결과값으로 "/"이 포함 -> URL에서 사용할 수 없음
- 서버에서 사용자에 대한 세션을 유지할 필요가 없음 -> 서버 확장 용이

### 과정

- 사용자 로그인 -> 서버는 JWT 생성 후 클라이언트에게 전달
- 클라이언트에서 헤더에 JWT 포함하여 서버에 요청
- 서버는 JWT 검증 후 Payload의 정보 확인

### Header

- 토큰의 타입
- signature 생성 알고리즘

### Payload

- 식별하기 위한 데이터
- 민감한 정보를 담지 않음

### Signature

- Header에 명시된 알고리즘으로 암호화
  - 비밀키(서버에 저장)
  - Base64URL로 인코딩 된 Header + "." + Base64URL로 인코딩 된 Payload를
