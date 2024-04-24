# 정의

> 검증기를 실행하라는 Annotation.
> `WebDataBinder` 에 등록한 검증기를 찾아서 실행.

# 검증기 선정 방법

여러 검증기 중 어떤 검증기를 적용하게 될 지는 supports()에서 지정한 클래스를 통해 정해짐

# 사용 예시
## 검증기
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
## 호출 클래스 상위
```java
@InitBinder
public void init(WebDataBinder dataBinder) {
    dataBinder.addValidators(itemValidator);
}
```
## 호출 메서드
```java
// 아래 부분 제외해도 검증 가능
// private final ItemValidator itemValidator;

@PostMapping("/add")
public String addItem(
	@Validated @ModelAttribute Item item, 
	BindingResult bindingResult, 
	RedirectAttributes redirectAttributes) {

	// 아래 부분 제외해도 검증 가능
	// itemValidator.validate(item, bindingResult);
	...
}
```