# JSON과 같은 형태의 객체 생성


# 기본 사용법
```java
@ResponseBody
@PostMapping("/request-body-json")
public HelloData requestBodyJsonV5(@RequestBody HelloData data) {

         log.info("username={}, age={}", data.getUsername(), data.getAge());
    
         return data;
     }
```