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
