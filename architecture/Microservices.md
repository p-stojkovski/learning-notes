# Microservices Architecture

## 1. FUNDAMENTALS

### Microservices
- Microserivce is an independently deployable unit that performs one job extremely well and interacts with other services over well defined interface.
- The only communication allowed between services is via service interace calls over the network (api, message, event driven).

### Finding Microservice Boundaries
- Most important thing is decomposition of the services.
- Understanding where one service starts and where ends is one of the fundamental challenges.
- Two tools to help determine where the split of the microservices is aligned:
  - DDD
  - Event storming

### Key Concepts of Microservices
1. Service Indenpendence
2. Decentralized Data
3. API Based Communication
4. Resiliance and fault tolerance
  1. Always ask yourself - What would happen if this integration failed? And build accordingly.
5. Scalability
6. Autonomous teams

### The Fallacies of Distributed Computing
- What is a distrubuted system?
  - A system where components located on different machines work together as a single entity. 
- "A distributed system is one in which the failure of a computer you didn't even know existed renders your own computer unuseable.
- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure

### Coupling
- A serivce boundary determines how your services interact, what they share. And don't share, which is the key of microservies.
- Microservice should be completly independent, orgise around busniness domains will help you do that.
- Coupling is the degree of interdependence between modules in your system.
- Your architecture should target loose coupling
- The appropriate level of coupling depends on the level of control you have over the endpoints.
- Types of coupling:
  - Runtime: you need to know where the other system is at runtime
  - Temporal: two separate modules depending of the timing or order of events, one module need to execute after another.
  - Content: when one module can directly modify the data of another module.
  - Functional: when two modules depend of eachother functionality
  - Sequential: where the output of one module fits directly into another.
- Cohesion is the degree in which inside a module belong together. Things that change together, live together.
- Each servce owns it's own data. And no services have a direct access to the data of another.
- Information hiding is the principle of hiding as much data as possible behind a microservices boundary.

### Microservice Communication - Synchronous
- One service exposes an endpoint and another service make a request to that endpoint.
- The calling serivce waits for the response.
- Benefit:
  - Immediately garantee if the operation is completed or not
  - Feels familiar, like make a method call
- Tradeoffs:
  - Runtime coupling
  - If the service is down or unavailable directly impacts the calling service.
  - Can be overloaded and latency can be increased.

### Microservice Communication - Asynchronous
- When one service makes a non blocking call to another service.
- The current service can continue it's work without waiting a response.

### Dealing with Consistency
- Two types of Consistency:
  - Eventual 
  - Strong

### Microservice Deployment
- Each individual service should be indenpendetly deployable.

### Code sharing
- Sharing code should be kept to a minimum.
- A cross cutting concern is something that will apply across all layers of an individual microservice, as well as something all services likely to need. (ex. Logging, Libary for Event Publishing, SDK for Api endpoints)
- Avoid leaking business logic into your client libary

### Service Discovery
- Service Mesh, API Gateway
- An API Gateway maps external requests onto internal services. Ca have rate limiting, api keys, fancy developer portals.
- API Gateway focuses on external communication and managing traffic between clients and services.
- Service meshes shift the responsibility for inter-service communication out of the individual service and into a mesh. (Load balancing, correlation ids...)
- Service Mesh focuses on internal communication and managing traffic between services.

**Real-World Examples: API Gateway vs. Service Mesh**

**API Gateway:**

Imagine a large e-commerce website. Customers (clients) can browse products, add them to carts, and checkout. This involves interacting with various backend services:

- Product Catalog Service: Provides product information (images, descriptions, prices).
- Shopping Cart Service: Tracks items added to the cart and manages quantities.
- Payment Processing Service: Handles secure payment transactions.
- Order Management System: Processes orders and tracks fulfillment.

The API Gateway acts as the single entry point for customers. It receives requests from users, like adding an item to the cart. Then:

- Authenticates the user to ensure they are allowed to access the website.
- Routes the request to the appropriate backend service (Product Catalog or Shopping Cart).
- Aggregates data from multiple services (e.g., product details and cart contents) to return a complete response to the user.
- Enforces security policies like rate limiting to prevent abuse.
- Logs and monitors API activity.

**Service Mesh:**

Behind the scenes, the backend services (Product Catalog, Shopping Cart, etc.) communicate with each other to fulfill user requests. A Service Mesh manages this internal communication traffic. Here's how it helps:

- Service discovery: Helps services find each other dynamically, even if they move to different servers.
- Load balancing: Distributes requests across multiple instances of a service for optimal performance.
- Resilience: Ensures requests are delivered even if one service experiences an issue.
- Security: Enforces encryption and authentication for secure communication between services.
- Monitoring: Helps track service health and identify potential problems.

In this example:
- The Shopping Cart service might call the Product Catalog service to get details about a specific item.
- The Order Management System might call the Payment Processing service to verify payment before completing an order.
- The service mesh handles all these internal service-to-service interactions, making it easier for developers to build and manage the e-commerce system.

### Optimize for rate of change
- When you are architecting your system constantly ask yourself, how do I optimize my rate of change?
- How do I ensure different components of my system ca be shiped indenpentently with little chance of taking eachother down.

## 2. INTEGRATION

### Shared Data
- File based integrtions
- Share with data with files between services.
- What is the format of the file and the schema?
- Where the files will be stored, what it the folder structure, what is the naming convention, what happens to files after being processed, how do you deal with errors (if single record or entire file fails)
- Eventual consistency is a challenge
- File transfer is a very good tool in your toolbox if you integrating you new system into a old legacy system.

### Request/Response
- Sync communication between components
- RPC, REST, GraphQL
