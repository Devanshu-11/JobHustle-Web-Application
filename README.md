INTRODUCTION:
-------------
        • Implemented a user authentication with features like login and registration using bcrypt
        • User and Jobs APIs to handle operations like user profile management, job posting, updating, and deleting.
        • Enable users to filter jobs based on various criteria, such as location, industry, or job type, and implement sorting options to customize the display of results.
        • Provide comprehensive API documentation to assist developers in understanding and integrating with your job

TECHNOLOGIES USED:
-------------------
* JavaScript
* NodeJs  
* Express(framework)
* Mongoose

To Run Project:
-------------------
* npm run server


DEPENDENCIES INSTALLED:
------------------------

      * bcryptjs
      * colors
      * cors
      * dotenv
      * express
      * express-async-errors
      * express-mongo-sanitize
      * express-rate-limit
      * jsonwebtoken
      * mongoose
      * morgan
      * nodemon
      * validator


CONFIGURATION : 
---------------
    In this folder, I have given all the values that can change in the application when used on different environment and systems. The DataBase information is also given in this folder.

MODELS :
--------
    I have created 2 models here namely, 
        * Job Model
        * user Model


CONTROLLERS : 
-------------
     This is the place where all the functionalities are defined for all the models present in the application. All the functionalities are accessed by using APIs from the authenticated and authorized users.

     AUTH CONTROLLER:
     ----------------
        This the place where the user will be redirected when they want to sign up or sign in to the application. User who are signed in will be authenticated and be given with JSON WEB TOKENS, by using that tokens only the user can access the functionalities of the application.
    
     JOBS CONTROLLER:
     --------------------
        In this file, authenticated user can Create, update, find one, find All or delete the categories in the application.

     TEST CONTROLLER:
     ------------------
        In this file, the User will abe to test his application, whether it is running properly or not and change accordingly.

     USER CONTROLLER:
     ----------------
        In this file, authenticated use will have the accessability to create or update the new cart. Finally everything present in that cart will be displayed to the user along with the total price of the cart.

MIDDLEWARE:
-----------
      This is the folder where every API requests are validated, also every user is authenticated and authorized using json web tokens.

ROUTES:
-------
      This is the folder where every API call source is present, for each API call control is transferred to the correct controller file where all the functionalities are done. Before passing the control to the controllers, middlewares are called to check the authenticity and validation of the API call.


All API:
-------------

**1.** TEST API
```terminal
Post method- (Body, raw,json)
http://localhost:8080/api/v1/test/test-post 
{"firstName":"Enter Your First Name"}
```


**2.** REGISTER API
```terminal
Post method- (Body, raw,json)
http://localhost:8080/api/v1/auth/register
{
    "firstName":"Enter Your First Name",
    "email":"Enter Your E-mail",
    "password":"Enter Your Password"
}
```



**3.** LOGIN API
```terminal
Post method- (Body, raw,json)
http://localhost:8080/api/v1/auth/login
{
    "email":"Enter Your E-mail",
    "password":"Enter Your Password"
}
```


**4.** UPDATE API
```terminal
Put method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/user/update-user
{
    "firstName":"Enter Your First Name",
    "email":"Enter your Email",
    "lastName":"Enter Your Last Name",
    "location":"Enter Your location"
}
```


**5.** CREATE JOBS API
```terminal
Post method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/jobs/create-job
{
    "company":"Your Company Name",
    "position":"Your Position Name"
}
```


**6.** GET JOBS API
```terminal
Get method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/get-job


**7.** UPDATE JOBS API
```terminal
Put method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/update-job/your_job_id
{
    "company":"Your Company Name",
    "position":"Your Position Name"
}
```


**8.** DELETE JOBS API
```terminal
delete method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/delete-job/your_job_id
```


**9.** STATS AND FILTERS JOBS API
```terminal
GET method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/job-stats
```


**10.** SEARCHING JOBS API
```terminal
Get method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/get-job?key=value


**11.** SORTING JOBS API
```terminal
Get method- (Body, raw,json) (headers-AUTHORIZATION)
http://localhost:8080/api/v1/job/get-job?sort=latest