# \<form\> tag 

## \<form\> tag 이용해 서블릿에 요청하기

```xml
<form name="FormLogin" method="get" action="login">
    <input type="text" name="user_id" placeholder="아이디">
    <input type="password" name="user_pw" placeholder="비밀번호">
    <input type="submit" value="로그인">
</form>
```

사용자가 자신의 아이디와 비밀번호를 입력한 후 로그인을 클릭하면 \<form\> 태그의 action 속성은 데이터를 전송할 서블릿이나 JSP의 이름을 지정합니다. 그러면 지정된 이름이 login인 서블릿으로 ID와 비밀번호가 전송됩니다.

실제 데이터는 각 \<input\> 태그의 name 속성 값과 쌍으로 전송됩니다. 그럼 서블릿에섯는 name 속성 값으로 같이 전송된 입력 데이터를 받아 옵니다.

&nbsp;

## 서블릿에서 클라이언트의 요청 얻기

HttpServletRequest 클래스에서 \<form\> 태그로 전송된 데이터를 받아오는 데 사용하는 메서드로는 다음과 같은 것들이 있습니다.

- getParameter() 메서드는 name 속성 값으로 전송된 데이터를 받아옵니다. 
- getParameterValues() 메서드는 name 속성 값으로 전송된 데이터가 여러 개일 때 사용합니다. 
- getParameterNames() 메서드는 name 속성 값으로 전송된 데이터의 이름을 모두 얻어옵니다.

&nbsp;

## 서블릿에서 클라이언트로 응답 보내기

서블릿에서 응답을 처리하는 방법은 다음과 같습니다.

1. doGet() 이나 doPost() 메서드 안에서 처리합니다.
2. javax.servlet.http.HttpServletResponse 객체를 이용합니다.
3. setContentType()을 이용해 클라이언트에게 전송할 데이터 종류(MIME-TYPE)를 지정합니다.
4. 클라이언트와 서블릿의 통신은 자바 I/O 스트림을 이용합니다.

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승