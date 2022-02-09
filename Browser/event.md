## 버블링

- 한 요소에서 발생한 이벤트가 상위 요소에게 전파되는 방식

## 캡처링

- 이벤트가 상위 요소에서 하위요소로 전파되는 방식

## event.target / event.currentTarget

- event.target : 실제로 event가 발생한 요소
- event.currentTarget : 이벤트 핸들러가 부착된 요소

## 이벤트 위임 Event Delegation

- 하위 요소들에게 이벤트 핸들러를 각각 등록하는 대신 하나의 상위 요소에 이벤트 핸들러를 등록하는 방법
- event.target으로 요소 판별 가능
