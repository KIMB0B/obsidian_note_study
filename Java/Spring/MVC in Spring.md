# [[Model-View-Controller(MVC)]] 전체 구조

![[Spring MVC 구조.png]]

# 동작 순서

1. **핸들러 조회**: 핸들러 매핑을 통해 요청 URL에 매핑된 핸들러(컨트롤러)를 조회한다.
2. **핸들러 어댑터 조회**: 핸들러를 실행할 수 있는 핸들러 어댑터를 조회한다.
3. **핸들러 어댑터 실행**: 핸들러 어댑터를 실행한다.
4. **핸들러 실행**: 핸들러 어댑터가 실제 핸들러를 실행한다.
5. **ModelAndView 반환**: 핸들러 어댑터는 핸들러가 반환하는 정보를 ModelAndView로 **변환**해서 반환한다.
6. **viewResolver 호출**: 뷰 리졸버를 찾고 실행한다.
    JSP의 경우: `InternalResourceViewResolver` 가 자동 등록되고, 사용된다.
7. **View 반환**: 뷰 리졸버는 뷰의 논리 이름을 물리 이름으로 바꾸고, 렌더링 역할을 담당하는 뷰 객체를 반환한다.
    JSP의 경우 `InternalResourceView(JstlView)` 를 반환하는데, 내부에 `forward()` 로직이 있다.
8. **뷰 렌더링**: 뷰를 통해서 뷰를 렌더링 한다.

# 경로 매핑

[[@RequestMapping]]을 이용하여 메서드에 경로를 매핑함

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

# HTTP Header 조회
```java
public class RequestHeaderController {

    @RequestMapping("/headers")
    public String headers(
	    HttpServletRequest request,
	    HttpServletResponse response,
	    HttpMethod httpMethod,
	    Locale locale,
		@RequestHeader MultiValueMap<String, String> headerMap,
		@RequestHeader("host") String host,
		@CookieValue(value = "myCookie", required = false) String cookie
	) {
	}
```
> [!note] 설명
> `HttpMethod`: 
> HTTP 메서드를 조회한다.
> 
> `Locale`: 
> Locale 정보를 조회한다.  
> 
> `@RequestHeader MultiValueMap<String, String> headerMap`: 
> 모든 HTTP 헤더를 MultiValueMap 형식으로 조회한다. 
> 
>`@RequestHeader("host") String host`: 
>특정 HTTP 헤더를 조회한다. 
>속성
>-필수 값 여부: `required`
>-기본 값 속성: `defaultValue`  
>
>`@CookieValue(value = "myCookie", required = false) String cookie`: 
>특정 쿠키를 조회한다.
>속성
>-필수 값 여부: `required` 
>-기본 값: `defaultValue`

# 요청 데이터 조회
## 1. [[@RequestParam]]
## 2. [[@ModelAttribute]]

