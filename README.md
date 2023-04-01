# spring-boot-microservices
A real time microservices supply monitoring project utilizing spring cloud technologies framework. Services can connect/interact to each other or can also connect with external tools as shown in the 
Architectural layer below. 



## Services and their functionality
- Event driven activity such as notifying customers when order has been made was implemented with kafka. The kafka broker was set up using [Docker](https://developer.confluent.io/quickstart/kafka-docker/?utm_medium=sem&utm_source=google&utm_campaign=ch.sem_br.nonbrand_tp.prs_tgt.dsa_mt.dsa_rgn.emea_lng.eng_dv.all_con.confluent-developer&utm_term=&creative=&device=c&placement=&gclid=Cj0KCQjwiZqhBhCJARIsACHHEH-xX9qtTC87qTy6cshJ2Xg9Q9Is-G7lbOuU7w50jUVTDxAwrVW4VY8aAmXLEALw_wcB) and [Spring for Apache kafka](https://spring.io/projects/spring-kafka).

- Distributed Tracing was implemented with [spring-cloud-sleuth](https://spring.io/projects/spring-cloud-sleuth) and [Zipkin](https://zipkin.io/pages/quickstart) for the UI. This helps to track the performance of our app by adding traces and spans id for every api call made to all the services. 

- Circuit breaker was implemented using Resilience 4j depency from Spring Cloud circuit breaker framework. This helps to degrade functionality when a method call fails. Since we are implementing a synchronous call to the inventory service, a circuit breaker would ensure clients are routed to a new page when a service fails or takes longer time to respond. More information [here](https://spring.io/projects/spring-cloud-circuitbreaker).

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
