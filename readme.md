### Project description
This project has been created while taking the course [Master Java Web Services and REST API with Spring Boot](https://www.udemy.com/course/spring-web-services-tutorial/) on Udemy. The application includes basics of creating a database and an adequate REST API.

### Database structure
The database contains two tables: user_details and post which are in the one-to-many relation (multiple posts can be assigned to a single user). 

### List of handled requests

- GET http://localhost:8080/jpa/users - returns all users
- POST http://localhost:8080/jpa/users - saves new user in database. The request requires a json file.
- GET http://localhost:8080/jpa/users/{id} - returns a specific user
- DELETE http://localhost:8080/jpa/users/{id} - deletes a specific user
- GET http://localhost:8080/jpa/users/{id}/posts - returns posts of a specific user
- POST http://localhost:8080/jpa/users/{id}/post - saves a new post assigned to a specific user

Requests concerning the user not preceded by "jpa" also do work, but they are manipulating a hardcoded data (not a real connection to the database). They were used as examples while learning basics of REST API.

### Useful links
- http://localhost:8080/h2-console - allows to monitor the content of the database (JDBC URL: jdbc:h2:mem:testdb)
- https://chrome.google.com/webstore/detail/talend-api-tester-free-ed/aejoelaoggembcahagimdiliamlcdmfm - Google Chrome plugin to send POST and DELETE requests

### Example request bodies
Post an user:
```json
{
  "name": "Jose Arcadio Morales",
  "birthDate": "2000-07-29"
}
```

Post a post:
```json
{
  "description": "That's being responsible"
}
```

### Hello world
Additionally to the database, the project contains helloworld module to provide an example of internationalization. To receive an international greeting, send a get request 
- GET http://localhost:8080/hello-world-internationalized

with an adequate header: Accept-Language:[language] 

Implemented languages are: en (default), nl, it