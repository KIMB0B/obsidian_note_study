# 정의

>Bean Validation 2.0(JSR-380)이라는 기술 표준
>검증 애노테이션과 여러 인터페이스의 모음

# 사전 작업
### 의존관계 추가

`build.gradle`에서 의존관계를 추가해줘야함.
```properties
implementation 'org.springframework.boot:spring-boot-starter-validation'
```

### 다른 검증기 연결 코드 제거

[[@Validated#^b256ed|다른 검증기 연결 코드]]가 있으면 Spring Validation만 적용해주기 위해 삭제

# 사용 예시

### 도메인에 적용
```java
@Data
 public class Item {

     private Long id;
     
     @NotBlank
     private String itemName;

     @NotNull
     @Range(min = 1000, max = 1000000)
     private Integer price;

     @NotNull
     @Max(9999)
     private Integer quantity;
}
```
>[!note] 설명
>@NotBlank, @NotNull, @Range, @Max 등등 여러가지의 Bean Validation이 있음

### 호출 메서드
```java
@PostMapping("/add")
public String addItem(
	@Validated @ModelAttribute Item item, 
	BindingResult bindingResult, 
	...) {
	...
}
```

### Message 등록
```properties
// 상세
NotBlank.item.itemName=상품 이름은 필수입니다.

// 범용
NotBlank={0} 공백X 
Range={0}, {2} ~ {1} 허용 
Max={0}, 최대 {1}
```
>[!note] 인자값
>`{0}` 은 필드명이고, `{1}` , `{2}` ...은 각 애노테이션 마다 다르다.

# 오브젝트 에러 처리

[[BindingResult#]]]가 아닌 Object