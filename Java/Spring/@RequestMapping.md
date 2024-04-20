# 정의

> Spring에서 주로 사용하는 애노테이션 기반의 컨트롤러를 지원하는 핸들러 매핑과 어댑터

# 사용 예시
```java
@Controller
public class Controller {
	@RequestMapping("/hello/form", method = RequestMethod.GET)
    public String helloForm() {
        return "hello-form";
    }
}
```
>[!note] 코드 설명
>`localhost:8080/hello`로 접속하면 ModelAndView를 통해 hello-form.jsp를 렌더링 함

# 장점

@RequestMapping은 메서드 단위에서 적용되기 때문에 하나의 컨트롤러에서 여러 경로를 매핑할 수 있다.

# 간편한 축약 Annotation 사용

`@GetMapping` 또는 `@PostMapping` 등으로 Get 또는 Post 방식 등의 @RequestMapping을 간편하게 정의할 수 있음
- @GetMapping  
- @PostMapping  
* @PutMapping  
* @DeleteMapping  
* @PatchMapping

# 중복되는 상위 경로 관리

하나의 컨트롤러 클래스에서 중복되는 상위 경로는 아래와 같이 통일할 수 있음
```java
@Controller
@RequestMapping("/hello")
public class Controller {

	@GetMapping("/form")
    public String helloForm() {
        return "hello-form";
    }

	@GetMapping("/save")
	public String helloSave() {
        return "hello-save";
    }
}
```

# 경로 변수 사용 (@PathVariable)

경로에 {} 부분으로 변수로 받을 부분을 지정하고 @PathVariable로 해당 경로에 들어온 값을 변수로 사용할 수 있음
```java
@GetMapping("/mapping/{userId}")
public String mappingPath(@PathVariable("userId") String data) {

    log.info("mappingPath userId={}", data);
    return "ok";
}
```
변수명을 {}안에 넣은 값과 같은 값으로 지으면 @PathVariable의 인자값을 생략할 수 있음
```java
@GetMapping("/mapping/{userId}")
public String mappingPath(@PathVariable String uesrId) {

    log.info("mappingPath userId={}", userId);
    return "ok";
}
```

# 특정 헤더 조건 매핑(headers 옵션)

특정 헤더를 기준으로 조건을 추가하여 현재 요청 URL에서 요청을 할지 말지 결정함
* headers="mode",  (mode라는 header가 있을 때)
* headers="!mode"  
* headers="mode=debug"  
* headers="mode!=debug" (! = )