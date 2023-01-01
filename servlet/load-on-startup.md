## load-on-startup

서블릿은 브라우저에서 최초 요청시 init() 메서드를 실행한 후 메모리에 로드되어 기능을 수행합니다. 따라서 최초 요청에 대해서는 실행 시간이 길어질 수밖에 없습니다.
이런 단점을 보완하기 위해 이용하는 기능이 load-on-startup입니다.

### load-on-startup 특징

- 톰캣 컨테이너가 실행되면서 미리 서블릿을 실행합니다.
- 지정한 숫자가 0보다 크면 톰캣 컨테이너가 실행되면서 서블릿이 초기화됩니다.
- 지정한 숫자는 우선순위를 의미하며 작은 숫자부터 먼저 초기화됩니다.

```java
@WebServlet(name="loadConfig", urlPatterns = "/loadConfig", loadOnStartup = 1)
public class LoadAppConfig extends HttpServlet {

    private ServletContext context;

    @Override
    public void init(ServletConfig config) {
        System.out.println("LoadAppConfig init() 메서드 호출");
        context = config.getServletContext();
        String menu_member = context.getInitParameter("menu_member");
        String menu_order = context.getInitParameter("menu_order");
        String menu_goods = context.getInitParameter("menu_goods");
        context.setAttribute("menu_member", menu_member);
        context.setAttribute("menu_order", menu_order);
        context.setAttribute("menu_goods", menu_goods);
    }

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setContentType("text/html;charset=utf-8");
        PrintWriter out = resp.getWriter();
        String menu_member = (String) context.getAttribute("menu_member");
        String menu_order = (String) context.getAttribute("menu_order");
        String menu_goods = (String) context.getAttribute("menu_goods");
        out.print("<html><body>");
        out.print("<table border=1 cellspacing=0><tr>메뉴 이름</tr>");
        out.print("<tr><td>" + menu_member + "</td></tr>");
        out.print("<tr><td>" + menu_order + "</td></tr>");
        out.print("<tr><td>" + menu_goods + "</td></tr>");
        out.print("</table>");
        out.print("</body></html>");
    }
}
```

톰캣 실행 시 init() 메서드를 호출하면 getInitParameter() 메서드를 이용해 web.xml의 메뉴 정보를 읽어 들인 후 다시 ServletContext 객체에 setAttribute() 메서드로 바인딩합니다.

브라우저에 요청하면 web.xml이 아니라 ServletContext 객체에서 메뉴 항목을 가져온 후 출력하기 때문에 파일에서 읽어 들여와 출력하는 것보다 빨리 출력할 수 있습니다.

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승