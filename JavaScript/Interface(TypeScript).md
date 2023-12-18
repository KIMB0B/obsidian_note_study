# 정의

>[[TypeScript]]에서 Object(객체)의 타입을 지정할 때 사용함
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

**인터페이스**
```typescript
interface IProfile { 
	name: string 
	age: number | string 
	school: string 
	hobby?: string 
}
```

**객체 선언**
```typescript
let profile: IProfile = { 
	name: "철수", 
	age: 8, 
	school: "다람쥐초등학교" 
}
```

---
# 특징

1. 기본적으로 interface안에 지정한 속성들은 객체 선언 시 무조건 선언되어야 하고, 무조건을 원치 않다면 interface의 속성명 뒤에 ?를 붙힘(예시의 hobby속성 참고)
2. 