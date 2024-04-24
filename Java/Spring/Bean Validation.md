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
```java
private final ItemValidator itemValidator;

@InitBinder
public void init(WebDataBinder dataBinder) {
    dataBinder.addValidators(itemValidator);
}
```