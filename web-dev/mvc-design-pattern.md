# MVC 디자인 패턴

MVC란 Model-View-Controller의 약자로, 일반 PC 프로그램 개발에 사용되는 디자인 패턴을 웹 애플리케이션에 도입한 것입니다. 즉, 웹 애플리케이션을 화면 부분, 요청 처리 부분, 로직 처리 부분으로 나누어 개발하는 방법이죠.

&nbsp;

## MVC의 특징

- 각 기능이 분리되어 있어 개발 및 유지보수가 편리합니다.
- 각 기능의 재사용성이 높아집니다.
- 디자이너와 개발자의 작업을 분업화해서 쉽게 개발할 수 있습니다.

&nbsp;

## MVC의 구성 요소와 기능

&nbsp;

<img src="../images/model2.png" alt="model2" width="500" style="margin-left: auto; margin-right: auto; display: block;"/>

&nbsp;


### Controller

- 서블릿이 컨트롤러의 역할을 합니다.
- 클라이언트의 요청을 분석합니다.
- 요청에 대해서 필요한 모델을 호출합니다.
- Model에서 처리한 결과를 보여주기 위해 JSP를 선택합니다.

### Model

- 데이터베이스연동과 같은 비즈니스 로직을 수행합니다.
- 일반적으로 DAO와 VO 클래스로 이루어져 있습니다.

### View

- JSP가 화면 기능을 담당합니다.
- Model에서 처리한 결과를 화면에 표시합니다.