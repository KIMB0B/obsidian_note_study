# 정의

> Annotation을 통해 Bean으로 지정된 클래스들의 [[의존성 주입(DI)]]을 위해 사용하는 Annotation

# 사용 예시 
## 1. 생성자 주입
```java
@Component
public class OrderServiceImpl implements OrderService {

	private final MemberRepository memberRepository;
	private final DiscountPolicy discountPolicy;

	@Autowired
     public OrderServiceImpl(MemberRepository memberRepository, DiscountPolicy discountPolicy) {
         this.memberRepository = memberRepository;
         this.discountPolicy = discountPolicy;
     }

}
```
>[!note] 코드 설명
> OrderServiceImpl생성자에 @Autowired를 추가하여 OrderServiceImpl이 생성되면서 동시에 memberRepository와 discountPolicy의 의존성을 주입받음
## 2. 수정자(setter) 주입
```java
@Component
public class OrderServiceImpl implements OrderService {
	
    private MemberRepository memberRepository;
    private DiscountPolicy discountPolicy;
    
	@Autowired
	public void setMemberRepository(MemberRepository memberRepository) {
        this.memberRepository = memberRepository;
	}
	
    @Autowired    
    public void setDiscountPolicy(DiscountPolicy discountPolicy) {
        this.discountPolicy = discountPolicy;
    }
}
```
>[!note] 코드 설명
>외부에서 setMemberRepository()나 setDiscountPolicy() 즉 setter 함수를 사용하여 OrderServiceImpl 클래스의 의존성을 주입 가능
## 3. 필드 주입
```java
@Component
public class OrderServiceImpl implements OrderService {
	
    @Autowired    
    private MemberRepository memberRepository;
    @Autowired
    private DiscountPolicy discountPolicy;
}
```
>[!note] 코드 설명
>필드를 선언한 곳 바로 앞에 @Autowired를 추가하여 의존성 주입 가능
>매우 간단해보이나 외부에서 의존성 변경이 불가능하기 때문에 스프링 설정을 목적으로 하는 [[@Configuration]] 같은 곳의 특별한 용도에서만 사용해야 함
## 4. 일반 메서드 주입
```java
@Component
public class OrderServiceImpl implements OrderService {
	
    private MemberRepository memberRepository;
    private DiscountPolicy discountPolicy;
    
    @Autowired
    public void init(MemberRepository memberRepository, DiscountPolicy discountPolicy) {
        this.memberRepository = memberRepository;
        this.discountPolicy = discountPolicy;
    }
}
```
>[!note] 코드 설명
>생성자가 아닌 이와같은 일반 메서드에서도 의존성 주입이 가능하지만 일반적으로 잘 사용하지는 않음
## 5. Lombok 활용
```java
 @Component
 @RequiredArgsConstructor 
 public class OrderServiceImpl implements OrderService {
	 private final MemberRepository memberRepository;
     private final DiscountPolicy discountPolicy;
}
```
>[!note] 코드 설명
>@RequiredArgsConstructor를 통해 final이 붙은 필드를 선언해주는 생성자를 자동으로 만들어줌
>그리고 생성자가 딱 한개만 있으면 @Autowired를 생략할 수 있기 때문에 위와같이 작성만 해도 의존성 주입이 가능함

# 추가 옵션

@Autowired는 기본값으로 해당 어노테이션이 붙은 개체에게 필수적으로 의존성 주입이 되어야 함.
필수적으로 주입되지 않아도 실행이 가능하게 만드는 옵션이 required = false임.
```java
@Component
public class OrderServiceImpl implements OrderService {
	
    @Autowired(required = false)  
    private MemberRepository memberRepository;
    @Autowired(required = false)  
    private DiscountPolicy discountPolicy;
}
```