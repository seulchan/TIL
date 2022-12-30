## 서블릿 매핑하기
실제 서블릿 매핑을 보면 \<servlet\> 태그와 \<servlet-mapping\> 태그의 하위 태그에 \<servlet-name\> 태그가 공통으로 있습니다. \<servlet-name\> 태그의 값 'firstServlet'이 \<servlet\> 과 \<servlet-mapping\> 태그를 연결시켜 줍니다.

그리고 웹 브라우저에서 \<url-pattern\> 태그의 /first로 요청할 경우 firstServlet 값을 가지는 \<servlet\> 태그를 찾아 실제 서블릿인 FirstServlet을 실행합니다.

```
    <servlet>
        <servlet-name>firstServlet</servlet-name>
        <servlet-class>FirstServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>firstServlet</servlet-name>
        <url-pattern>/first</url-pattern>
    </servlet-mapping>
```
