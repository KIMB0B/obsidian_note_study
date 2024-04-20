# JSON과 같은 형태의 객체 생성
```java
@Data
 public class HelloData {
     private String username;
     private int age;
 }
```

# 기본 사용법
```java
@ResponseBody
@PostMapping("/request-body-json")
public HelloData requestBodyJson(@RequestBody HelloData data) {
    log.info("username={}, age={}", data.getUsername(), data.getAge());
    return data;
}
```