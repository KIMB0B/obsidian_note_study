# 타입 추론

TypeScript는 변수 선언 시 따로 타입을 지정하지 않으면 타입을 추론하여 설정하게 됨
이 덕분에 이후 다른 타입을 넣으면 에러를 발생시켜 일관성 유지

```typescript
let aaa = '안녕하세요' // aaa의 타입을 String이라고 추론함
aaa = '반갑습니다' 
aaa = 3 // 🚨 다른 타입을 넣게되면 에러 발생!
```

---
# 타입 명시

`:` 뒤의 타입명으로 변수의 타입을 직접 명시할 수 있음
**두개 이상**의 타입 또한 명시 가능

```typescript
// 타입 지정 후 다른 타입의 값 변경 시도
let bbb: string = '반갑습니다.' 
bbb = '반가워요!!' 
bbb = 10 // 🚨 숫자 타입 불가능!

// 두개 이상의 타입 지정
let ccc: string | number = 1000 
ccc = '1000원' // ccc는 문자열, 숫자 둘 다 되기 때문에 에러가 발생하지 않음

// 함수 매개변수와 반환값의 타입 지정
function add2(num1: number, num1: number, unit: string): string { 
	return num1 + num2 + unit 
}
```

Object의 타입 지정은 [[Interface(TypeScript)|Interface]]를 통해 타입을 정의한 후 지정할 수 있음