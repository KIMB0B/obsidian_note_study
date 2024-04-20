# 기본 사용법

```java
@ResponseBody
@RequestMapping("/request-param-v3")
public String requestParamV3(
         @RequestParam String username,
         @RequestParam int age) {
    log.info("username={}, age={}", username, age);
    return "ok";
}
```
>[!note] 생략 설명
>변수명을 파라미터명과 동일하게 지정하면 @RequestParam 뒤의 인자를 생략할 수 있음.

```java
@RequestParam(required = true, defaultValue = "guest") String username,
@RequestParam(required = false, defaultValue = "-1") int age
```
>[!note] required 옵션 설명
>required값을 true로 주면 필수 입력해야 하는 파라미터, false면 입력하지 않아도 되는 파라미터이다.
>따로 설정해주지 않으면 기본적으로는 true로 설정되어 있음.

>[!note] defaultValue 설명
> 해당 파라미터의 값을 지정하지 않으면 기본적으로 지정될 값을 설정할 수 있음.