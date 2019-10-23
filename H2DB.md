## Spring Boot H2DBを利用してデータの確認をする方法

### アプリケーションプロパティに以下の設定をする
/src/main/resources/application.properties
```
spring.datasource.data-source-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:demodb
spring.datasource.username=sa
spring.datasource.password=aaa
```
設定しない場合はデフォルトで以下のようになる
```
spring.datasource.data-source-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=
```

### アプリケーションプロパティに以下のように追加しコンソールが使えるようにする

アプリケーションプロパティに以下の設定をする
/src/main/resources/application.properties
```
spring.h2.console.enabled=true
```

ブラウザで「http://localhost:8080/h2-console」 にアクセス
アプリケーションプロパティに設定した情報を入力
>Driver Class：org.h2.Driver  
>JDBC URL：jdbc:h2:mem:demodb  
>User Name：sa  
>Password：aaa  

コンソールが使用できるようになる。
