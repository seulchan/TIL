## 바인딩

서블릿에서 조회한 대량의 상품 정보를 JSP로 전달할 때는 GET 방식이 불편합니다. 따라서 서블릿에서 다른 서블릿 또는 JSP로 대량의 데이터를 공유하거나 전달하고 싶을 때는 바인딩(binding) 기능을 사용합니다.

웹 프로그램 실행 시 자원(데이터)을 서블릿 관련 객체에 저장하는 방법으로, 주로 HttpServletRequest, HttpSession, ServletContext 객체에서 사용되며 저장된 자원(데이터)은 프로그램 실행 시 서블릿이나 JSP에서 공유하며 사용합니다.

&nbsp;

### 서블릿 객체에서 사용되는 바인딩 관련 메서드

|관련 메서드   | 기능 |
|---|---|
|setAttribute(String name, Object obj) | 자원(데이터)을 각 객체에 바인딩합니다. |
|getAttribute(String name)|각 객체에 바인딩된 자원(데이터)을 name으로 가져옵니다.|
|removeAttribute(String name)|각 객체에 바인딩된 자원(데이터)을 name으로 제거합니다.|

&nbsp;

### HttpServletRequest를 이용한 redirect 포워딩 시 바인딩

```java
@WebServlet("/first")
public class FirstServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setContentType("text/html;charset=utf-8");
        req.setAttribute("address", "서울시 강남구");
        resp.sendRedirect("second");
    }
}

@WebServlet("/second")
public class SecondServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setContentType("text/html;charset=utf-8");
        PrintWriter out = resp.getWriter();
        String address = (String) req.getAttribute("address");
        out.print("<html><body>");
        out.print("주소: " + address);
        out.print("<br>");
        out.print("redirected successfully and binding too");
        out.print("</body></html>");
    }
}
```

실행 결과를 보면 null이 출력됩니다. 왜 그럴까요?

- 포워딩 과정 1단계인 웹 브라우저에서 요청할 때 서블릿에 전달되는 첫 번째 request는 웹 브라우저를 통해 재요청되는 두 번째 request와는 다른 요청입니다. 즉, redirect 방식으로는 서블릿에서 바인딩한 데이터를 다른 서블릿으로 전송할 수 없습니다.
- 그럼 이런 의문이 들 수 있을 것입니다. GET 방식으로 전송하면 되지 않느냐고 말이죠. 물론 전달하고자 하는 데이터가 보안과 상관이 없으며, 데이터 양이 적다면 그렇게 해도 괜찮습니다. 하지만 데이터베이스에서 조회된 수십 개의 회원 정보나 상품 정보를 전달해야 한다면 확실히 redirect 방식에는 문제가 있습니다.

&nbsp;

### HttpServletRequest를 이용한 dispatch 포워딩 시 바인딩

```java
@WebServlet("/first")
public class FirstServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setContentType("text/html;charset=utf-8");
        req.setAttribute("address", "서울시 강남구");
        RequestDispatcher dispatch = req.getRequestDispatcher("second");
        dispatch.forward(req, resp);
    }
}

@WebServlet("/second")
public class SecondServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setContentType("text/html;charset=utf-8");
        PrintWriter out = resp.getWriter();
        String address = (String) req.getAttribute("address");

        out.print("<html><body>");
        out.print("주소: " + address);
        out.print("<br>");
        out.print("dispatched successfully and binding too");
        out.print("</body></html>");
    }
}
```

화면에 정상적으로 주소가 출력됩니다. 이 포워딩 과정을 보면 첫 번째 서블릿에서 두 번째 서블릿으로 전달되는 request가 브라우저를 거치지 않고 바로 전달되었습니다. 따라서 첫 번째 서블릿의 request에 바인딩된 데이터가 그대로 전달된 것입니다.

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승