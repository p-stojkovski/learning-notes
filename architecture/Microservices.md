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
  - Always ask yourself - What would happen if this integration failed? And build accordingly.
5. Scalability
