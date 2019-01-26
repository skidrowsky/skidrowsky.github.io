Logstash conf 파일
(C:\ELK\logstash-6.1.2\bin\testsqlserver.conf)
파일 내용 :
input {
  jdbc {
    jdbc_connection_string => "jdbc:sqlserver://localhost:1433;databaseName=Northwind;integratedSecurity=true;"
    jdbc_driver_class => "com.microsoft.sqlserver.jdbc.SQLServerDriver"
    jdbc_user => "xxx"

    statement => "SELECT * FROM Customers"
  }
}

output {
  elasticsearch {
    hosts => ["localhost:9200"]
    index => "northwind_customers"
  }
}

로그스태시 실행
![logstash_import_sql](https://user-images.githubusercontent.com/25881203/51785118-7a2b9b80-2196-11e9-9f77-13c951c6853d.png)

*문제점 및 해결 내용 : Logstash 실행시 아래 오류 발생하였고 JDK 버전 아래 bin 디렉토리로 sqljdbc_auth.dll 파일이 존재하지 않아 발생하는 문제.  
Failed to load the sqljdbc_auth.dll cause :- no sqljdbc_auth in java.library.path

해결책 : JDBC 파일 설치 한 다음 아래 파일을 찾아서 
![sqljdbc_auth_path](https://user-images.githubusercontent.com/25881203/51785126-992a2d80-2196-11e9-8d57-28b0e0981478.png)
아래 경로로 복사
![sqljdbc_auth_targetpath](https://user-images.githubusercontent.com/25881203/51785135-a34c2c00-2196-11e9-8195-738508451f5a.png)

