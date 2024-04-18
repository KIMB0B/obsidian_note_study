# 정의

> Spring에서 주로 사용하는 애노테이션 기반의 컨트롤러를 지원하는 핸들러 매핑과 어댑터

# 사용 예시
```java
@Controller
public class Controller {
	@RequestMapping("/hello")
    public ModelAndView process() {
        return new ModelAndView("hello-form");
    }
}
```
>[!note] 코드 설명
>`localhost:8080/hello`로 접속하면 