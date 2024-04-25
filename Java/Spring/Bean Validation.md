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

[[BindingResult#1. 필드 오류 - FieldError|FieldError]]가 아닌 [[BindingResult#2. 글로벌 오류 - ObjectError|ObjectError]]관련 오류는 오브젝트 오류 관련 부분만 [[BindingResult#2. reject()|직접 자바 코드]]로 작성하는 것을 권장

# Groups

같은 Model이어도 상황별로 검증 로직이 다를 때 사용할 수 있음.

예시) 상품 등록할 때는 수량을 9999까지만 넣을 수 있지만 수정할 때는 무제한으로 넣을 수 있는 경우
### 1. Interface 생성
```java
package hello.itemservice.domain.item;
public interface SaveCheck { }
```
```java
package hello.itemservice.domain.item;
public interface UpdateCheck { }
```
### 2. 