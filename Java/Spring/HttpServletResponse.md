# 정의
> HTTP 서버가 클라이언트에게 응답을 보내는 데 사용되는 객체
> HTTP 응답 상태 코드를 설정하고, 응답 헤더를 추가하거나 수정하며, 클라이언트로 보낼 데이터를 쓸 수 있음

# HTTP 응답 설정

## 1. 상태 코드 설정
```java
response.setStatus(HttpServletResponse.SC_OK); // 정상 상태코드(200)을 설정
```

## 2. 헤더 직접 설정
```java
response.setHeader("Content-Type", "text/plain;charset=utf-8");
response.setHeader("Cache-Control", "no-cache, no-store, must-revalidate");
response.setHeader("Pragma", "no-cache");
response.setHeader("my-header","hello");
```

## 3. Content 편의 설정
```java
response.setContentType("text/plain");
response.setCharacterEncoding("utf-8");
```

## 4. 쿠키 편의 설정
```java
Cookie cookie = new Cookie("myCookie", "good");
cookie.setMaxAge(600); //600초

response.addCookie(cookie);
```

## 5. redirect 편의 설정
```java
response.sendRedirect("/hello.html");
```

# 데이터 응답
## 1. HTML 직접 응답
```java
response.setContentType("text/html");
response.setCharacterEncoding("utf-8");

PrintWriter writer = response.getWriter(); 
writer.println("<html>"); 
writer.println("<body>");  
writer.println(" <div>안녕?</div>"); 
writer.println("</body>"); 
writer.println("</html>");
```