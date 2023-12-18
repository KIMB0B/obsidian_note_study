# 정의

>JavaScript에서 Object(객체)의 타입을 지정할 때 사용함
>상호간에 정의한 약속 혹은 규칙을 의미

---
# Object 정의 범주

- 객체의 스펙(속성과 속성의 타입)
- 함수의 파라미터
- 함수의 스펙(파라미터, 반환 타입 등)
- 배열과 객체를 접근하는 방식
- 클래스

---
# 예시

인터페이스
```typescript
interface IProfile { 
name: string 
age: number | string school: string hobby: string }
```