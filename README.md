# Solution

## Overview

1. Notes API created with spring boot framework.
2. Backed by MySQL database.
3. Rate limiting implemented using Bucker library.

## Run Locally

1. Install and run mysql locally.
2. Create user `notesuser` with `notespwd`.
3. Create database `notes-db` and grant access to it for `notesuser`.
4. Can run MySQL in docker.

	`docker run --name=mysql-db -p 3306:3306 -e MYSQL_DATABASE=notes-db -e MYSQL_USER=notesuser -e MYSQL_PASSWORD=notespwd -e MYSQL_ROOT_PASSWORD=notespwd -d mysql:5.7`

5. Run API locally

	```bash
	$ mvn clean package -DskipTests
	$ mvn  spring-boot:run -Dspring-boot.run.arguments="--MYSQL_HOST=localhost --MYSQL_USER=notesuser --MYSQL_PWD=notespwd"
	```

6. Run Unit Tests

	`mvn -Dtest=*Unit* test`

7. Run Integration Tests

	`mvn -Dtest=*Integration* test`

## Run Locally In Docker

### Run Build

`docker-compose run app-build`

### Run Unit Tests

`docker-compose run unit-test`

### Run Integration Tests

`docker-compose run it-test`

### Run MySQL DB

`docker-compose run -d db`

### Run Spring Boot API

`docker-compose run -d app`
