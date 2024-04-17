# 정의

> 서블릿은 웹 컴포넌트 중 하나로, 웹 서버 또는 애플리케이션 서버에서 클라이언트의 요청을 처리하고 그 결과를 클라이언트에게 다시 전송하는 역할을 함

# 스프링 부트 설정

메인 어플리케이션 클래스에서 `@ServletComponentScan` 을 사용해 프로젝트의 서블릿을 자동으로 등록함
```java
@ServletComponentScan
@SpringBootApplication
public class MainApplication {
     public static void main(String[] args) {
         SpringApplication.run(ServletApplication.class, args);
    }
}
```

# 서블릿 생성 예시

HttpServlet 클래스를 extends하여 service()함수를 구현해 사용할 수 있음
`http://localhost:8080/hello`로 접속하면 일어날 일을 아래 service() 함수에서 정의할 수 있음
```java
@WebServlet(name = "helloServlet", urlPatterns = "/hello")
public class HelloServlet extends HttpServlet {

	@Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
         ...
    }
}
```

# [[HttpServletRequest]]