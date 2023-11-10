# CQRS

Project Description:
Created a CQRS project using Spring-Boot and event sourcing using Axon framework.

## What is CQRS?
CQRS or command query responsibilty segregation is a design pattern:

	- it seperates read and write operations to different service.
	- The problem is we can't scale up our app independetly for read and write request. Generally we have more read request than write request.
	- Solves:
		- handles high load
		- write complex queries
		- additional security
	- So we create 2 seperate microservices, one for Read(GET) REST calls and other for Write(POST, PUT, DELETE) REST calls. Both these services will host to different server.
	- So now we need to sync both our microservice database (incase when write service DB arent updated to read microservice DB) to maintain consistency and for that we can use Kafka event driven system. 
	- The command microservice will publish the event (like create/update event) to topic and Query microservice will consume it.

 
