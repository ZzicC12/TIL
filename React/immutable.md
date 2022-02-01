## 불변성

### 불변성이란?

- 메모리에 값이 할당된 후에는 해당 메모리에 할당된 값을 변경할 수 없는 특성

#### 원시 값

- [Primitive values](https://developer.mozilla.org/ko/docs/Web/JavaScript/Data_structures#%EA%B8%B0%EB%B3%B8_%ED%83%80%EC%9E%85_primitive_value "MDN 링크")
- 변수가 가리키는 메모리 주소에 실제 값이 저장되어 있음
- 불변성 O

#### 객체

- [Objects](https://developer.mozilla.org/ko/docs/Web/JavaScript/Data_structures#%EA%B0%9D%EC%B2%B4_objects "MDN 링크")
- 변수가 가리키는 메모리 주소에 객체가 저장된 메모리 주소(참조값)가 저장되어 있음
- 불변성 X / 객체의 속성을 직접 변경 가능

### state의 불변성을 지켜야 하는 이유

- react는 state가 변경되면 해당 component를 rerender
- react는 성능 최적화를 위해 state의 변경을 얕은 비교를 사용하여 판단
- 얕은 비교 : 메모리 주소가 동일한지 비교 ( 객체의 경우 참조 값만 비교, 속성은 비교하지 않음 )
- 불변성을 지키지 않고 state 객체의 속성을 직접 변경할 경우 -> state 객체의 참조값은 이전과 동일 -> 얕은 비교는 state 객체가 변경되지 않았다고 판단 -> rerender X
- 새로운 state 객체를 생성 -> 얕은 비교는 state 객체가 변경되었다고 판단 -> rerender O
