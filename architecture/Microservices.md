# Microservices Architecture

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
