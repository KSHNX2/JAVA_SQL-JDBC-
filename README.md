# JAVA_SQL-JDBC-

출처 : IBM

내용: 기존 PrepareStatement에서 로깅 가능하게 개선된 클래스

사용법:
loggingableStatment 클래스를 패키지에 넣고 사용할 클래스에서 import한다.

사용코드:
Connection con = DriverManager.getConnection("jdbc:h2:tcp://localhost/~/springboot", "sa", "");
String query = "UPDATE member SET pass=?, name = ? WHERE id = ?;";

LoggableStatement pstmt = new LoggableStatement(con, query);
~
system.out.print(pstmt.getQueryString()) // ?가 제거된 완성된 쿼리가 생성된다.
