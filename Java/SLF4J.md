# 정의

> 다양한 로그 라이브러리들을 통합하여 제공해주는 인터페이스
> 구현체로는 대체로 Logback 라이브러리를 사용함

# 장점
- 쓰레드 정보, 클래스 이름 같은 부가 정보를 함께 볼 수 있고, 출력 모양을 조정할 수 있다.  
- 로그 레벨에 따라 개발 서버에서는 모든 로그를 출력하고, 운영서버에서는 출력하지 않는 등 로그를 상황에 맞게 조절할 수 있다.  
- 시스템 아웃 콘솔에만 출력하는 것이 아니라, 파일이나 네트워크 등, 로그를 별도의 위치에 남길 수 있다. 특히 파일로 남길 때는 일별, 특정 용량에 따라 로그를 분할하는 것도 가능하다.  
- 성능도 일반 System.out보다 좋다. (내부 버퍼링, 멀티 쓰레드 등등) 그래서 실무에서는 꼭 로그를 사용해야 한 다.

# 사용 예시

```java
public class MainController {
    
	private final Logger log = LoggerFactory.getLogger(getClass());
	
	log.trace("trace log={}", "aaa");
	log.debug("debug log={}", "aaa");
	log.info(" info log={}", "aaa");
	log.warn(" warn log={}", "aaa");
	log.error("error log={}", "aaa");
}
```
>[!note] 코드 설명
>첫번째 줄을 보면 LoggerFactory의 getLogger()를 통해 log를 작성할 수 있는 변수를 선언함
>log의 단계는 error < warn < info < debug < trace 단계로 깊어지며 어느 단계부터 로그를 볼건지 설정할 수 있음

# Annotation 사용

Lombok의 @Slf4j Annotation을 사용하여 log를 선언하는 부분을 생략할 수 있음.
```java
@Slf4j
public class MainController {
    
	log.trace("trace log={}", "aaa");
	log.debug("debug log={}", "aaa");
	log.info(" info log={}", "aaa");
	log.warn(" warn log={}", "aaa");
	log.error("error log={}", "aaa");
}
```

# 로그 레벨 설정

```properties
# application.properties

# 전체 로그 레벨을 info 단계로 설정
# 그럼 info 단계부터 warn, error 단계의 에러가 나옴
logging.level.root=info

#hello.springmvc 패키지와 그 하위 로그 레벨을 debug 단계로 설정
# 그럼 해당 패키지와 하위 로그의 로그들은 debug부터 info, warn, error 단계의 에러가 나옴
logging.level.hello.springmvc=debug
```

# 올바른 로그 사용법

- **올바르지 않은 경우**
	`log.debug("data=" + data)`
	로그 출력 레벨을 info로 설정해도 해당 코드에 있는 "data="+data가 실제 실행이 되어 버린다. 
	결과적으로 문자 더하기 연산이 발생함.
- **올바른 경우**
	`log.debug("data={}", data)`
	로그 출력 레벨을 info로 설정하면 아무일도 발생하지 않는다. 
	따라서 위과 같은 의미없는 연산이 발생하지 않음.