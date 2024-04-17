# 정의

> 서블릿은 웹 컴포넌트 중 하나로, 웹 서버 또는 애플리케이션 서버에서 클라이언트의 요청을 처리하고 그 결과를 클라이언트에게 다시 전송하는 역할을 함

# 스프링 부트 설정

메인 어플리케이션 클래스에서 @ServletComponentScan 을 사용해 프로젝트의 서블릿을 자동으로 등록함
```java
@ServletComponentScan //서블릿 자동 등록 @SpringBootApplication  
public class ServletApplication {

     public static void main(String[] args) {
         SpringApplication.run(ServletApplication.class, args);
        }
```