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
>[!note] 코드 설명
>첫번째 줄을 보면 LoggerFactory의 getLogger()를 통해 log를 작성할 수 있는 변수를 선언함
>log의 단계는 error < warn < info < debug < trace 단계로 깊어지며 어느 단계부터 로그를 볼건지 설정할 수 있음

# 로그 레벨 설정
# 사용 예시

```
```
