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


Manual Functional Testing
For this approach I selected the tools Postman since I have worked with this tool on my current job however, I never used automation tool but since postman has snippets for test creation it was easier to work with.
The following activities were set in order to execute this project
Review selected API Requests:
Using the information about the services on “https://petstore.swagger.io/#/”, I identify  8 requests for this API which are:
-	Create user : https://petstore.swagger.io/v2/user
-	Create user with Array : https://petstore.swagger.io/v2/user/createWithArray
-	Create user with List : https://petstore.swagger.io/v2/user/createWithList
-	Find user by username : https://petstore.swagger.io/v2/user/{username}
-	Update user : https://petstore.swagger.io/v2/user/{username}
-	Delete user : https://petstore.swagger.io/v2/user/{username}
-	Log in user : https://petstore.swagger.io/v2/login
-	Log out : https://petstore.swagger.io/v2/logout
Stablish functionalities to test:
For each request the features to validate are
-	Status code
-	Request Structure
-	Response Structure
-	Data type on the response structure
-	Data values on the response structure
-	Response Header Structure
-	Response Header Values
-	Schema Validation

Create test scenarios : 
The scenarios were created base on the happy path approach and although negative scenarios were taken in consideration but would not be executed. I usually create test cases scenarios with the use of an excel "Adidas QA Challenge.xls".

Create data file
A data file was created since some params and body values were set as variables and to have more iterations on the execution. For Create user With Array and List I was not able to handle those variables correctly so those data are static on the postman configuration.

Set up Postman with API service:
API service was imported by raw data using the son configuration find in the swagger page. Since only we were going to test User services, Pet and Order APIs were deleted.

Prerequisite: tool Postman should be install on the computer, 
1.	Download and un zip file "Postman approach.zip"
2.  Open postman tool
3.	Click on import button
4.	Import file “User Service -Swagger Petstore.postman_collection.json”
5.	Open run collection
6.	Upload data file “adidas Challenge Postman data.csv” on the data field
7.	Order of the run should be : 
-	POST Create User
-	POST Create user with input array 
-	POST Create user with input array
-	GET User by Username
-	Get Log in user
-	PUT Update user
-	DEL Delete User
-	GET Log out
8.	Click on Run the collection
 
BDD Approach

For this approach the tools I used maven tool with the dependencies of Cucumber and Serenity to implemented, write test cases since it would be a BDD framework and in order to document all the executed test cases and runs in a report Serenity offers this feature.
The following activities were set in order to execute this project
Review selected API request:
Using the information about the services on “https://petstore.swagger.io/#/”, I identify  8 requests for this API which are:
-	Create user : https://petstore.swagger.io/v2/user
-	Create user with Array : https://petstore.swagger.io/v2/user/createWithArray
-	Create user with List : https://petstore.swagger.io/v2/user/createWithList
-	Find user by username : https://petstore.swagger.io/v2/user/{username}
-	Update user : https://petstore.swagger.io/v2/user/{username}
-	Delete user : https://petstore.swagger.io/v2/user/{username}
-	Log in user : https://petstore.swagger.io/v2/login
-	Log out : https://petstore.swagger.io/v2/logout
Stablish functionalities to test:
For BBD I focus was taken with and e2e scenarios:
-	Create single user
-	Find Register User
-	User updates information
-	Created user logs in
-	Delete Registered User
-	User logs out
Create test scenarios in gherkin:
 The following scenarios were created to test all e2e flow

Scenario 1: Create single user on the pet store

    Given the pet store API is available
    And admin user has a user request with id 1
    And admin user has a user request with username user20
    And admin user has a user request with firstName Constanza
    And admin user has a user request with lastName Pinilla
    And admin user has a user request with email test@gmail.com
    And admin user has a user request with password test123
    And admin user has a user request with phone 3125944659
    And admin user has a user request with userStatus 1
    When an admin submit  the user request
    Then pet store API creates user with details


Scenario 2: Find Register User by username on the pet store

    Given the pet store API is available
    When a user search for the user20 in the pet store
    Then pet store API retuns user details

Scenario 3 : User updates information on the pet store

    Given the pet store API is available
    And User has a user wants to update id information with 1
    And User has a user wants to update username with user40
    And User has a user wants to update firstName with Andrea
    And User has a user wants to update lastName with Pinilla
    And User has a user wants to update email with test@gmail.com
    And User has a user wants to update password with test123
    And User has a user wants to update phone with 3125944659
    And User has a user wants to update userStatus with 1
    When a user submit information for the user20 in the pet store
    Then pet store API updates user with details

Scenario 4:  Created user logs into the pet store API

    Given the pet store API is available
    And user has a Username user20
    And user has a Password test123
    When a user submit the credentials on the pet store
    Then pet store API logged in the pet store user

Scenario 5: Delete Registered User by username on the pet store

    Given the pet store API is available
    When a user submits delete request for the user20 in the pet store
    Then pet store API deletes user


Scenario 6 :  User logs out of the pet store API

    Given the pet store API is available
    When a user submit the log out option on the pet store
    Then pet store API logged out user from the pet store user


BDD APPROACH INSTALLATION
Prerequisite: tool intellij or eclipse should be install on the computer

1.	Download and un zip file "BDD approach.zip"
2.  Open or create a project with the path “BDD approach/petstoreapi”
3.	Open terminal and execute command  mvn clean verify
4.	On the project Go to the folder /target/site/serenity and open with browser the file “index.html” to view the execution report


Risk Analysis

Delivering time
This was the highest risk since I took 2 approaches to resolve the challenge, planning and executing processes took a lot of time for the BBD approach which could not be tested all the request of the user API and had to have in mind the time to document the challenge
Covered all functionalities: 
Due time, both approaches and knowledge this was a low risk, since the object of this challenge is Quality instead of quantity but still was no able to cover all API functionalities and features


Results and conclusions

Approach Functional Testing:
-	Test case were created to validate a happy path for each requested
-	Delete user request could not be possible to test since in all the iterations it failed with and error code 500 and I was not able to fix this or to find the cause of this error.
-	Negative test cases were not created to due to the lack of time but were on the scope.
-	Couldn’t use a data file to test request Create with Array and create with list since I didn’t have the knowledge or time to understand it and implemented. Unfortunately, I had to set up static values instead of variables.
BDD Testing:
-	Test case were created to validate a happy path for each requested
-	Delete user request could not be possible to test since in all the iterations it failed with and error code 500 and I was not able to fix this or to find the cause of this error.
-	Negative test cases were not created to due to the lack of time but were on the scope.
-	Couldn’t test request Create with Array and create with list since I didn’t have the knowledge or time to understand it and implemented.


