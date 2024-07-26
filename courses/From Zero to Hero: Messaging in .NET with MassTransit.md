
# Messaging in .NET

### Communication between services
- SYNC
  - HTTP -> client sends request and waits a response from the service. It is sync by nature and task will continiue when receives response. Noting to do with async/await in C#.
  - gRPC
- ASYNC
  - Using queues -> client sends a message and usually don't waits for response.

Number of receivers:
- One
  - Single receivers -> Each request must be processed by one receiver or service. Ex. command pattern.
- Many
  - Multiple receivers -> Each request can be processed by zero to multiple receivers. Ex. publish-subscribe pattern (service bus using topics and subscriptions)

Communication styles:
- Request/response over HTTP
- RPC between services
- Messaging (often the best choice)

### What is the Problem with HTTP APIs?
- Coupling -> introduces dependencies between services, makes system less flexible and easy to change and less scalable.
- Performance bottlenecks -> if service is overloaded or slow, it can hold up the entire request.
- Limited communication patterns -> http apis with sync call primary handle request/response interactions, this can limit availability to implement complex workflow or event driven architectures when services need to react to events async.
- Reduced scalability -> scaling services designed for sync calls can be challenging. Adding more instances to service might not improve overall performance or throughput if waits responses from other services.
- Cascading failures
- Long running operations

### RPC vs Messaging
- Local function call
  - Predictable (returns or throws and exception)
  - Fast
  - Pass by reference in memory
- Network function call
  - Unpredictable (can be lost due to network problem, remote machine is unavailable)
  - Slow
  - Encoded to bytes and sent over the wire

How is RPC compared with messaging?
- Load
  - systems build with messaging will usually exceed the troughput of and RPC based system
  - more stable overall troughput
  - no waiting of respose of other services
  - RPC based systems rely on threads and responses
![image](https://github.com/user-attachments/assets/11acc564-3e37-4294-ad1c-516d64f3896b)

### Why asynchronous messaging?
- Replaces traditional HTTP Request/Response patterns
- Uses messages instead of requests and responses
- Messages can be sent and received without both parties to be up at the same time
- Allows components to operate independantly in async way which can improve:
  - performance
  - scalability
  - reliability
- Allows grater flexibility and can handle larger volumes of messages more efficiently
- These systems are better in regards to Fault Tolerance
- Mesages can be queued and processed later

Advantages of Async messaging
- Scalability -> allows for systems to scale horizontaly easier.
- Service decoupling/Loosely coupled components -> allows services to communicate between eachother without having to know eachother existence.
- Fault tolerance
- Resilience
  - Messaging improves the Fault tolerance and Resilience of a system because it allows the messages to be stored and retried if the consumer is not available.
- Integration enabled -> can have part of the systems with different tech stacks that can exchange information
- Load leveling -> the senders don't need to worry about the troughput of the receivers, continiue to send messages regardless of how and fast they are being consumed. 
- Temporal decoupling -> the systems don't need to be up at the same time.

- Build more resilient and scaleable systems that are highly available, elastic and can handle variaty of workloads by allowing components to operate independently and async we can reduce delays and improve overall system efficiency.

### Things to consider when using asynchronous messaging
- Complexity
- Message ordering
- Message deduplication
- Delivery guarantees
- Vendor lock-in

### Fallacies of distributed computing
Set of incorrect asumptions that developers often make when designing and implemeting distributed systems.

- The network is reliable 
  - We often assume that the network is reliable and our requests that we sent to other components will be timely and successfully delivered.
  - Networks can expirience faliuresm delays, conjections, leading to message loss.
- Latency is zero
  -  We often assume that the network latency is neglectable and messages are delivered instantly between components
  -  Can wary due to factor of geo distance, network conjection, quality of network...
- Bandwitdh is infinite
  - We often assume that the network bandwitdh is unlimited and that we transmit large volumes of data between components, without any performance degradation.
  - Bandwitdh is actualy finite, and maybe become saturated leading to decrease performance and throughput.
- The network is secure
  - We often assume that the network is secure and the message we sent between components are protected for unauthorized accesss...
  - Networks can have security threats such as inteceptions, spoofing...
  - Networks are targets for malicious actors who can exploit weakneses to gain unatuhorized access to data. (hacking, malware injections, man in middle...)
  - Data breach
  - Unencrypted communication
  - How to secure? Implement firewalls, data encription, access control, regular security updates
- Topology doesn't change
  - We often assume that the topology of our distribted system will remain static and predictable, meaning that the components are a;ways reachable and available.
  - Chnages in network connectivity, system configurations, component aviability..
  - Distributed system is live organism.
- There is one administrator
  - Distributed systems often invole multiple administrators with different level of control and authority.
- Transport cost is zero
  - Data transfer costs
  - Bandwith, useage fee and network can impact overall cost
- The network is homogeneous

### Types of coupling
Coupling refers to the degree of interdependents between different modules and components, basicly indicates how much one component relies on another one in terms of Communication, Data Exchange and Coordination.

The more the components interact with eachother, the more tightly coupled the system is and harder will be to mantain.

Types of coupling:
- Logical
  - How much one component relies on internals workings on another.
  - Change in one component will triger changes in another components.
  - Can have 2 types:
    - Efferent -> Measure how many **outgoing** dependencies a component has. (ex. Child dependend on the needs of the parent, teacher)

      ![image](https://github.com/user-attachments/assets/20009e95-93b2-4315-a3ea-63953ef1e71e)
    - Afferent -> Discribe the number of **incoming** dependencies (ex. Kids depend on parent to cook, take care of them. Parent are afferently coupled to the children)

      ![image](https://github.com/user-attachments/assets/9f284fb3-17f0-431f-bc05-9d0a8f8fab49)

      ![image](https://github.com/user-attachments/assets/c4aa21ac-f359-4a49-83dc-8687a2c42909)
- Temporal
  - Refers to situation where components are **Syncronized or coordinated** based on timing constraints.
  - These components are coupled because they happen in same time.
- Data
  - Occurs when components share data through well defined interfaces. These components share no bussiness logic and minimise the aknowleage that is revealed across the boundaries to only miniumum set of data that is only needed.

When aiming to loose coupling we can build more robus and flexible distributed systems.

### Channels
![image](https://github.com/user-attachments/assets/20ecf658-705b-4c05-aea7-5d7ec25b531f)
![image](https://github.com/user-attachments/assets/77912221-73f5-4820-8e17-b8586dbb0817)
![image](https://github.com/user-attachments/assets/ee6e70f6-3104-4f6e-9ea9-5f61636c2c6a)

### Pipes & Filters
Pipes & Filters is an architectural concept that discribes how multpile steps can changed together using channels to change the message.

![image](https://github.com/user-attachments/assets/08d82834-bc97-4a86-a77c-0c845bf7bde3)

### Types of messages
- Document
- Command
- Events
- Queries
- Request/Reply

Messages are communication units exchanged between different components within a distributed system.

### Events
An Event is a type of message that describes and notifies other components of systems or within the same system about something that happened.

Event can be:
- Descrete
- Actionable
- Independent

### Commands
Command is a type of message to send an instruction from one component or system to another.  

The command message is construct for the needs of consumer without requring a reply, usually.

Specfficly modeled to trigger an action or operation on the receiving end.

### Commands vs Events
![image](https://github.com/user-attachments/assets/4448d6b8-5dfa-47f6-bbea-c66ae441fe18)

### Producers
Producer is a component or entity responsible for generating and sending messages to a system.
![image](https://github.com/user-attachments/assets/6e2db1f9-7882-4b50-a3e3-4cc5b1e55ebd)

### Consumers/Receivers
- Consumer is a component or entity responsible for receiving and processing messages from a messaging system.
- Consumer life purpuse is to consume the messages and do the required work.
- Can be scaled horizontaly to handle message load
- Multiple instances can run in parallel, improving throughput and performance.

They can implement mechanisms like:
- Message acknowledgement
  - Automatic -> Ack as soon as they are delivered, before processing (lowest latency in message delivery)
  - Manual -> Ack after processed. (will increase latency)
- Retry policy
- Error handling
  - If a meesage can't be processed for some reasons for number of times the message will be delivered to a dead-letter channel.

### Pull & Push consumption models
How does the consumer know there is a message to process?
- Pull model -> The consumer decides the consumprion rate which can prevent the system be overwhelmed by too many requests, the extra messags will stay in the queue.
  ![image](https://github.com/user-attachments/assets/f6755ecd-1ea6-41d2-80fc-b45d6a1ef880)
  ![image](https://github.com/user-attachments/assets/2ac2026a-b336-4049-90ba-f1b3916b4636)
  ![image](https://github.com/user-attachments/assets/3ea73957-2349-4576-8cae-c28ab3c02d4d)
- Push model -> The consumer is notified that a new message is available and it is more efficeint because is secures and saves the system of being overloaded with messages.
  ![image](https://github.com/user-attachments/assets/150bc713-57bc-48d4-ab1a-515d919d76cf)

### Queues
- One of the most important structures in computer science.
- Allows 3 operation:
  - Enqueue
  - Dequeue
  - Peek

![image](https://github.com/user-attachments/assets/e3969f52-5651-40b4-940b-ef7ddf6a2335)

What is message queue?
- Intermediary construct that works with messages.
  - Retrives
  - Stores
  - Makes them available for consumption
- Manages the message lifecycle and guarantiees that each message is processed by at least one consumer. 

![image](https://github.com/user-attachments/assets/4fe5a3a3-5bfd-47ca-95b6-256dc88a8bfc)

### Topics & Subscriptions
- Topics are specialized queues that route and deliver messages based on a routing key to multiple subscribers.
- Topic is specialized message queue that delivery of message is to one or more subscribers.
  - Supports one to many, 0 to many
  - Has an embedded message filter
  - Routes messages based on a key
  - Used in pub/sub architecture
![image](https://github.com/user-attachments/assets/2786114f-d1f9-4b8f-a4fd-caad1d3ce43f)

### Message brokers/Buses
- Message broker is one of the most important part of a distributed system.
- Provides a centralized set of queues and abstractions that hold messages until they are consumed.
- Enable loosely coupled architectures
- A message broker is an intermediary or a middleware component that facilietes comunication between components.
- Act as a central hub for sending and receiving messages
- Provides capabilites like: routing, queing, message persistence
- Give up Fault Tolerance Temporal decoupling, Load leveling, and monitoring capabilities
![image](https://github.com/user-attachments/assets/bcbb97a9-cf23-4927-9920-64c87cfac614)

There are 3 categories:
- Queue- based -> most common
- Cache -based
- Stream -based

Producers write messages to brokers, the brokers route the messages and dispatch them to the right consumers or store them until they are consumed.

### Load leveling
- The process of distributing incoming messages evenly across the components in the system
- To ensure that no single component is overwhelmed
- In case of spiky loads the queues will buffer messages until they are consumed
- The comsumers decide the rate at which they process messages
- Prevents performance bottlenecks, resource exhaustion and serice degradation
- Distributes the load across the components

### Delivery modes/guarantees
- At most once
- At least once
- Excatly once

### Transports
- TCP/IP
- HTTP
- AMQP
- MQTT
- STOMP
- Web Sockets
