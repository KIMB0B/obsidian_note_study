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

### 