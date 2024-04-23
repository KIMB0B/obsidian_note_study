# 정의

>클라이언트로부터 받은 데이터가 비즈니스 규칙을 만족하는지 확인하거나, 데이터가 일관성 있고 안정적인 상태를 유지할 수 있도록 보장해주는 기능

# 오류 관리와 추적

## 1. [[BindingResult]]

# ThymeLeaf에서 검증 오류 표현

[[검증 관련 기능|ThymeLeaf의 검증 관련 기능]] 참고

# [[Message 관리|Message 기능]] 응용

Message 기능을 사용하여 오류 메시지를 효과적으로 관리할 수 있음.

## 1. 오류 Message 설정 파일 생성과 application 설정

 `src/main/resources/` 경로에 `errors.properties` 생성
 
 그 후 `application.properties`에서 errors도 추가해줌
```properties
spring.messages.basename=messages, errors
```

## 2. errors.properties 내용 추가
```properties
# 예시
required.item.itemName=상품 이름은 필수입니다.
range.item.price=가격은 {0} ~ {1} 까지 허용합니다.
max.item.quantity=수량은 최대 {0} 까지 허용합니다.
totalPriceMin=가격 * 수량의 합은 {0}원 이상이어야 합니다. 현재 값 = {1}
```

