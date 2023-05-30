# Spring Boot Login example with Spring Security, MySQL and JWT

- Appropriate Flow for User Login and Registration with JWT
- Spring Boot Rest Api Architecture with Spring Security
- How to configure Spring Security to work with JWT
- How to define Data Models and association for Authentication and Authorization
- Way to use Spring Data JPA to interact with MySQL Database

## User Registration, Login and Authorization process.
![spring-boot-login-example-flow](https://github.com/ramanbajpai7/SignUp-Login-using-SpringBoot/assets/84241394/c31865b3-1d07-4b50-9840-46ffaff0dbc1)



## Spring Boot Server Architecture with Spring Security
You can have an overview of our Spring Boot Server with the diagram below:
![spring-boot-login-example-architecture](https://github.com/ramanbajpai7/SignUp-Login-using-SpringBoot/assets/84241394/8b539b51-2a37-49f8-8d45-14d2cb1a47af)


## Dependency
– If you want to use PostgreSQL:
```xml
<dependency>
  <groupId>org.postgresql</groupId>
  <artifactId>postgresql</artifactId>
  <scope>runtime</scope>
</dependency>
```
– or MySQL:
```xml
<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <scope>runtime</scope>
</dependency>
```
## Configure Spring Datasource, JPA, App properties
Open `src/main/resources/application.properties`
- For PostgreSQL:
```
spring.datasource.url= jdbc:postgresql://localhost:5432/testdb
spring.datasource.username= postgres
spring.datasource.password= 123

spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation= true
spring.jpa.properties.hibernate.dialect= org.hibernate.dialect.PostgreSQLDialect

# Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto= update

# App Properties
bezkoder.app.jwtSecret= bezKoderSecretKey
bezkoder.app.jwtExpirationMs= 86400000
```
- For MySQL
```
spring.datasource.url= jdbc:mysql://localhost:3306/testdb?useSSL=false
spring.datasource.username= root
spring.datasource.password= 123456

spring.jpa.properties.hibernate.dialect= org.hibernate.dialect.MySQL5InnoDBDialect
spring.jpa.hibernate.ddl-auto= update

# App Properties
bezkoder.app.jwtSecret= bezKoderSecretKey
bezkoder.app.jwtExpirationMs= 86400000
```

```
mvn spring-boot:run
```

## Run following SQL insert statements
```
INSERT INTO roles(name) VALUES('ROLE_USER');
INSERT INTO roles(name) VALUES('ROLE_MODERATOR');
INSERT INTO roles(name) VALUES('ROLE_ADMIN');
```
## Database Exploration
![H2](https://github.com/ramanbajpai7/Login/assets/84241394/7d597218-8605-46c9-b8cf-fe2a12ee6f67)

You can explore the database using the H2-Console. Access it at `http://localhost:8080/h2-console`. Please note that the H2-Console is provided for demo purposes only.

## Backend
![SETUP](https://github.com/ramanbajpai7/Login/assets/84241394/b26de4e0-de47-49fb-8bdc-3ea803ea20dc)

The demo includes three user accounts with different access levels:

- Admin: Username - admin, Password - admin
- User: Username - user, Password - password
- Disabled: Username - disabled, Password - password (this account is deactivated)
## Steps to run the Project

1. Clone the repository:

   ```shell
   git clone https://github.com/your-username/jwt-spring-security-demo.git
   ```

2. Navigate to the project directory:

   ```shell
   cd jwt-spring-security-demo
   ```

3. Start the application with the Spring Boot Maven plugin:

   ```shell
   mvn spring-boot:run
   ```

4. The application will run on `http://localhost:8080`.
## Requirements

- Maven 3.6.x
- Java 11
- Postman
- Rest API
