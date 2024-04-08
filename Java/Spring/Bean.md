# 정의

Spring IoC(Inversion of Control) 컨테이너가 관리하는 객체.
[[의존성 주입(DI)]]을 통해 외부에서 관리 및 주입 가능.

# 선언 방법

- XML을 통한 선언
```xml
<beans> 
	<bean id="myBean" class="com.example.MyClass"/> 
</beans>
```

- Annotation을 통한 선언
	**주요 Annnotation**
	- `@Component`: 일반적인 컴포넌트.
	- `@Repository`: 데이터 저장소의 역할을 수행하는 Bean에 사용.
	- `@Service`: 비즈니스 로직을 수행하는 Bean에 사용.
	- `@Controller`: 웹 요청과 응답을 처리하는 Bean에 사용.
	**사용 예시**
	```java
	@Component 
	public class MyBean { 
	}
```
	**Configuration을 통한 선언**
		[[@Configuration|Configuration 자세히보기]]
		![[@Configuration]]


# 의존성 주입 방법

Autowired를 통해 의존성 주입이 가능함.

[[@Autowired|Autowired 자세히보기]]
![[@Autowired]]

# Bean 사용 방법

ApplicationContext 형식의 변수를 선언하여 getBean()등의 함수를 통해 등록된 Bean을 불러옴.

[[ApplicationContext|ApplicationContext 자세히보기]]
![[ApplicationContext]]