# Interview Archives

This is my personal interviews archives and it's where I store my research that aims to provide resources to better work with teams of developers in my engineering management journey.

- [Interview Archives](#interview-archives)
  - [Ruby on Rails](#ruby-on-rails)
  - [iOS](#ios)
  - [Android](#android)
  - [System Design](#system-design)
    - [General Questions](#general-questions) 
    - [Microservices x Monolithic application](#microservices-x-monolithic-application)
      - [Microservices](#microservices)
        - [Benefits](#benefits)
        - [Drawbacks](#drawbacks)
      - [Monolithic](#monolithic)
        - [Benefits](#benefits)
        - [Drawbacks](#drawbacks)

## Ruby on Rails

- What's a scope?
- Have you ever built a Rails app with a service-oriented architecture?
- If you were starting up a new Rails app, what gems would you add?
- Have you ever worked with Rails Engines?
- What was the biggest challenge you have faced with Rails APIs?
- If we talk about Ruby frameworks, do you have experience with any other framework outside the Rails universe?
- Do you prefer `Minitest` or `RSpec`? Why?
- What kind of tests do you judge important and essential for a backend app?
- What's a shared context in `RSpec`?
- What's `TDD`?

## iOS

- What’s the difference between var and let? Which one would you choose for properties in a struct and why?
- What are lazy properties?
- What are closures?
- What’s the application and controller lifecycle?
- Which are the ways of achieving concurrency in iOS?
- Explain the different types of iOS Application States.
- Describe managed object context and the functionality that it provides.
- Have you ever written a networking layer? Describe briefly how did/would you do that?
- How do you parse JSON in Swift? How do you parse XML in Swift?
- What’s a dispatch group? 
- How do you find and resolve memory leaks?
- Do you have experience with unit testing? How about UI testing?
- Have you ever developed a test-driven project (TDD)?
- What is declarative programming? Have you tried SwiftUI yet?
- Do you prefer imperative or declarative programming in iOS?
- Explain the MVC architecture in iOS
- Explain the MVP architecture in iOS
- Explain the MVVM architecture in iOS
- Explain the Viper architecture in iOS

## Android

- Which are the ways of achieving concurrency in Android?
- What is the difference between a fragment and an activity?
- What are the core components under the Android application architecture?
- What is the life cycle of android activity?
- What is the difference between File, Class, and Activity in android?
- What are broadcast receivers? How is it implemented?
- What is a Service? How is it implemented?
- What is the difference between Service and Thread?
- How does Manifest file plays an integral role in App development?
- What are some of the disadvantages of Android?
- What is an Android Runtime?
- What is the difference between a regular bitmap and a nine-patch image?
- What is a sticky broadcast? Give an example.
- Explain the MVC architecture in Android
- Explain the MVP architecture in Android
- Explain the MVVM architecture in Android

## System Design

### General Questions

- What's availability of a system?
- What's the latency between systems?
- What's throughput of a system? How do you measure throughput?
- When do we need load balancing? Explain what load balancing is and use cases.
- When do we need Database Replication?
- When do we need Sharding?
- What's Rate Limiting and when do we need to implement it?
- Explain with your own words what Publish/Subscribe Pattern is.
- What's a reverse proxy and when to use?
- What happens when you type https://www.paywith.com in your browser?
- What's TCP/IP and HTTP? What are their responsibilities?
- Do you have experience with Relational databases? Which ones?
- Do you have experience with Non-Relational databases? Which ones?
- What other types of Storage do you know?
- What's the difference between Pooling and Streaming?
- What are Peer-To-Peer Networks?
- What's Leader Election?
- What's MapReduce?

### Microservices x Monolithic application

#### Microservices

<img src=https://github.com/vbrazo/interview-archives/blob/main/docs/scenario%201%20-%20microservices_app.png width=1000 />

##### Benefits

- It tackles the problem of complexity by decomposing application into a set of manageable services which are much faster to develop, and much easier to understand and maintain.
- It enables each service to be developed independently by a team that is focused on that service.
- It reduces the barrier of adopting new technologies since the developers are free to choose whatever technologies make sense for their service and not bounded to the choices made at the start of the project.
- Microservice architecture enables each microservice to be deployed independently. As a result, it makes continuous deployment possible for complex applications.
- Microservice architecture enables each service to be scaled independently.

##### Drawbacks

- Microservices architecture adding complexity to the project just by the fact that a microservices application is a distributed system. You need to choose and implement an inter-process communication mechanism based on either messaging or RPC and write code to handle partial failure and take into account other fallacies of distributed computing.
- Microservices have a partitioned database architecture. Business transactions that update multiple business entities in a microservices-based application need to update multiple databases owned by different services. Using distributed transactions is usually not an option and you end up having to use an eventual consistency-based approach, which is more challenging for developers.
- Testing a microservices-based application is also much more complex than in the case of the monolithic web application. For a similar test for a service, you would need to launch that service and any services that it depends upon (or at least configure stubs for those services).
- It is more difficult to implement changes that span multiple services. In a monolithic application, you could simply change the corresponding modules, integrate the changes, and deploy them in one go. In a Microservice architecture, you need to carefully plan and coordinate the rollout of changes
to each of the services.
- Deploying a microservices-based application is also more complex. A monolithic application is simply deployed on a set of identical servers behind a load balancer. In contrast, a microservices-based application typically consists of a large number of services. Each service will have multiple runtime instances. And each instance needs to be configured, deployed, scaled, and monitored. In addition, you will also need to implement a service discovery mechanism. Manual approaches to operations cannot scale to this level of complexity and successful deployment of a microservices-based application requires a high level of automation.

#### Monolithic

<img src=https://github.com/vbrazo/interview-archives/blob/main/docs/scenario%202%20-%20monolithic_app.png width=1000 />

##### Benefits

- Simple to develop.
- Simple to test. For example you can implement end-to-end testing by simply launching the application and testing the UI with Selenium or do unit/integration testing with RSpec.
- Simple to deploy. You just have to copy the packaged application to a server.
- Simple to scale horizontally by running multiple copies behind a load balancer.

##### Drawbacks

- This simple approach has a limitation in size and complexity.
- Application is too large and complex to fully understand and made changes fast and correctly.
- The size of the application can slow down the start-up time.
- You must redeploy the entire application on each update.
- Impact of a change is usually not very well understood which leads to do extensive manual testing.
- Continuous deployment is difficult.
- Monolithic applications can also be difficult to scale when different modules have conflicting resource requirements.
- Another problem with monolithic applications is reliability. Bug in any module (e.g. memory leak) can potentially bring down the entire process. Moreover, since all instances of the application are identical, that bug will impact the availability of the entire application.
- Monolithic applications have a barrier to adopting new technologies. Since changes in frameworks or languages will affect an entire application it is extremely expensive in both time and cost.
