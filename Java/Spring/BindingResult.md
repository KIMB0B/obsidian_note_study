# 정의

> 사용자 입력의 데이터 바인딩 과정에서 발생하는 오류를 관리하고 추적하는 인터페이스
> 이를 통해 입력 데이터의 유효성 검사 결과를 저장하고, 필요할 때 오류를 쉽게 처리할 수 있도록 도와줌

>[!warning] 주의사항
> Controller의 함수의 매개변수로 들어가는 BindingResult는 [[@ModelAttribute]]이 붙은 매개변수 바로 뒤에 와야한다. 
> ex) public String addUser(@ModelAttribute User user, <u>BindingResult bindingResult</u>, ...) {...}

# 오류 상황 추가

## 1. 필드 오류 - FieldError

```java
// FieldError 생성자 요약

// 1. 간단한 버전
public FieldError(
	String objectName, 
	String field, 
	String defaultMessage)

// 2. 상세 버전
public FieldError(
	String objectName, 
	String field, 
	@Nullable Object rejectedValue, 
	boolean bindingFailure, 
	@Nullable String[] codes, 
	@Nullable Object[] arguments, 
	@Nullable String defaultMessage)
```
> [!note] 파라미터 정리(간단한 버전)
> - `objectName` : `@ModelAttribute` 이름  
>- `field` : 오류가 발생한 필드 이름  
>- `defaultMessage` : 오류 기본 메시지

> [!note] 파라미터 정리(상세 버전)
> - `objectName` : `@ModelAttribute` 이름  
>- `field` : 오류 필드  
> - `rejectedValue` : 사용자가 입력한 값(거절된 값)  
> - `bindingFailure` : 타입 오류 같은 바인딩 실패인지, 검증 실패인지 구분 값 
> - `codes` : 메시지 코드  
> - `arguments` : 메시지에서 사용하는 인자  
> - `defaultMessage` : 기본 오류 메시지

```java
// 사용 예시
bindingResult.addError(new FieldError("item", "itemName", "상품 이름은 필수입니다.")); 

// 오류 발생 시 사용자가 입력한 값을 유지한 버전
// rejectedValue 파라미터를 추가함
new FieldError("item", "itemName", item.getItemName(), false, null, null, "상품 이름은 필수입니다.")
```

## 2. 글로벌 오류 - ObjectError

```java
// ObjectError 생성자 요약

// 1. 간단한 버전
public ObjectError(
	String objectName, 
	String defaultMessage)

// 2. 상세 버전
public FieldError(
	String objectName, 
	@Nullable String[] codes, 
	@Nullable Object[] arguments, 
	@Nullable String defaultMessage)
```
> [!note] 파라미터 정리(간단한 버전)
> - `objectName` : `@ModelAttribute` 이름 
>- `defaultMessage` : 오류 기본 메시지

> [!note] 파라미터 정리(상세 버전)
> - `objectName` : `@ModelAttribute` 이름  
> - `codes` : 메시지 코드  
> - `arguments` : 메시지에서 사용하는 인자  
> - `defaultMessage` : 기본 오류 메시지
```java
// 사용 예시
if (...) {  
	bindingResult.addError(new ObjectError("item", "총합은 10,000원 이상이어야 합니다.")); 
}
```