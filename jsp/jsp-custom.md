# 커스텀 태그

액션 태그나 표현 언어를 사용하더라도 조건식이나 반복문에서는 여전히 자바 코드를 사용하고 있습니다. 이러한 자바 코드를 제거하기 위해 JSTL이나 커스텀 태그가 등장했습니다. 커스텀 태그란 JSP 페이지에서 자주 사용하는 자바 코드를 대체하기 위해 만든 태그입니다.

커스텀 태그의 종류는 다음 두 가지 입니다.

- JSTL (JSP Standard Tag Library) : JSP 페이지에서 가장 많이 사용하는 기능을 태그로 제공하며, JSTL 라이브러리를 따로 설치해서 사용합니다.
- 개발자가 만든 커스텀 태그: 개발자가 필요에 의해 만든 태그로, 스트러츠나 스프링 프레임워크에서 미리 만들어서 제공합니다.

&nbsp;

## JSTL

### 여러 가지 JSTL 태그 종류

| 라이브러리 | 세부 기능 | 접두어 | 관련 URI |
|:---|:---|:---|:---|
| 코어 | 변수 지원, 흐름 제어, 반복문 처리, URL 처리 | c | http://java.sun.com/jsp/jstl/core |
| 국제화 | 지역, 메시지 형식, 숫자 및 날짜 형식 | fmt | http://java.sun.com/jsp/jstl/fmt |
| XML | XML 코어, 흐름 제어, XML 변환 | x | http://java.sun.com/jsp/jstl/xml |
| 데이터 베이스 | SQL | sql | http://java.sun.com/jsp/jstl/sql |
| 함수 | 컬렉션 처리, 문자열 처리 | fn | http://java.sun.com/jsp/jstl/functions |

&nbsp;