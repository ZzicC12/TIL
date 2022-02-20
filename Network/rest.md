## REST

- Representational State Transfer
- 자원의 표현에 의한 상태 전달
- HTTP를 기반으로 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처
- URI는 리소스를 표현
- HTTP method는 리소스에 대한 행위를 표현

## 제약 조건

### Client-Server architecture

- 클라이언트와 서버는 각각 독립적
- 의존성 감소

### Stateless

- 각각의 요청은 별개의 것으로 처리
- 서버가 상태를 저장하지 않음

### Cacheability

- 캐시 처리 가능

### Layered System

- 서버는 다중 계층으로 구성될 수 있음

### Code on demand (optional)

- 서버가 전송한 스크립트를 클라이언트에서 실행

### Uniform Interface

#### Resource identification in requests

- 클라이언트의 요청에서 리소스를 식별할 수 있어야 함
- URI를 통해서 리소스 식별

#### Resource manipulation through representations

- HTTP method를 사용해서 리소스에 대한 행위를 표현해야 함

#### Self-descriptive messages

- 메시지를 어떻게 처리해야 하는지에 대한 충분한 정보를 포함해야 함
- 응답 헤더에 `Content-Type`을 통한 설명

#### Hypermedia as the engine of application state

- 애플리케이션의 상태는 하이퍼링크를 통해 전이되어야 함
- 응답에 요청과 관련된 링크를 포함
