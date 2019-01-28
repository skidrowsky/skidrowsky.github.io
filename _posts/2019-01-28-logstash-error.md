---
title: "Logstash error 해결 내용"
date: 2019-01-28 09:00:30 -0400
categories: elastic
---

logstash pipeline 실행하였을 때, 다음의 오류가 발생하였음.
실행 구문은 아래와 같음
'''
logstash -f sql_customers.conf

sql_customers.conf 파일 내용
input {
  jdbc {
    jdbc_connection_string => "jdbc:sqlserver://60.100.94.85:1433;databaseName=Northwind;integratedSecurity=true;"
    jdbc_driver_class => "com.microsoft.sqlserver.jdbc.SQLServerDriver"
    jdbc_user => "xxx"
    statement => "select * from Customers"
  }
}

output {
  elasticsearch {
    hosts => ["localhost:9200"]
    index => "customers"
  }
}
'''
Error jdbc_driver_library not loaded
