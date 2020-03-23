# QAChallenge
QA challenge

Scope and Overview

The scope of this project is to validate features and functionality of the User API Service of the API pet store.
I selected to test the User API since this service allows to create, update, delete, log in and log out users of the pet store API.
This module of user is the entrance to the other 2 services Pet and Order, if this module it is not working then this would mean the user would not be allow to access, create,  update, delete a Pet or an Order for instance the user would not be able to use the pet store service.
From the Stakeholder and product owner’s side without this working module the business continuity would be impacted since there would be no users to place orders and pet to sell.
Currently my testing experience is focus con Manual and is focus on testing from the user side (UAT), so this challenge has a bigger complexity since my automation experience is minimal. Since November of 2019 I have been taking online courses to learn to automate test since this is a subject I’m interested on learning but I would never developed a project like this.
I would approach this challenge in 2 ways validating a happy path
1.	Manual Functional Testing (automated with postman)
2.	BDD Testing


APROACH POSTMAN TOOL INSTALLATION
Prerequisite: tool Postman should be install on the computer, 
1.	Open postman tool
2.	Click on import button
3.	Import file “User Service -Swagger Petstore.postman_collection.json”
4.	Open run collection
5.	Upload data file “adidas Challenge Postman data.csv”
6.	Order of the run sould be 



BDD APPROACH INSTALLATION
Prerequisite: tool intellij or eclipse should be install on the computer

1.	On the folder BDD approach , download folder “petstoreapi”
2.	Open or create a project with a file , select the path where folder “petstoreapi”
3.	Open terminal and execute cmd line mvn clean verify
4.	On the project Go to the folder /target/site/serenity and open with browser the file “index.html” to view the execution report


