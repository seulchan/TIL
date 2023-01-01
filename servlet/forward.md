## 포워드란?

하나의 서블릿에서 다른 서블릿이나 JSP와 연동하는 방법을 포워드(forward)라고 합니다.

## 서블릿에서 사용되는 포워드 방법

- redirect 방법
  - HttpServletResponse의 sendRedirect() 메서드를 사용합니다.
  - 웹 브라우저에 재요청하는 방식입니다.
  - 형식: sendRedirect("포워드할 서블리 또는 URL");
- refresh 방법
  - HttpServletResponse의 addHeader() 메서드를 사용합니다.
  - 웹 브라우저에 재요청하는 방식입니다.
  - 형식: response.addHeader("Refresh", "경과시간(초); url=요청할 서블릿 또는 JSP");
- location 방법
  - 자바스크립트 location 객체의 href 속성을 사용합니다.
  - 자바스크립트에 재요청하는 방식입니다.
  - 형식: location.href="요청할 서블릿 또는 JSP";
- dispatch 방법
  - 일반적으로 포워딩 기능을 지칭합니다.
  - 서블릿이 직접 요청하는 방법입니다.
  - RequestDispatcher 객체의 forward() 메서드를 사용합니다.
  - 형식:

   ```JAVA
   RequestDispatcher dispatcher = request.getRequestDispatcher("요청할 서블릿 또는 JSP"); 
   dispatcher.forward(request, response);    
   ```

---

## dispatch 방법의 특징

- redirect, refresh, location 방법은 서블릿이 웹 브라우저를 거쳐 다른 서블릿이나 JSP에게 요청하는 방법입니다. 반면에 dispatch 방법은 서블릿에서 클라이언트를 거치지 않고 바로 다른 서블릿에게 요청하는 방법입니다.

- dispatch를 이용한 포워딩 과정이 redirect 방법과 다른 점은 클라이언트의 웹 브라우저를 거치지 않고 바로 서버에서 포워딩이 진행된다는 것입니다. 따라서 웹 브라우저 주소창의 URL이 변경되지 않습니다. 즉, 클라이언트 측에서는 포워드가 진행되었는지 알 수 없습니다.

<p style="text-align:center;">
<img src="../images/dispatch-redirect.png" alt="forward" width="500"/>
</p>

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승