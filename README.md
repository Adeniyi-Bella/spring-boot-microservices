# spring-boot-microservices
A real time microservices supply monitoring project utilizing spring cloud technologies framework. Services can connect/interact to each other or can also connect with external tools as shown in the 
Architectural layer below. 



## Services and their functionality
- Distributed Tracing was implemented with [spring-cloud-sleuth](https://spring.io/projects/spring-cloud-sleuth) and [Zipkin](https://zipkin.io/pages/quickstart) for the UI. This helps to add traces and spans id for every api call made to all the services. 

- Circuit breaker was implemented using Resilience 4j depency from Spring Cloud circuit breaker framework. This helps to degrade functionality when a method call fails. More information [here](https://spring.io/projects/spring-cloud-circuitbreaker).

- Service discovery was implemented with spring cloud discovery Eureka server/client. This helps to persist services on the client side acting as a caching solution. 

- API gateway was implemented with spring cloud gateway to route and filter incoming requests to micro services.

- Order service: Built on mySQL DB. Makes synchronous call to Inventory service to confirm if goods are available and asynchronous call to notification service notifying customers if order was successful.

- Product service: Built on mongoDB. An endpoint to display goods. The frontend would be built on this end point. 

- Inventory service: Built on mySQL DB. Takes count of the quantity of goods in stock. 

- Notification service: Serveless API to notify cutomers about their orders.

## Architecture Layer

![architecture](https://user-images.githubusercontent.com/37347588/227748019-5f854bc5-8454-412b-bc23-ac3c4512ba58.png)

## Logic Layer for each service
![logic layer](https://user-images.githubusercontent.com/37347588/227748037-b6576358-4221-4177-ae0f-23b4e7941270.png)
