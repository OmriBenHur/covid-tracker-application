# Project Title:

A COVID-19 Tracker Web Application.

## 1. Project Description: 

A Java Spring Boot Web application for tracking global Corona Virus (COVID-19) cases.

## 2. Tech Stack:

- HTML / Bootstrap
- JavaScript 
- Java 11
- Spring Boot 2.7.5
- Maven
- Intellij IDE

Spring Dependencies:
- Spring Web
- Thymeleaf 
- Spring Boot Dev Tools

## 3. Data source used: 

COVID-19 Data Repository by the Center for Systems Science and Engineering (CSSE) at Johns Hopkins University

https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series

## 4. Installation:

i. Clone the git repo

```
https://github.com/AAdewunmi/covid-tracker-application.git
```

ii. Open project folder

iii. Explore

## 5. How To Use:

- Run CovidTrackerApplication.java in Intellij IDE.

- Open http://localhost:8080 in any web browser and view.

## 6. Demo (UI Screenshot):

![This is an image](src/main/java/com/application/covidtrackerapplication/images/Screenshot.png)

## 7. Contribution:

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Adapted from:

UDEMY: Java Development Mega Course: Build Projects Practically

(Java Programming Course: Learn Development of JAVA Projects Using JSP, JDBC, Servlets, Swing, Spring Boot, Maven, Hibernate)

Project Name: Project 39: Covid Information Tracker

Created by: Engineering.Org.In

Last updated: 09/2022

URL: https://www.udemy.com/course/build-real-world-java-projects-using-spring-jsp-jdbc/



######################################################################################################################

ii. CI jenkins pipline with sonarqube, maven and nexus ducumentation:

## 1. docker compose up to run all three containers: Jenkins, sonarqube server and nexus

## 1. jenkins runs on port 8080

## 2. sonarqube runs on port 9000

## 3. nexus runs on port 8081


## 2. open jenkins on http://localhost:8080

follow the setup wizards default settings (install recommended packages)
and configure the system as follows 

downlload the following plugin on jenkins:
<img width="672" alt="pl" src="https://user-images.githubusercontent.com/110596448/200188509-a86777bd-5f13-4c95-8e7f-1c1bb466f633.PNG">
<img width="667" alt="pl1" src="https://user-images.githubusercontent.com/110596448/200188510-7c6b6133-03e7-4ab2-988f-b16ee703cf6a.PNG">
<img width="665" alt="pl2" src="https://user-images.githubusercontent.com/110596448/200188511-cedbff77-23ac-4148-be42-564d5fa26d07.PNG">


next, under mange jenkins, global tool configuration; configure the following
<img width="834" alt="Capture" src="https://user-images.githubusercontent.com/110596448/200188578-651875b1-4868-42f0-b327-0c42aa6bd7ce.PNG">
<img width="833" alt="2" src="https://user-images.githubusercontent.com/110596448/200188582-025228b0-11dd-49cd-97af-913b59586be2.PNG">
<img width="824" alt="3" src="https://user-images.githubusercontent.com/110596448/200188587-c2ec8a96-2ce7-4ea5-892e-f99e3fcc16bc.PNG">


next, under mange jenkins, configure system; configure the following;
<img width="826" alt="Capture1" src="https://user-images.githubusercontent.com/110596448/200188626-c7200707-a081-4055-b7c7-701767c20f39.PNG">


## 3. open sonarqube on http://localhost:9000

you will be prompted to enter a user name and password, enter the following:

username: admin

password: admin

then you will have to create a new password, and log back in to sonarqube.

you will have to create a token for jenkins to use; 

once you are logged in to sonarqube, go to administration, security, global permissions;
<img width="827" alt="5" src="https://user-images.githubusercontent.com/110596448/200188909-a902380d-3732-4cbd-bd6e-49d95b0e7ac8.PNG">


enable execute analysis for your'e user(for demonstration purposes i showed the admin user.
<img width="824" alt="6" src="https://user-images.githubusercontent.com/110596448/200189361-bfde30dd-ab62-456d-aeb0-5357963ed048.PNG">

then under security,  select users from the drop down list, and select on the icon below "token"
<img width="822" alt="7" src="https://user-images.githubusercontent.com/110596448/200189418-4f39fecd-500e-48b6-b698-d6ef011686b3.PNG">

enter a name for your token (for internal use only) and click generate.
<img width="833" alt="8" src="https://user-images.githubusercontent.com/110596448/200189450-b10524fd-d5ac-4749-b5a8-6b2199a5ebff.PNG">

copy the token and temporarly write in down somewhere safe, you will not be able to view it again.

## 4. open nexus on http://localhost:8081

continue the initil setup (same as sonarqube).

change your pasword and write it down temporarly somewhere safe.


## 5. return to jenkins.

go to manage jenkins, credentials, system, global credentials; create and configure the credentials as shown the image with the previous steps information;
<img width="835" alt="4" src="https://user-images.githubusercontent.com/110596448/200189875-f5b5b7b5-fee7-49b1-9f4d-d0914ad15bf7.PNG">

next in the dashboard, create new item, choose pipline and enter a name for your pipline.
<img width="749" alt="10" src="https://user-images.githubusercontent.com/110596448/200190085-ddb2752c-a09a-4448-a383-4ee2803dbbc7.PNG">

scroll down and paste the contents of the jenkinsfile found in the docker folder

<img width="924" alt="11" src="https://user-images.githubusercontent.com/110596448/200190130-e6d3f0cd-a49e-476d-8782-51936f192da5.PNG">



## 6. that's it!

you can now run the job and it will clone this repo, analyze it by sonarqube, package it with maven and finally upload the application's .war file to nexus.




 
