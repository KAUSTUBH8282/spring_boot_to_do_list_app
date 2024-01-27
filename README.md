# spring-todo

Todo app built with Spring Boot.

<p align="center">
  <img src="https://raw.githubusercontent.com/k435467/django-todo-react/master/demo/django-todo-react-demo.gif" width="300">
</p>

A to-do web app that leverages Spring Boot for the backend and React.js for the frontend.

## Features

- Spring Boot backend with:
  - Spring Web
  - Spring Data JPA
  - Lombok
- React.js frontend
- Axios for API calls

The app follows a layered architecture with models defined in Java, CRUD operations managed by a service class, and a REST API controller to interface with the frontend.

## Table of Contents

- [spring-todo](#spring-todo)
  - [Usage](#usage)
  - [Architecture](#architecture)
    - [DAO](#dao)
  - [Dependencies and Frameworks](#dependencies-and-frameworks)
    - [H2 Database](#h2-database)
    - [Spring Boot DevTools](#spring-boot-devtools)
    - [Lombok](#lombok)
    - [Spring Data JPA](#spring-data-jpa)
    - [Junit](#junit)
    - [Mockito](#mockito)
    - [MockMvc](#mockmvc)
    - [JWT](#jwt)
  - [Tools](#tools)
    - [Postman](#postman)
    - [Swagger](#swagger)
    - [REST Client](#rest-client)
  - [Dependency Injection](#dependency-injection)
    - [Constructor-based](#constructor-based)
    - [Setter-based](#setter-based)
    - [Field-based](#field-based)

## Usage

### Backend Setup

To set up the backend Spring Boot application, follow these steps:

1. Navigate to the root directory of the backend application (where the `pom.xml` is located)
    ```shell
   cd SpringTodo/
2. Open the backend directory in Eclipse IDE or any IDE of your choice that supports Maven projects.
4. Import the project as an existing Maven project.
5. Allow the IDE to resolve dependencies and build the project which may take a few minutes.
6. Once the build is complete, you can run the application by:
   - Using the IDE's built-in features to run Spring Boot applications.
   - Running the main application class as a Java application.
   - Using the Maven command: `./mvnw spring-boot:run` (for Unix systems) or `mvnw spring-boot:run` (for Windows).

The backend server should start, and by default, it will be accessible at `http://localhost:8080`.

### Frontend Setup

To set up the frontend React application, follow these steps:

```shell
# Navigate to the frontend directory
cd frontend/

# Install dependencies
npm install

# Start the React server
npm start

#The frontend Server will be available at this ip address on localHost
The Frontend server should start, and by default, it will be accessible at http://localhost:3000

## Architecture

- Presentation Layer
- Business Layer
- Presistence Layer
- Database

--

- Controller
- Service Layer
- DAO
- Database

### DAO

Data Access Object. It provides an abstract interface and some specific data operations without exposing details of the database.

```java
public interface TodoDao extends CrudRepository<Todo, Integer> {}
```

## Dependencies and Frameworks

### H2 Database

A in memory database. It has a console webpage.

### Spring Boot DevTools

For hot reloading.

### Lombok

Java annotation lib which helps to reduce boilerplate code.

Lombok - IntelliJ IDEA Plugin

- @Getter
- @Setter
- @NoArgsConstructor
- @ToString

### Spring Data JPA

Java Persistence API. Hibernate is a ORM tool and an implementation of JPA.

javax.persistence.\*

- @Entity
- @Table
- @Id
- @GeneratedValue
- @Column

Interface:

- Repository
- CrudRepository
- PagingAndSortingRepository
- JpaRepository

### Junit

Run TEST with Coverage. (Element: Class% / Method% / Line%)

- org.junit.jupiter.api
- @Test
- assertEquals()

AAA patern:

- Arrange
- Act
- Assert

### Mockito

A mocking framework for unit tests in Java.

### MockMvc

Test web layer.

### JWT

JSON Web Token. Usually for auth.

## Tools

### Postman

[Postman](https://www.postman.com/)
is an API platform for building and using APIs.

### Swagger

[Swagger](https://swagger.io/) UI: Visualize OpenAPI Specification definitions.

### REST Client

```text
Method Request-URI HTTP-Version
Header-field: Header-value

Request-Body
```

- IntelliJ IDEA - [HTTP Client](https://www.jetbrains.com/help/idea/http-client-in-product-code-editor.html#creating-http-request-files)

- VSCode - [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)

## Dependency Injection

- Constructor-based dependency injection
- Setter-based dependency injection
- Field-based dependency injection

**@Component** is an annotation that allows Spring to automatically detect our custom beans. Spring will:

- Scan our app for classes anntated with @Component
- Instantiate them and inject any specified dependencies into them
- Inject them wherever needed

Specialized Stereotype Annotations:

- @Controller
- @Service
- @Repository
- @Component
- @CustomComponent

### Constructor-based

It is recommended for required dependencies allowing them to be immutable and preventing them to be null.

```java
@Component
public class ConstructorBasedInjection {

    private final InjectedBean injectedBean;

    @Autowired
    public ConstructorBasedInjection(InjectedBean injectedBean) {
        this.injectedBean = injectedBean;
    }

}
```

### Setter-base

It is recommended for optional dependencies.

```java
@Component
public class ConstructorBasedInjection {

    private InjectedBean injectedBean;

    @Autowired
    public void setInjectedBean(InjectedBean injectedBean) {
        this.injectedBean = injectedBean;
    }

}
```

### Field-base

Not recommended.

```java
@Component
public class ConstructorBasedInjection {

    @Autowired
    private InjectedBean injectedBean;

}
```
