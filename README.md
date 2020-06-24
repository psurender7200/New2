# Rosenmeister_Repository
 Rosenmeister_Repository
 
# Project Details
This project is API project which is used to build Create and GET API.
The challenge consists of creating two services:

- user_brithday
- letter_digit

# Conditions:

- Make use of docker and docker-compose
- Make use of unit tests
### user_brithday
User Birthday Service

a.	Create an API endpoint which accepts a list of JSON objects as POST-payload.

-	Store the data in a Postgres Database
-	The email address should be unique
-	All fields are required

b.	Create an API endpoint which returns a list of objects, filtered by the following
parameters (birthday)
-	from (example: from=%d%m)
-	to (example: to=%d%m)

c.	Create an API endpoint which returns the average age of all records in the database.
Think about caching.

### Letter Digit

Create an API-Endpoint taking a string with letters and digits and returning a list of all possible upper & lowercase variations.
Example: (a2B => [a2b, a2B, A2b, A2B])
The implementation has done on Django Rest API.

# Dependencies

•	Django==3.0.6
•	django-filter==2.2.0
•	djangorestframework==3.11.0
•	psycopg2==2.8.5
•	python3-memcached==1.51
Postgres-SQL is db used for this project

# Docker execution steps

1.	Start Oracle virtual box which is needed for Docker toolbox to run, Docker toolbox in windows will wait for virtual box IPaddress, so 	 please start virtual box.
2.	Now open docker command promt and go inside project folder , then you please  run the docker command  as “docker-compose up -d”.
3.	After above step run then ,you see Django server are in running state and also postgres container also in running state.

# Rest API database Migrations

Create the Database by using below command

**docker exec -it <Postgres-ContainerID> createdb -U <Username> RosenmeisterDB**

### Run below commands

•	docker exec -it yourDjangoContainerID bash

•	Python manage.py migrate 

•	Python manage.py collectstatic

•	To exit bash use command as Control + p + q  

# Docker Image details
  Docker image will be created with the name “rosenmeister”
 

# Docker Verification details

After execution of above steps, if you want to verify about container details
1.	To check container is running or not, you can hit the command as “docker ps”  which  shows running container.
2.	Then you need to get the IPAddress of virtual box to open rest api project in  browser. Command to get virtual box IP address    “docker-machine ip”
3.	Below sections, I have provided end points, Kindly take urls from that section.

# Docker Container extra details – 

If you want to delete running container and image, follow below steps
1.	Docker ps
2.	Docker stop <container Id>
3.	Docker rm <container Id>
4.	Docker Images
5.	Docker rmi  <Image ID>

# End Points Information :

Below are the end points of the complete project.

## user_brithday service endpoints

### only one endpoint is used for user_birthday service.

**Create API / Get API (To show all records)-**
 
http://<HostName>:8000/birthday/

**GET API to Fetch filtered records –**
 
http://<HostName>:8000/birthday/?date_from=1940-01-01&date_to=1950-01-01

**Get API to get Average Age -**

http://<HostName>:8000/birthday/avgage/Info/

## letter_digit service endpoint

**letter_digit service is considered as different resource and created separate endpoint as below**

Create-API - http://<HostName>:8000/letterdigit/


More details are present in documentation on the execution and dev configuration, production configuration, and execution details.
