# 서블릿 속성과 스코프

## 서블릿 속성 

서블릿 속성이란 다음 세 가지 서블릿 API 클래스에 저장되는 객체(정보)라고 보면 됩니다.

- ServletContext
- HttpSession
- HttpServletRequest

서블릿 API의 setAttribute()로 바인딩하고, 필요할 때 getAttribute()로 바인딩된 속성을 가져오면 됩니다. 또한 removeAttribute()로 속성을 서블릿 API에서 제거할 수 있습니다.

&nbsp;

## 서블릿 스코프

서블릿 스코프는 서블릿 API에 바인딩된 속성에 대한 접근 범위를 의미합니다.

- ServletContext에 바인딩된 속성은 애플리케이션 전체에서 접근할 수 있으므로 애플리케이션 스코프를 갖습니다. 
- HttpSession에 바인딩된 속성은 그 HttpSession에 해당하는 브라우저에만 접근할 수 있으므로 세션 스코프를 갖습니다.
- HttpServletRequest는 해당 요청/응답에 대해서만 접근하므로 리퀘스트 스코프를 갖습니다.

&nbsp;

| 스코프 종류 | 해당  서블릿 API | 속성의 스코프 |
| --- | --- | --- |
| 애플리케이션 스코프 | ServletContext | 속성은 애플리케이션 전체에 대해 접근 가능 |
| 세션 스코프 | HttpSession | 속성은 브라우저에서만 접근 가능 |
| 리퀘스트 스코프 | HttpServletRequest | 속성은 해당 요청/응답 사이클에서만 접근 가능 |

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승