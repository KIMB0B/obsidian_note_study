# 정의

> 직접 xml이나 java코드로 설정파일을 작성할 필요 없이 @Component 어노테이션이 붙은 클래스들을 스프링 빈으로 등록해줌.
> [[@Autowired]]를 이용하여 설정했던 의존관계도 그대로 적용된 채로 빈에 등록됨.

# 사용 예시
```java
@Configuration
@ComponentScan
public class
```