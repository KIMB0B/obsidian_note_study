# 정의

>

# 데이터가 들어갈 객체 생성
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
@RequestMapping("/model-attribute-v1")
public String modelAttributeV1(@ModelAttribute HelloData helloData) {
    log.info("username={}, age={}", helloData.getUsername(), helloData.getAge());
    return "ok";
}
```