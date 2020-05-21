# Docker-Spring-Boot-JPA-MySQL
Deploying Spring  Boot Application to the Docker with MySQL DataBase

## Topics Covered
* Repo mainly covers deploying spring boot application to the docker with mysql as database.
* This Example covers wriring simple & robust web services using HTTP Methods of GET & POST.
* Also covers Many To Many Real time example with Annotation.
* Proper way of handling exception & also code clean & maintainance
* Clinet App for testing the rest services.


## Running Spring rest locally

You can then access Restfull here: https://github.com/Sudarshan-Gowda/Docker-Spring-Boot-JPA-MySQL


## In case you find a bug/suggested improvement for Spring Restfull Webservices
Our issue tracker is available here: https://github.com/Docker-Spring-Boot-JPA-MySQL/issues


## Working with Rest in Eclipse

### prerequisites
The following items should be installed in your system:
* Tool - STS(Spring Toot Suite) or Eclipse
* Server - Apache Tomcat 7
* Database - MySQL
* Postman - Optional (Can use client API)
* Docker Clinet

### Steps:

1) Download this Project and do maven import.
```
git clone https://github.com/Sudarshan-Gowda/Docker-Spring-Boot-JPA-MySQL.git
```
2) To Import the Praject Using STS or Eclipse.
```
File -> Import -> Maven -> Existing Maven project
```


## Looking for something in particular?

|Spring Boot Configuration | Class or Java property files  |
|--------------------------|---|
|The Docker File| [DockerFile](https://github.com/Sudarshan-Gowda/Docker-Spring-Boot-JPA-MySQL/DockerFile) |


## Steps to test the application:

### Docker
1) Download and install the docker in your machine
2) Pull out mysql image and run it as container from the below url
 ` docker run --name mysql-standalone -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=research -e MYSQL_USER=user -e MYSQL_PASSWORD=password -d -p 3306:3306 mysql:5.7 `
3) Once the mysql container  is installed, lets focus on creating our rest api image creation from below steps.

### 
1) Go to your project directory and build the jar file from the command line `mvn clean install`, if your using maven plugin means.
2) Then to build the docker image use the below command,
    `docker build -t spring-boot-mysql .`
3) Then you can list out the images to check the docker images has been build successfully or not,
   `docker image`
4) Not we need to run the docker images and need to map it to the mysql running images right, lets  do it by using below command,
  `docker run -p 7000:7000 --name spring-boot-mysql --link mysql-standalone:mysql -d spring-boot-mysql`
5) Thats all now we can access the deployed application from the port 7000.


1) Once the application is installed properly, Run the application
2) Once the application is deployed properly you can start to test the api's
3) Find the below exposed urls to test the application.
	```	
	a. To fetch all the course details
	http://localhost:7000/employees

	b. To register the student (POST Method)
	http://localhost:7000/employees
  {
    "empName": "Meera",
    "empDob": "2019-09-11T11:32:17.000+0000",
    "empEmail": "meera@gmail.com",
    "empExperience": 3
  }

	```
   
# Contributing

The [issue tracker](https://github.com/Sudarshan-Gowda/Spring-Mvc-Rest-API-And-Client-App/issues) is the preferred channel for bug reports, features requests and submitting pull requests.

