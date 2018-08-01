# Simple App Using ReactJS as Front End and Spring Boot 2 as the Server and to provide REST Service

## What is the Use of This Repo
This App is a Simple ReactJS and Springboot 2 App which uses

1. ReactJS
 * React Components
 * HTTP Client using axios Library
 * Basic react Routing
 * React Bootstrap
 * Communication between React Components
2. SpringBoot 2
 * Springboot RestController
 * Service, Repository(DAO) from Spring Framework
 * Autowiring is used as well to inject the Dependencies

This Applications template can be copied and used to build other bigger applications.

The CSS used is very basic since the main aim of this project is to focus on React JS

## What Does this Application do

The Application displays a list of customers, and on clicking on a customer it displays more details about the customer

## Prerequites to Run the Application

### Install NodeJS

Refer https://nodejs.org/en/ to install NodeJS

### Install create-react-app
Install create-react-app npm package globally. This will help to easily run the project and also build the source files easily. Use the following command to install create-react-app

```bash
npm install -g create-react-app
```

### Install maven

Install Maven and Ensure IDE is pointing to Right Maven folder

Also Ensure maven is set as a path variable to that maven commands can be run easily

Refer https://maven.apache.org/ for maven installation

## Steps to Run the Application

Clone the repo into local

Open the client folder and install the npm packages using the following commands

```bash
cd client
npm install
```

Go Back to the Parent Project Folder and build the package using the following commands

```bash
cd ..
mvn clean package
```

Go to server folder and start the Application using the following commands

```bash
cd server
mvn spring-boot:run
```

The Application runs on **localhost:8080** and the application runs in a embedded container in local

## Folder Structure

**client** : This has the Client Code implemented using React JS

**server** : This has the Springboot code

**pom.xml** : This is multimodule pom. This pom in turn executes the pom within the client and the server folders

## Application Design

### ReactJS

#### Components

1. **Customers** Component : This Component displays a list of customers. This Component gets the data from a json data by Calling Spring Boot REST API

2. **CustomerDetails** Component : This Component Displays the details of the selected customer. This Component gets its data by Calling the Spring Boot REST API. This Component is the Child Component of *Customers* Component

#### HTTP client

**axios** library is used to make HTTP Calls

#### URL

The application has just one url /customerlist which ties to *Customers* Component

### Springboot 2

The package `com.example.demo` has the `DemoApplication.java` file which ensures that the application runs in an embedded container and forms the starting point of the code

The package `com.example.dao.impl` has the DAO ( Data Access Object ) Defined. The package `com.example.dao` has the interfaces defined for the DAOs.
The **DAO( Data Access Object )** connects to the DataBase and gets the necessary data

The package `com.example.service.impl` has the Services Defined . The package `com.example.service` has the interfaces defined for the Services.
The **Service** is where the business logic is run on the Data which comes from DAO

The package `com.example.controller` has the Rest Controller defined. The controller has all the end points defined and mentions which function should be executed when an end point is called. The Controller also defines which Endpoint Calls which Service

The package `com.example.models` has all the java models defined

The `application.properties` file is used to define various properties such as the port in which the embedded container runs , the context path of the application etc

## Postman Collection

Import the postman collections from `postman` folder into Postman.
This postman collection has all the REST endpoints which are implemented in springboot.

## References

**create-react-app** : The following link has all the commands that can be used with create-react-app
https://github.com/facebook/create-react-app

**ReactJS** : Refer to https://reactjs.org/ to understand the concepts of ReactJS

**React Bootstrap** : Refer to https://react-bootstrap.github.io/getting-started/introduction/ to understand how to use React Bootstrap

**Springboot** : Refer to https://spring.io/guides/gs/rest-service/ to build REST service using Springboot

**axios** : Refer to https://www.npmjs.com/package/axios to know more about how to use axios library to make http requests
