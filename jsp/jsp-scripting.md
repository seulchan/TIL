# JSP 스크립트 요소

JSP 스크립트 요소 (scripting element)란 JSP 페이지에서 여러 가지 동적인 처리를 제공하는 기능으로, <% %> 기호 안에 자바 코드로 구현합니다. <% %> 기호를 스크립트릿(scriptlet)이라고 부릅니다.

스크립트 요소의 종류는 다음과 같습니다.

- declaration tag: JSP에서 변수나 메서드를 선언할 때 사용합니다.
- scriptlet: JSP에서 자바 코드를 작성할 때 사용합니다.
- expression tag: JSP에서 변수의 값을 출력할 때 사용합니다.

&nbsp;

## Declaration tag

선언문 안의 멤버는 서블릿 변환 시 서블릿 클래스의 멤버로 변환됩니다. 선언문의 형식음 다음과 같습니다.

```JSP
<%! 멤버 변수 or 멤버 메서드 %>

<%!
    int count = 0;
    public void increment() {
        count++;
    }
%>
```

&nbsp;

## Scriptlet

Scriptlet은 초기의 JSP에서 자바 코드를 이용해 화면의 동적인 기능을 구현했습니다. 비록 현재 JSP 페이지에서는 거의 사용되지 않지만 자바 코드로 화면의 동적인 기능을 구현할 수 있다면 자바 코드를 대체해서 나온 여러 가지 태그들을 이해하는 데에도 분명 도움이 될 것입니다.

scriptlet은 다음과 같은 형식으로 작성합니다.

```JSP
<% 자바 코드 %>

<% String age = request.getParameter("age"); %>
```

&nbsp;

## Expression tag

Expression tag는 JSP 페이지의 정한 위치에 값을 출력하는 기능입니다. 즉, JSP 페이지에서 변수나 메서드의 결과값 등을 출력하는 용도로 사용합니다.

표현식의 형식은 다음과 같습니다.

```JSP
<%= 값 or 자바 변수 or 자바 식 %>

<%= name %>
```

&nbsp;

## JSP 주석문

다음은 JSP 페이지에 사용되는 주석문들입니다.

- HTML 주석문
- 자바 주석문
- JSP 주석문

JSP 페이지에서는 HTML이 사용되므로 HTML 주석문이 있고, Scriptlet 안에서는 자바 코드가 사용되므로 자바 주석문이 있습니다. 그리고 스크립트 요소에 대해 주석 처리를 하는 JSP 주석문도 있습니다.

다음과 같이 <% %> 부분에 '--'를 붙이면 JSP 주석문이 됩니다.

```JSP
<%-- 내용 --%>
```

&nbsp;

## 내장 객체(내장 변수) 기능

JSP 페이지의 내장 객체(내장 변수)란 JSP가 서블릿으로 변환될 때 컨테이너가 자동으로 생성시키는 서블릿 멤버 변수를 말합니다. 즉, 서블릿으로 구현 시 자주 사용했던 객체를 개발자가 일일이 만드는 것이 아니라 서블릿으로 변환 시 컨테이너가 자동으로 생성하여 사용하게끔 제공하는 것입니다.

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승
