## Critical Rendering Path

### 1. DOM 생성

1.  서버로부터 받은 바이트 형태의 데이터를 인코딩해서 문자열로 변환한다.
2.  문자열로 된 HTML 문서를 파싱하며 토큰들로 분해한다.
3.  토큰들을 객체로 변환하여 노드를 생성한다.
4.  노드들의 트리 구조인 DOM을 생성한다.

### 2. CSSOM 생성

- HTML 파싱 과정과 동일
- 바이트 -> 문자열 -> 토큰 -> 노드 -> CSSOM

### 3. Render Tree 생성

- DOM과 CSSOM을 결합하여 렌더 트리 생성
- 렌더링되지 않는 노드는 제외

### 4. Layout (Reflow)

- 렌더 트리, 뷰포트를 바탕으로 요소들의 위치와 크기를 계산

### 5. Paint (Repaint)

- layer 별로 화면을 그림

### 6. Composition

- layer 순서대로 렌더

## 최적화

1. composition만 발생하는 CSS 속성 사용
