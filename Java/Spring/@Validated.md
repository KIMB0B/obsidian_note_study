# 정의

> [[검증(Validation) 기능|검증]]기를 실행하라는 Annotation.
> `WebDataBinder` 에 등록한 검증기를 찾아서 실행.

# 검증기 선정 방법

여러 검증기 중 어떤 검증기를 적용하게 될 지는 supports()에서 지정한 클래스를 통해 정해짐

# 사용 예시
### 검증기(변동 없음)
```java
@Component
public class ItemValidator implements Validator {
    @Override    
    public boolean supports(Class<?> clazz) {
        return Item.class.isAssignableFrom(clazz);
    }

	@Override
	public void validate(Object target, Errors errors) {
		...
	}
}
```
### 호출 클래스 상위
```java
@InitBinder
public void init(WebDataBinder dataBinder) {
    dataBinder.addValidators(itemValidator);
}
```

^dfaab1

[[Bean Validation]]을 이용하면 생략 가능

### 호출 메서드
```java
@PostMapping("/add")
public String addItem(
	@Validated @ModelAttribute Item item, 
	BindingResult bindingResult, 
	...) {

	// 아래 부분 제외해도 검증 가능
	// itemValidator.validate(item, bindingResult);
	...
}
```

# HTTP 메시지 컨버터를 통한 객체 Return

[[@RequestBody]]를 사용하여 객체 자체를 return할 때도 검증 기능을 사용할 수 있음.
```java
@PostMapping("/add")
public Object addItem(
	@RequestBody @Validated ItemSaveForm form, 
	BindingResult bindingResult) { 
	
	if (bindingResult.hasErrors()) {  
		log.info("검증 오류 발생 errors={}", bindingResult); 
		return bindingResult.getAllErrors();
	}

log.info("성공 로직 실행");

         return form;
     }
```
