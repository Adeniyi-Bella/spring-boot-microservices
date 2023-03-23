# Spring-boot-microservices

# Solution Architecture

![architecture](https://user-images.githubusercontent.com/37347588/227370022-018302e3-e59d-46b6-b13e-e559e554dd41.png)

# Logic Layer

![logic layer](https://user-images.githubusercontent.com/37347588/227370611-023b4e2f-ab00-469c-a9ea-d5c01e8bd8c1.png)

## Micro Services
- Product services: Provides API to create and view products. Acts as product catalog.
- Order services: Provides API for products ordering.
- Inventory service: Provides API to check if product is in stock. Order service can communicate with inventory service. 
- Notification service: Can send email-notification after order is placed

## The services were built with springboot initilizr framework [here](start.spring.io). 
