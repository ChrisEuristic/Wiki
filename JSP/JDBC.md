# JDBC - Database Control

### Database Driver 로드
```java
/* MySQL Driver 예시 */
Class.forName("com.mysql.cj.jdbc.Driver");
```

### Connection 객체 생성
```java
import java.sql.Connection;
Connection con = DriverManager.getConnection(DB URL, DB 계정, DB 비밀번호);
```

### Statement 객체 생성 및 Query 전송
```java
Statement state = con.createStatement();

/* 쿼리 전송 후 결과를 ResultSet 객체에 수신 */
ResultSet resultSet = state.executeQuery("SQL 쿼리문");
```

### preparedStatement 객체 생성 및 Query 전송
```java
/* 클래스명과 함수명 스펠링 주의 */
/* 클래스는 Prepared, 함수는 Prepare */
PreparedStatement preState = con.prepareStatement("SQL 쿼리문");

/* PreparedStatement 객체는 쿼리문 내에 ? 형태로 변수를 삽입할 수 있다. */
preState.setString(몇번째 '?' 인지, 문자열값); // setString()은 SQL 상에서 따옴표가 자동 추가.
preState.setInt(몇번째 '?' 인지, 정수값);
// Date 등도 가능하다.

/* SELECT 쿼리 전송 후 결과를 ResultSet 객체에 수신 */
ResultSet resultSet = preState.executeQuery();

/* CRUD 쿼리 전송 */
preState.executeUpdate();
```

### Cursor Processing
```java
while(resultSet.next()){
  ClassDTO dto = new ClassDTO();
  dto.setFunction1(resultSet.getString(1));
  dto.setFunction2(resultSet.getInt(2));
  dto.setFunction3(resultSet.getString("Attribute"));
  /* 컬럼의 번호나 컬럼명을 적는 방법 모두 유효 */
  ...
}
```
