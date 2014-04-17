---
title: Java DataSource Connect への道
date: 2013-05-09 07:50
tags: java
---

Java のはなしを(ry

web.xml にこう書いて

    <resource-ref>
        <res-ref-name>jdbc/name</res-ref-name>
        <res-type>javax.sql.DataSource</res-type>
        <res-auth>Container</res-auth>
    </resource-ref>

context.xml にはこう書いて META-INF の下みたいなところにつっこんでおく。

    <?xml version='1.0' encoding='utf-8'?>
    <Context>
        <Resource
            name="jdbc/name"
            auth="Container"
            type="javax.sql.DataSource"
            driverClassName="com.mysql.jdbc.Driver"
            url="jdbc:mysql://localhost:3306/dbname?autoReconnect=true&amp;characterEncoding=UTF8&amp;zeroDateTimeBehavior=convertToNull"
            username="user"
            password="pass"
            maxActive="100"
            maxIdle="10"
            maxWait="10000"
            testOnBorrow="true"
            validationQuery="SELECT 1"
            removeAbandoned="true"
            removeAbandonedTimeout="100"
            logAbandoned="true"
            />
        <Resource
            name="jdbc/name2"
            こんな感じに複数定義可能。paramは上と同じ感じなので略。
            />
    </Context>

validationQuery は死活監視のために発行するSQLにあたるようだ。

