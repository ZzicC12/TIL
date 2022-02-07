## 동일 출처 정책 same-origin policy

- 브라우저가 스크립트를 통해 다른 출처에서 가져온 리소스와 상호작용하는 것을 제한하는 정책
- 자신의 출처와 동일한 리소스만 불러올 수 있음
- iframe의 취약점을 방어
  1. A 사이트에 로그인한 상태에서 B 사이트에 접속
  2. B 사이트의 iframe에서 A 사이트 삽입
  3. B 사이트의 script에서 iframe이 로드되면 리소스를 탈취 가능 (동일 출처 정책이 없을 경우)
  4. 동일 출처 정책으로 B 사이트와 B 사이트의 iframe에 삽입된 A 사이트의 origin이 다름으로 리소스에 접근 불가

## 출처 Origin

- scheme + host + port
- `http://localhost:3000`

## 교차 출처 리소스 공유 CORS

- Cross Origin Resource Sharing
- 브라우저가 다른 출처의 리소스와 상호작용하는 것을 허용하는 정책
- 서버의 응답에 `Access-Control-Allow-Origin` 헤더 추가

## XSS

- Cross-Site Scripting Attack
- 동적으로 HTML을 작성하는 부분에서 취약점 발생
- 스크립트를 통해 쿠키 탈취 가능 -> `HttpOnly`를 사용하여 스크립트로 쿠키 접근을 차단

## CSRF

- Cross-Site Request Forgeries
- 쿠키를 직접 탈취하는 것이 아님
- 피싱 메일의 링크를 클릭 -> 해당 쿠키를 사용하여 유저가 원하지 않는 행동 수행
- csrf token을 사용하여 검증
