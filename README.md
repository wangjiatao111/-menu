# -
菜谱
=====
一个菜谱小程序，前端使用微信小程序，使用java搭建的javaweb项目进行服务，使用mysql
需要修改的地方：
-----
一、后台服务端：
----
1：地址：ssm/src/main/resources/applicationContext.xml将password改成自己数据库的密码
```/xml
<bean id="dataSource" class="com.mchange.v2.c3p0.ComboPooledDataSource">
<property name="driverClass" value="com.mysql.jdbc.Driver"/>
    <property name="jdbcUrl" value="jdbc:mysql:///epicure"/>
    <property name="user" value="root"/>
    <property name="password" value="修改这里"/>         换成自己的数据库密码
</bean>
```
二、小程序端：
----
1.地址：微信小程序端\app.js
```/javascript
globalData: {
    userInfo: null,
    url:"修改这里"      //换成自己的本地链接地址：http://localhost:8080/account/  
}
```
2.地址：微信小程序端\app.js（同1一样）
```/javascript
 data: {
            'code': res.code,
            'from': '修改这里',      换成自己小程序的appid
            'secret':'修改这里'      换成自己小程序的密匙（可以在自己的微信公众平台上查看）
          },
```
 运行方式
 ----
 ##1.使用微信开发者工具将微信小程序端导入，不使用云开发，换成自己的appid<br>
 ##2.将数据库.sql导入<br>
 ##3.使用tomcat运行小程序后台服务端（我之前是直接使用idea导入再将其运行）<br>
 
