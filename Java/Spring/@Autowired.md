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
> OrderServiceImpl생성자에 @Autowired를 추가하여 