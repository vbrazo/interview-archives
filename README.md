# Interview Archives

This is my personal interviews archives and it's where I store my research that aims to provide resources to better work with teams of developers in my engineering management journey.

- [Interview Archives](#interview-archives)
  - [Microservices x Monolithic application](#microservices-x-monolithic-application)
    - [Microservices](#microservices)
      - [Benefits](#benefits)
      - [Drawbacks](#drawbacks)
    - [Monolithic](#monolithic)
      - [Benefits](#benefits)
      - [Drawbacks](#drawbacks)

## Microservices x Monolithic application

### Microservices

#### Benefits

- It tackles the problem of complexity by decomposing application into a set of manageable services which are much faster to develop, and much easier to understand and maintain.
- It enables each service to be developed independently by a team that is focused on that service.
- It reduces the barrier of adopting new technologies since the developers are free to choose whatever technologies make sense for their service and not bounded to the choices made at the start of the project.
- Microservice architecture enables each microservice to be deployed independently. As a result, it makes continuous deployment possible for complex applications.
- Microservice architecture enables each service to be scaled independently.

#### Drawbacks

- Microservices architecture adding complexity to the project just by the fact that a microservices application is a distributed system. You need to choose and implement an inter-process communication mechanism based on either messaging or RPC and write code to handle partial failure and take into account other fallacies of distributed computing.
- Microservices have a partitioned database architecture. Business transactions that update multiple business entities in a microservices-based application need to update multiple databases owned by different services. Using distributed transactions is usually not an option and you end up having to use an eventual consistency-based approach, which is more challenging for developers.
- Testing a microservices-based application is also much more complex than in the case of the monolithic web application. For a similar test for a service, you would need to launch that service and any services that it depends upon (or at least configure stubs for those services).
- It is more difficult to implement changes that span multiple services. In a monolithic application, you could simply change the corresponding modules, integrate the changes, and deploy them in one go. In a Microservice architecture, you need to carefully plan and coordinate the rollout of changes
to each of the services.
- Deploying a microservices-based application is also more complex. A monolithic application is simply deployed on a set of identical servers behind a load balancer. In contrast, a microservices-based application typically consists of a large number of services. Each service will have multiple runtime instances. And each instance needs to be configured, deployed, scaled, and monitored. In addition, you will also need to implement a service discovery mechanism. Manual approaches to operations cannot scale to this level of complexity and successful deployment of a microservices-based application requires a high level of automation.

### Monolithic

#### Benefits

- Simple to develop.
- Simple to test. For example you can implement end-to-end testing by simply launching the application and testing the UI with Selenium or do unit/integration testing with RSpec.
- Simple to deploy. You just have to copy the packaged application to a server.
- Simple to scale horizontally by running multiple copies behind a load balancer.

#### Drawbacks

- This simple approach has a limitation in size and complexity.
- Application is too large and complex to fully understand and made changes fast and correctly.
- The size of the application can slow down the start-up time.
- You must redeploy the entire application on each update.
- Impact of a change is usually not very well understood which leads to do extensive manual testing.
- Continuous deployment is difficult.
- Monolithic applications can also be difficult to scale when different modules have conflicting resource requirements.
- Another problem with monolithic applications is reliability. Bug in any module (e.g. memory leak) can potentially bring down the entire process. Moreover, since all instances of the application are identical, that bug will impact the availability of the entire application.
- Monolithic applications have a barrier to adopting new technologies. Since changes in frameworks or languages will affect an entire application it is extremely expensive in both time and cost.
