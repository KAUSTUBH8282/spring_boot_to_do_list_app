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

1. Navigate to the root directory of the backend application (where the `pom.xml` is located)...cd SpringToDo/
2. Open the backend directory in Eclipse IDE or any IDE of your choice that supports Maven projects.
3. Import the project as an existing Maven project.
4. Allow the IDE to resolve dependencies and build the project which may take a few minutes.
5. Once the build is complete, you can run the application by:
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
