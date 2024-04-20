# 정의

> 다양한 로그 라이브러리들을 통합하여 제공해주는 인터페이스
> 구현체로는 대체로 Logback 라이브러리를 사용함

# 사용 예시

```java
private final Logger log = LoggerFactory.getLogger(getClass());

log.trace("trace log={}", "aaa");
log.debug("debug log={}", "aaa");
log.info(" info log={}", "aaa");
log.warn(" warn log={}", "aaa");
log.error("error log={}", "aaa");
```