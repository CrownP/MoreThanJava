```java
//1.生命数据库驱动、数据库url、账号、密码
String driver = "数据库驱动名称"
String url = "数据库连接地址"
String user = "用来连接数据库的用户名"；
String pwd = "用来连接数据库的密码"；
//2.加载驱动
Class.forName(driver);
//3.根据url创建数据库连接
Connection con = DriverManage.getConnection(url, user, pwd);
//4.用数据库连接对象创建Statement对象（或PrepareStatement,其执行扫描的结果集比Statement大）
Statement s = con.createStatement();
或
PrepareStatement ps = con.PrepareStatement(sql);
//5.做数据库的增删改查工作
ResultSet rs = s.executeQuery();
//6.关闭结果集对象 ResultSet,Statement,Connection
rs.close();
s.close();
con.close();
//各个步骤异常处理
```

