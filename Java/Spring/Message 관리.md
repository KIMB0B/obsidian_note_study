# 정의

>Spring 프로젝트에서 여러 곳에 사용되는 다양한 문구를 한 곳에서 관리할 수 있도록 하는 기능
>국가별로 설정할 수도 있어서 국제화 기능을 제공함

# 초기 설정

Spring에선 `ResourceBundleMessageSource`를 [[Bean]]으로 등록해주면 됨
```java
@Bean
public MessageSource messageSource() {
	ResourceBundleMessageSource messageSource = new ResourceBundleMessageSource();
	
	messageSource.setBasenames("messages", "errors");
    messageSource.setDefaultEncoding("utf-8");
    return messageSource;
	
}
```

Spring Boot에서는 자동으로 등록이 되어 있어서 `application.properties`에서 설정해주면 됨
```properties
spring.messages.basename=messages
```

메시지 파일은 `src/main/resources/` 경로에 넣어주면 됨
![[Pasted image 20240423005450.png]]
