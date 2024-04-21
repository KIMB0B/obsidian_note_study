# 정의

> Controller의 메서드가 return하는 데이터 자체가 클라이언트에게 전달되도록 하는 Annotation

# 단순 텍스트 응답

```java
@ResponseBody
@GetMapping("/response-body-string")
public String responseBody() {}
    return "ok";
}
```

# JSON 응답
```java

```