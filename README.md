# spring-boot-microservices
A real time microservices supply monitoring project using spring boot and spring cloud technologies to create 
rest API. Services can connect/interact to each other or can also connect with external tools as shown in the 
Architectural layer below. 

## Services and their functionality
- Order service: Built with mySQL DB. Makes synchronous call to Inventory service to confirm if goods are available and asynchronous call to notification service notifying customers if order was successful.

- Product service: Built with mongoDB. An endpoint to display goods. The frontend would be built on this end point. 

- Inventory service: Built with mySQL DB. Takes count of the quantity of goods in stock. 

- Notification service: Serveless API to notify cutomers about their orders.

## Architecture Layer

![architecture](https://user-images.githubusercontent.com/37347588/227748019-5f854bc5-8454-412b-bc23-ac3c4512ba58.png)

## Logic Layer for each service
![logic layer](https://user-images.githubusercontent.com/37347588/227748037-b6576358-4221-4177-ae0f-23b4e7941270.png)
