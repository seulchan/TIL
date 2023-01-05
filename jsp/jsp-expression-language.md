# 표현 언어 (Expression Language)

## 표현 언어 특징

- 기존 표현식보다 편리하게 값을 출력한다.
- 변수와 여러 가지 연산자를 포함할 수 있다.
- JSP의 내장 객체에 저장된 속성 및 자바의 빈 속성도 표현 언어에서 출력할 수 있다.
- 표현 언어 자체 내장 객체도 제공
- JSP 페이지 생성 시 기본 설정은 표현 언어를 사용할 수 없다.
- 페이지 디렉티브 태그에서는 반드시 isELIgnored=false로 설정해야 한다.

&nbsp;

## 표현 언어 내장 객체

JSP는 기본적으로 내장 객체들을 제공하지만 이 객체들은 표현식에서만 사용할 수 있습니다. 따라서 표현 언어에서는 따로 내장 객체를 제공합니다. 표현 언어에서 제공하는 내장 객체들은 ${} 안에서만 사용할 수 있습니다.

|구분 | 내장 객체 |설명 |
|:---|:---|:---|
|스코프|pageScope|JSP의 page 같은 기능을 하고 page 영역에 바인딩된 객체를 참조|
||requestScope|JSP의 request 같은 기능을 하고 request 영역에 바인딩된 객체를 참조|
||sessionScope|JSP의 session 같은 기능을 하고 session 영역에 바인딩된 객체를 참조|
||applicationScope|JSP의 application 같은 기능을 하고 application 영역에 바인딩된 객체를 참조|
|요청 매개변수|param|request.getParameter() 메서드를 호출한 것과 같으면 한 개의 값을 전달하는 요청 매개변수를 처리|
||paramValues|request.getParameterValues() 메서드를 호출한 것과 같으면 여러 개의 값을 전달하는 요청 매개변수를 처리|
|헤더 값|header|request.getHeader() 메서드를 호출한 것과 같으면 요청 헤더 이름의 정보를 단일 값으로 반환|
||headerValues|request.getHeaderValues() 메서드를 호출한 것과 같으면 요청 헤더 이름의 정보를 배열로 반환|
|쿠키 값|Cookies|쿠키 이름의 값을 반환|
|JSP 내용|pageContext|pageContext 객체를 참조할 때 사용|
|초기 매개변수|initParam|컨텍스트 초기화 매개변수 이름의 값을 반환|

&nbsp;

## 표현 언어 스코프 우선 순위

표현 언어에서는 동일한 속성 이름에 접근할 경우 page 객체의 속성이 우선순위가 가장 높습니다. 표현 언어에서 같은 속성에 대한 우선위는 다음과 같습니다.

page > request > session > application

