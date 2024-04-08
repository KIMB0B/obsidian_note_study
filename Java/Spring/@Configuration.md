# 정의

따로 빈 정의용 클래스를 하나 생성해서 빈을 정의하는 방식.
이 어노테이션이 붙은 클래스 내에서 `@Bean` 어노테이션이 붙은 메서드를 통해 Bean을 정의하고, 컨테이너에 등록할 수 있음.

# 사용 예시
```java
@Configuration 
public class AppConfig {  
    @Bean  
    public MemberRepository memberRepository() {  
        return new MemoryMemberRepository();  
    }  
  
    @Bean  
    public DiscountPolicy discountPolicy() {  
        return new RateDiscountPolicy();  
    }  
  
    @Bean  
    public MemberService memberService() {  
        return new MemberServiceImpl(memberRepository());  
    }  
  
    @Bean  
    public OrderService orderService() {  
        return new OrderServiceImpl(memberRepository(), discountPolicy());  
    }  
}
```