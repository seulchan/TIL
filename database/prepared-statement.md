## Prepared Statement 와 Statement

Statement를 이용해서 데이터베이스와 연동할 경우에는 연동할 때마다 DBMS에서 다시 SQL문을 컴파일해야 하므로 속도가 느리다는 단점이 있습니다.

이럴 경우 PreparedStatement를 이용하면 SQL문을 미리 컴파일해서 재사용하므로 Statement 인터페이스보다 훨씬 빠르게 데이터베이스 작업을 수행할 수 있습니다. 따라서 데이터베이스와 연동할 때 또는 빠른 반복 처리가 필요할 때는 PreparedStatement를 사용해야 합니다.

## PreparedStatement 특징

- PreparedStatement 인터페이스는 Statement 인터페이스를 상속하므로 Statement 인터페이스의 모든 메서드를 사용할 수 있습니다.
- Statement 인터페이스가 DBMS에 전달하는 SQL문은 단순한 문자열이므로 DBMS는 이 문자열을 DBMS가 이해할 수 있도록 컴파일하고 실행합니다. 반면에 PreparedStatement 인터페이스는 컴파일된 SQL문을 DBMS에 전달하여 성능을 향상시킵니다.
- PreparedStatement 인터페이스에서는 실행하려는 SQL문에 '?'를 넣을 수 있습니다. 따라서 '?'의 값만 바꾸어 손쉽게 설정할 수 있어 Statement보다 SQL문 작성하기가 더 간단합니다.

&nbsp;

Excerpt From <자바 웹을 다루는 기술> by 이병승