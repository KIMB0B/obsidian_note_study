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
>`localhost:8080/hello`로 접속하면 ModelAndView를 통해 hello-form.jsp를 렌더링 함

# 장점

@RequestMapping은 메서드 단위에서 적용되기 때문에 하나의 컨트롤러에서 여러 경로를 매핑할 수 있다.

# 중복되는 경로 관리

하나의 컨트롤러 클래스에서 중복되는 경로는 아래와 같이 통일할 수 있음
