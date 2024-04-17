# 정의
> 서블릿은 개발자가 HTTP 요청 메시지를 편리하게 사용할 수 있도록 개발자 대신에 HTTP 요청 메시지를 파싱하고, 그 결과를 `HttpServletRequest` 객체에 담아서 제공한다.

# Http 요청 메시지 조회
## Start-Line 정보
```java
//GET
System.out.println("request.getMethod() = " + request.getMethod());
// HTTP/1.1
System.out.println("request.getProtocol() = " + request.getProtocol());
//http
System.out.println("request.getScheme() = " + request.getScheme());
// http://localhost:8080/request-header
System.out.println("request.getRequestURL() = " + request.getRequestURL());
// /request-header
System.out.println("request.getRequestURI() = " + request.getRequestURI());
//username=hi     
System.out.println("request.getQueryString() = " + request.getQueryString());  
//https 사용 유무
System.out.println("request.isSecure() = " + request.isSecure()); 
```