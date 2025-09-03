HealthRx Hiring Challenge – Spring Boot Solution

This repository contains a Spring Boot application built to automate the HealthRx Hiring Challenge submission process. The application executes the required API calls automatically on startup and handles query submission based on the registration number.

Project Overview

pom.xml – Maven configuration with dependencies (Spring Boot Web, Lombok, etc.).

src/main/resources/application.properties – Configuration file where you provide your personal details and API endpoints.

src/main/java/com/example/healthrx/ – Main package containing the application code.

HealthRxHiringChallengeApplication.java – Entry point for the Spring Boot app.

dto/ – Contains DTO classes (POJOs) for JSON requests/responses.

service/ApiService.java – Service layer responsible for API interactions using RestTemplate.

runner/ChallengeRunner.java – Implements CommandLineRunner, contains the core challenge logic that executes on startup.

Setup Instructions
1. Configure User Details

Edit src/main/resources/application.properties and replace the placeholder values with your information:

user.name=Your Name  
user.regNo=YOUR_REG_NO  
user.email=your.email@example.com  

2. Add Your SQL Solution (Important)

Check whether the last two digits of your registration number are odd or even.

Solve the respective SQL problem (from the challenge document).

Open ChallengeRunner.java → locate getFinalQueryByRegNo() → replace the placeholder SQL with your actual solution:

if (isOdd) {
    return "SELECT ... your solution for odd case ...;";
} else {
    return "SELECT ... your solution for even case ...;";
}

3. Build the Project

From the project root, package the application using Maven:

mvn clean package


This generates a JAR in the target/ folder (e.g., healthrx-hiring-challenge-0.0.1-SNAPSHOT.jar).

4. Run the Application

Run the JAR to trigger the API workflow:

java -jar target/healthrx-hiring-challenge-0.0.1-SNAPSHOT.jar


The app will execute the logic in ChallengeRunner, print logs, submit the SQL solution, and exit.
