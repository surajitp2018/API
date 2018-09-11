# API
This Contact API will take the data model that was provided and will commit it to a database. It supports the CRUD operations with full and incremental updates. By using Spring Boot, I took the liberty to define & design the database components that will support the API and data model. Identification object/table has been considered as parent with one-many child relationship with Address and Communication objects/tables. This is aligning with the data model provided in the problem statement. 

Instructions for running the application in Windows OS 

1. Please install the below mentioned softwares, if not already installed in the Windows machine.
Java runtime version 1.8.0_51
Spring Tool Suite 3.9.3
Oracle DB 12.x
Oracle SQL Developer (any latest version)
Postman 

2. Download the .zip file from the Github repository (link provided separately).
3. Unzip the file and save it at any folder of your choice.
4. Open Spring Tool Suite IDE and import the code to create the project.
5. Open the application.properties file under the resources (src/resources) folder.
6. Update the Oracle (datasource) configuration parameters and the user credentials, as per your Oracle setup.
7. Check if there is any error for any Maven dependencies that are missing. It can be for Oracle driver, if yes, please provide the correct path of Oracle jdbc driver of your local machine.
7. Start the API program by selecting Run As Spring Boot Application, once there are no errors.
8. Since the Spring Boot application is used to create the requried tables, when it is first time executed, it will create one record in the DB. Refer Application.java that implements CommandLineRunner to validate the data.
9. Now use Postman to test all the CRUD operations of the API. Here are the URLs for reference-
http://localhost:2222/contact/get/{id} - read and retrieve the contact data for specific identifier/identification 
http://localhost:2222/contact/create - create the contact data
http://localhost:2222/contact/update/{id} - update the contact data for specific identifier/identification
http://localhost:2222/contact/delete/{id} - delete the contact data for specific identifier/identification

Note: Since there is no Process or UX API layer implemented, we have little constraints in data inputs. During POST operation invoke using Postman, we need to make sure that DOB is in exact milliseconds. For ease, we can test the GET operation first to extract the data from DB, copy the data output to keep the date format, remove the "id" fields that are not part of data model and then prepare your own data to create more records in DB. 

