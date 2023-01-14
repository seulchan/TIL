# OSI 7계층과 TCP/IP

<img src="../images/osi-tcp.png" alt="http" width="600" style="margin-left: auto; margin-right: auto; display: block;"/>

&nbsp;

## OSI 7계층 

1~4 계층을 Data Flow Layer 또는 Lower Lyaer라고 부르고 5~7 계층을 Applicaion Layer 또는 Upper Layer라고 부릅니다. 이러한 계층 분류는 계층의 역할과 목표에 따른 것입니다. Data Flow Layer는 용어에서 의미하는 대로 데이터를 상대방에게 잘 전달하는 역할을 가지고 있습니다.

- 애프리케이션 개발자는 Applicaion Layer 프로토콜을 개발할 때 하위 data flow layer를 고려하지 않고 데이터를 표현하는 데 초점을 맞춥니다. 
- 반대로  애플리케이션 계층은 애플리케이션 개발자들이 고려해야 할 영역이므로 네트워크 엔지니어는 이 부분에 대해서는 일반적으로 심각하게 고려하지 않습니다. 
- 이런 이유로 애플리케이션 개발자는 하향식(Top-Down)형식으로 네트워크를 바라보고 네트워크 엔지니어는 상향식(Bottom-Up)형식으로 네트워크를 인식합니다.

&nbsp;

## TCP/IP 프로토콜 스택

OSI 레퍼런스 모델은 7계층으로 이루어진 반면, TCP/IP 모델은 4계층으로 구분합니다. OSI 7계층은 data flow layer와 application layer로 구분할 수 있습니다. 이 두 계층의 구분은 데이터를 만드는 애플리케이션 부분과 이 데이터를 잘 전달하는 데 집중하는 하부 계층으로 구분하는 것이 목적이었습니다. 그러다 보니 자연스럽게 애플리케이션 개발자가 고려해야 할 부분과 서버 엔지니어나 네트워크 엔지니어가 고려해야 할 부분이 구분되었는데 TCP/IP 모델은 그 구분이 더 확연히 드러납니다. 상위 3개 계층을 하나의 애플리케이션 계층으로 묶고 1,2 계층 즉 물리 계층과 데이터 링크 계층을 하나의 네트워크 계층으로 구분합니다.