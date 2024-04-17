# 정의
> 서블릿은 개발자가 HTTP 요청 메시지를 편리하게 사용할 수 있도록 개발자 대신에 HTTP 요청 메시지를 파싱하고, 그 결과를 `HttpServletRequest` 객체에 담아서 제공한다.

# Http 요청 메시지 조회

`http://localhost:8080/hello?username=hello`에 접속한 상황
## Start-Line 정보

```java
System.out.println("request.getMethod() = " + request.getMethod());
System.out.println("request.getProtocol() = " + request.getProtocol());
System.out.println("request.getScheme() = " + request.getScheme());
System.out.println("request.getRequestURL() = " + request.getRequestURL());
System.out.println("request.getRequestURI() = " + request.getRequestURI());    
System.out.println("request.getQueryString() = " + request.getQueryString());  
System.out.println("request.isSecure() = " + request.isSecure()); 
```

## 헤더 정보

```java
request.getHeaderNames().asIterator().forEachRemaining(headerName -> 
	System.out.println(headerName + ": " + request.getHeader(headerName))
);
```