# Software Architecture & Design of Modern Large Scale Systems

## 1. Introduction

### Software Architecture
- Everything we build has a structure.
- The more we invest in builing a product, the harder it is to change it's structure.
- The structure of our system describes:
  - The intent of our product
  - The qualities of the product

#### Applications to software
- Infinite ways to orginize our code
- Different organizations will give us different properties
- The software architecture impacts:
  - Performance and scale of the product
  - Ease of adding new features
  - Response to failure or security attack
- Cost of redesign will be significant in terms of time and money.

#### Definition of Software Architecure
- The software architecure of a system is a high-level description of the systems's structure, its different components, 
and how those components communicate with each other to fulfill the systems requirements and constrains.

- The software architecure of a system is a high-level description of the systems's structure:
  - An abstraction that shows us the important components while hiding the implementation details.
  - Technogolies or programming languages are not part of the software architecture but a part of the implementation
  - Decisions about implementation should be delayed to the very end of the design

- Its different components, and how those components communicate with each:
  - The components here are "black box" elements defined by their behavior and APIs
  - The components may themselves be complex systems with their own software architecture diagrams

- To fulfill the systems requirements and constrains:
  - Components come together to do what the **system must do**, which are our requirements
  - The system **does not do what it shouldn't do**, which are the constrains

#### Levels of Abstraction
- Software architecture can have many different leveles of abstraction:
  - Classes/structs
  - Modules/packages/libires and how they interact between eachother
  - **Services (processes/groups of processes)**

#### Advantages
- The more distributed, multiple service approach allows us to architect systems that can:
  - Handle large amounts of requests
  - Process and store very large amounts of data
  - Serve many users every day

#### Large Scale Systems - Exmaples
- Ride-sharing
- Video-on-demand
- Social media
- Online video games
- Investment Services
- Banks
- Etc...

#### Importance of Design and Architecture - Benefits
- If we get the architecture right we can:
  - Go from a small startup to a multi-bilion dollar company
  - Make a positive impact on milions people

#### Importance of Design and Architecture - Risks
- Not doing a good job at the design phase can:
  - Waste months of engineering time
  - Build a system that doesn't meet our requirements
- Restructuring a system that was not architected correctly is very hard and expensive

#### Software Development Cycle
- Software architecture is the **output** of the **design** phase and the **input** to the **implementation**.

![image](https://github.com/user-attachments/assets/12c24154-3ef9-4800-8fa1-1b54fd17705f)

#### Challenges of Software Architecture
- We **cannot** prove Software Architecture to either:
  - Correct
  - Optimal
- What we **can** do to quarantee sucess is follow:
  - Methodical Design Process
  - Architectural Patterns
  - Best Practices  

## 2. System Requirements & Architectural Drivers

### Introduction to System Design & Architectural Drivers
#### Requirements - Motivation:
- Format description of what we need to build
- Large scale system requirements are different than the usual requirements we typically get for implementing:
  - A method
  - An algotithm
  - Class

**High Level of Ambiguity**
- System Design has high level of ambiguity
- Two reasons: 
  - The persion providing the requirements is often not an engineer and may even br not very techical
  - Getting the requirements is part of the solution: The client doesn't always know what they need, only what prblem they need solved.
 
**Importance of Gathering Requirements**
- What happens if we don't get the requirements right?
  - We can simply build something and then fix it.
  - Seemingly there is no cost of materials in software so changes should be cheap?
  - Large scale systems are big projects that cannot be easily changed.
  - Many engineers are involved.
  - Many months of engineering work
  - Hardware and Software costs
  - Contracts include financial obligations
  - Reputation and brand

#### Requirements - Classification:
**Types of Requirements (Architectural drivers):**
- Feature of the System
  - Functional Requirements
- Quality Attributes
  - Non-Functional Requirements
- System Constrains
  - Limitations and boundaries of the system 

**Features / Functional Requirements**
- Describe the system behavior - what "the system must do"
- Easyly tied to the objective of our system
- Functional requirements do not determine its architecture
- Generally, any architecture can acheve any feature

**Quality Attributes / Non-Functional Requirements**
- System properties that "the system must have"
- Examples:
  - Scalability
  - Availability
  - Reliability
  - Security
  - Performance
  - ..... 
- The **quality attributes** dictate the software architecture of our system.

**System Constrains**
- Time constrains - Strict deadlines
- Financial Constrains - Limited budget
- Staffing Constrains - Small number of available engineers

#### Feature Requirements - Step by step process:
**Formal Method of gathering functional requirements**

Native way:
- Ask the client to describe everything they need
  - For complex systems it is not good approach

More powerful method of gathering requirements:
- Use cases
  - Situation/Scenario in which our system is used   
- User Flows
  - A step-by-step/graphical representation of each use case

Requirement gathering steps:
- Identify all the actors/users in our system
- Capture and describe all the possible use-cases/scenarios
- User Flow - Expand each use case through flow of events
  - Each event contains: Action and Data 

**Example with a swauence diagram**
- Sequence Diagram - Diagram that represents interactions between actors and objects
![image](https://github.com/user-attachments/assets/130fe413-0e42-4c0d-9d2d-78ba1a3b008c)
![image](https://github.com/user-attachments/assets/09f7af65-3dbc-412a-865d-b03f7ec6e343)
![image](https://github.com/user-attachments/assets/76ec1be3-cfc1-49b0-9fe5-7b8454ba1f35)
![image](https://github.com/user-attachments/assets/37f28c95-ead0-40d2-9af9-eec07846bd4f)

#### System Quality Attributes Requirements
**Quality Attributes - Motivation:**
- Systems are frequently redesigned and restructured NOT because of functional requirements
- But because the system as it stands:
  - Isn't fast enough
  - Doesn't scale
  - Slow to develop
  - Hard to maintain
  - Not secure enough

**Quality Attributes - Definition:**
- Quality attiutes are non functional requirements
- They descibe:
  - The qualities of the functional requirements
  - The overall properties of the system
- Provide a quality measure on how well our system performs on a particular dimension
- They have direct correlation with the architecture of our system
![image](https://github.com/user-attachments/assets/1ded7e73-096c-4235-98e0-0ea471130034)
![image](https://github.com/user-attachments/assets/8172536f-8173-48da-960f-6d74808fde4c)
![image](https://github.com/user-attachments/assets/6ca03df1-8c0c-4214-a7be-0eddcbc35091)

**Quality Attributes Considirations**

**1. Important considirations - Testability and Measurability**
- Quality attributes need to be:
  - Measurable
  - Testable
- If we can prove that our system stisfied the required quality attribute we don't know if our system performs well or poorly.

**2. Important considirations - Tradeoffs**
- No single software architecutre can provide all the quality attributes
- Certian quality attributes contradict one another
- Some combinations of quality attributes are very hard/impossible to achieve
- We (Software Architects) need to make the right **tradeoff**
![image](https://github.com/user-attachments/assets/8b62ec1a-c676-48ff-a4a3-5fbcdd2cd768)

**3. Important considirations - Feasibility**
- We need to make sure that the system is capable of delivering with the client asking for
- The client may ask for something that is either:
  - Technicallly impossible
  - Prohibitively expensive to implement
![image](https://github.com/user-attachments/assets/a1c0e87b-722c-42a0-8dac-76976bcbeb69)

### System Constraints in Software Architecture

#### System Constrains - Introduction
- Once we define what our system must do, we have freedom on how to structure our system
- While defining the final architecture, we have to make a lot of decisions
- For quality attributes, we are expected to make trade-offs

**System Constrains - Definition**
- "A system constraint is essentially a decision that was already either fully or partially made for us, restricting our degrees of freedom"
- But this is not always a bad thing
- Instead of looking at a constraint as a choice that was taken away, we look at it as a decision that was already made.
- System constraints are referred as pillars for software architecture because:
  - They provide us with a solid starting point
  - The rest of the system need to designed around them

**Types of Constraints**
- There are three types of constraints:
  - **Techical constraints**
  - Business constraints
  - Regulatory/legal constraints

**Techical constraints**
- Examples of techical constraints include:
  - Being locked to a particular hardware/cloud vendor
  - Having to use particular programming language
  - Having to use a particular database or techology
  - Having to support certian platforms, browsers or OS 
- Technical constraints may seem like they belong to implementation and not to software architecture
- In practice, they affect the decisions we make in the design phase and put restrictions on our architecture.

**Business constraints**
- As engineers, we make the right decisions and architectural choices from a technical perspective
- This forces us to make sacrifices in:
  - Architecture
  - Implementation
- Example:
  - Limited budget or a strict deadline will make us have very different choices than if we had an unlimited budget and unlimited time
  - Different software architecureal patterns are based on suitability between small startups or bigger organizations
  - Usage of third-party services with their own APIs and architectural paradigms as part of our architecture.

**Regulatory/legal constraints**
- Regulatory constraints may be:
  - Global
  - Specific to a region

We shouldn't take any given constraint lightly.
- There should be distinction between:
  - Real constraints
  - Self-imposed constraints
- Example:
  - External rules and regulations may not have room to negotiate
  - Internal constraints can be negotiated

Use loosely coupled architecture
- Example:
  -  If limited to a database /third-party service, we need to make sure our system is not tightly couplled to that technology or APIs
  -  Different parts of the system can be decoupled to be easily replaced or updated independently

## 3. Most important quality attributes in large scale systems

### Performance

#### Response time
- Time between a client sending a request and receiving a response
- Response Time = Processing Time + Waiting Time
  - Processing time: Time spent in our system actively process in the request and builing/sending response
  - Waiting Time (Latency): Duration of time request/response spends inactivelt in our system
  - Latency = Delay
- Response time is an important metric when the request is in the critical path of a user interaction

#### Throughput
- Amount of work performend by our system per unit of time
  - Measured in tasks/seconds
- Amount of data processed by our system per unit of time
  - Measured in bits/second, Bytes/second, MBytes/second

#### Important Considirations
- Measuring response time correctly
- Response time distribution
  - Percentile distribution
  - Tail latency
  - Performance degradation
    - Steer degradation
    - High resource utilization

### Scalability

#### Motivation & Definition

##### Trafic Petterns
- The load/traffic on our system never stays the same
- It can follow different patterns

##### Definiton
- The masure of a system's ability to handle a growing amount of work, in an easy and cost effective way, by adding resources to the system.
![image](https://github.com/user-attachments/assets/6485a055-3d9b-426e-aac7-10b46bf9f7ac)


##### Types of scalability
- Scale up/Vertical Scalability
- Scale out/Horizontal Scalability
- Team/Organization Scalability
![image](https://github.com/user-attachments/assets/41c495e7-9061-47e5-9e5b-9da1602a734f)

#### Vertical Scalability
- Adding resources or upgrading the existing resources on a single computer, to allow our system to handle higher traffic or load.
- Pros:
  -  Any application can benefit from it
  -  No code changes are required
  -  The migration between different machines is very easy
- Cons:
  - The scope of upgrade is limited
  - We are locked toa centrilized system which cannot provide:
    - High Availability
    - Fault Tolerance  

#### Horizontal Scalability
- Adding more resources in a form of new instances running on a different machines, to allow our system to handle higher traffic or load.
- Pros:
  - No limit on scalability
  - It's easy to add/remove machines
  - If designed correctly we get:
    - High Availability
    - Fault Tolerance 
- Cons:
  - Iniital code changes may be required
  - Increased complexity, coordination overhead

#### Team/Organization Scalability 
- Increasing productivity while hiring more negineers into the team
- Software architecture impact engineering velocity (team productivity)

### Availablity

#### Introduction
- Availability is an important attribute when designing a system
- It has the gratest impact on:
  - Our users
  - Our business
- Two risrs that our business faces of our system goes down:
  - Loss of revenue
  - Loss of customers to our compoetitors 

#### Definition
- The fraction of time/probability that our service is operationally functional and accessible to the user.

#### Formula of Availability
- Uptime = Time that our system is operationally functional and accessible to the user
- Downtime = Time that our system is unavailable to the user
- Availability (in %) = Uptime / (Entire time our system is running)
- Availability = Uptime / (Uptime + Downtime)

![image](https://github.com/user-attachments/assets/ceee1488-9dec-481f-9cc5-0c89597c35aa)

### Fault Tolerance and High Availability

#### Sources of failure

There are 3 sources of failures:
- Human errors:
  - Pushing a faulty config to production
  - Running the wrong command/script
  - Deploying an incompletely tested new version of software
- Software errors:
  - Long garbage collections
  - Out-of-memmory exceptions
  - Null pointer exceptions
  - Segmentation faults
- Hardware failures:
  - Servers/routers/storage devices breaking down due to limited shelf-life
  - Power outages due to natural disasters
  - Network failures because of:
    - Infrastructure issues
    - General congestion

#### Methods of Achieving high availability and fault tolerance
- Faliures will happen dispite:
  - Improvements to our code
  - Review, testing, and release processes
  - Performing ongoing maintenance to our hardware
- Fault tolerance is the best way to achieve high availability in our system 

#### Fault Tolerance
- Fault tolerance enables our system to remain operational and available to the users despite faliures within one or multiple of its components
- When faliures happen a fault-tolerant system will:
  - Continue operating at the same/reduced level of performance
  - Prevent the system from becoming unavailable
- Fault tolerance revolves around 3 major tactics:
  - Failure prevention
  - Failure detection and isolation
  - Recovery

#### Failure prevention
- To prevent our entire system from going down, eliminate any single point of failure on our system
- Examples:
  -  One server where we're running our application
  -  Storing all our data on the one instance of our database that runs on a single computer
- The best way to eliminate a single point of failure is through Replication and Redundancy

![image](https://github.com/user-attachments/assets/fb8eef47-87c2-4859-9e46-4738687ef834)
![image](https://github.com/user-attachments/assets/6b1cc4b1-1994-4080-bfb6-db457d81dd81)

##### Types of Redundancy
- Spatial Redundancy - Running replicas of our application on different computers
- Time Redundancy - Repeating the same operation/request multiple times until we succeed/give up

##### Strategies for Redundancy and Replication
- Two strategies which are extensively used in the industry in different systems:
  - Active-Active architecture, If we take the database example, it means that requests go to all the replicas, which forces them to all be in sync with each other. So if one of the replicas goes down, then the other replicas can step in and take all the requests immediately.
  - ![image](https://github.com/user-attachments/assets/22a772c7-754a-42e2-851d-1933ec13c895)
  - Active-Passive architecture, which implies that we have one primary instance or replica that takes all the requests, and the other passive replica or replicas follow the primary replica by taking periodic snapshots of its state.
  - ![image](https://github.com/user-attachments/assets/af2a4800-ea0b-4749-8701-e897d20d11f9)

##### Advanages of Active-Active Architecture
- Load is spread amoung all the replicas
- Identical to horizontal scalability
- Allows more traffic
- Better performance

##### Disadvanages of Active-Active Architecture
- All replicas are taking requests
- Additional coordination required to keep active replicas in sync

##### Advanages of Active-Pasive Architecture
- Implementation is easier
- There is a clear leader with up-to-date data
- Rest of the replicas are followers

##### Disadvanages of Active-Pasive Architecture
- Ability to scale our system is lost
- All the requests still go to only one machine

#### Failure detection and isolation
![image](https://github.com/user-attachments/assets/7a28cb38-713f-4d02-aeaa-cba5bb7fde47)

- Achieve fault tolerance by detecting and isolating faulty instances in a system.
- Example: If an application instance crashes due to software or hardware issues, it must be detected and isolated to prevent further issues.
- Detection Methods:
  - Monitoring Service:
    - A separate system that monitors the health of instances.
    - Health Checks: Sends periodic health check messages to instances.
    - Heartbeat Mechanism: Listens for periodic "heartbeat" messages from healthy instances.
    - Failure Detection: If the monitoring service does not receive a response within a predefined duration, it assumes the server is unavailable.
- False Positives:
  - Network Issues or Temporary Delays:
    - Temporary issues like network latency or garbage collection can cause false positives.
    - False positives are acceptable as long as false negatives are avoided.
- Advanced Monitoring:
  - Error Rate Monitoring:
    - Tracks the number of exceptions or errors per minute.
    - A high error rate may indicate a failure.
  - Response Time Monitoring:
    - Monitors how long each host takes to respond.
    - Excessively long response times may indicate a problem with the server.

#### Recovery from Failure
- Achieve high availability by quickly recovering from failures, minimizing downtime, and restoring normal operations.
- Key Principle:
  - High Availability Formula: Even if failures occur, if recovery is faster than the user can notice, the system remains highly available.
- Actions After Detecting and Isolating a Faulty Instance:
  - Stop Traffic/Workload: Cease sending traffic or workload to the faulty host to prevent further issues.
  - Restart the Instance: Attempt to restart the faulty instance with the hope that the problem will be resolved upon reboot.
  - Rollback:
    - Definition: Revert to a previous version that was stable and correct.
    - Common Use:
      - In databases, rollbacks are used to return to a previous correct state if data integrity is compromised.
      - In software deployments, if a new version causes widespread errors, roll back to the previous stable version to maintain system availability.

### SLA, SLO, SLI

#### Service Level Agreement - SLA
- Definition: A legal contract between a service provider and clients or users.
- Purpose: Represents promises regarding service quality (availability, performance, data durability, response times, etc.).
- Penalties: Details financial consequences for failing to meet promises (refunds, service credits, extensions).
- Applicability:
  - Common for paying external users.
  - Sometimes for free external users (e.g., compensations during trials).
  - Rarely for internal users but can exist to ensure service quality among internal teams.

![image](https://github.com/user-attachments/assets/175b8819-71df-4e7c-9862-deb9c5e574e4)

#### Service Level Objective - SLO
- Definition: Individual goals for system performance and quality.
- Examples:
  - Availability of three nines (99.9% uptime).
  - Response time of less than 100 milliseconds at the 90th percentile.
  - Issue resolution time of 24-48 hours.
- Relation to SLA: Each SLO is a specific agreement within the broader SLA.
- Importance: Even without an SLA, SLOs are crucial for setting expectations for system performance.

![image](https://github.com/user-attachments/assets/ecc6fa28-eafb-4444-8b14-d162767c939d)

#### Service Level Indicator - SLI
- Definition: Quantitative measures of compliance with SLOs.
- Examples:
  - Percentage of successful user requests (availability).
  - Response times and percentiles.
- Purpose: To measure and compare actual performance against the goals set by SLOs.
- Importance: Essential for validating SLOs and ensuring SLA compliance.

#### Considerations for Defining SLOs
- Focus on Important Metrics:
  - Define SLOs based on metrics that matter most to users.
  - Select appropriate SLIs to track these metrics.
- Limit the Number of SLOs:
  - Fewer SLOs are easier to manage and prioritize.
  - Focus on key objectives to align architecture and resources.
- Set Realistic Goals:
  - Commit to achievable SLOs with room for error.
  - Differentiate between external and internal SLOs to balance quality and cost.
- Recovery Plan:
  - Develop a plan for handling failures or performance issues.
  - Include automatic alerts, failovers, rollbacks, scaling policies, and predefined procedures.

## 4. API Design

### Introduction to API Design for Software Architects

**1. Introduction to APIs**
- **What is an API?**
  - API stands for **Application Programming Interface**. It acts as a **contract** between the engineers who develop the system and the client applications that use it.
  - The API defines how different software components communicate with each other, enabling systems to exchange data and functions without exposing internal workings.
  
- **Why do we need an API?**
  - Once we have the functional requirements of a system, we think of the system as a **black box** with behavior and a clear interface for interacting with it.
  - Since other applications will be using our system, we need to define how they can access it. This interface is called the API.

- **Who uses the API?**
  - **External clients**: like web browsers or mobile apps.
  - **Other systems**: internal systems or systems from other companies.
  - **Internal components**: even within our system, different components communicate using APIs.

---

**2. Types of APIs**
- **Public APIs**:
  - Available to the public, anyone can use them.
  - Users typically need to **register** before using the system, providing **better control**, **security**, and the ability to block misbehaving users.
  
- **Private APIs**:
  - Used internally within an organization, not exposed to external users.
  - They enable different teams in the organization to collaborate more effectively without exposing sensitive information outside.

- **Partner APIs**:
  - Similar to public APIs but are only exposed to select business partners with an agreement, such as customers or service subscribers.

---

**3. Benefits of APIs**
- **Encapsulation**: The API allows external systems to use our functionality without knowing about the system’s internal design or structure.
- **Parallel development**: Once the API is defined, client applications can begin integrating even before our system is fully implemented.
- **Easier internal design**: The API defines the entry points and helps organize our system structure more clearly.

---

**4. Best Practices for Designing APIs**
- **Encapsulation**: 
  - The API should hide the system’s internal design. Users should not need to understand how the system works internally to use it.
  - The API should be **decoupled** from the internal structure so that changes to the system don’t affect the API users.

- **Ease of use**:
  - The API should be easy to understand and use. This can be achieved by:
    - Providing **clear, descriptive names** for actions and resources.
    - Offering only one way to access certain data or perform tasks to avoid confusion.
    - Exposing only necessary information and keeping things **consistent** throughout the API.

- **Idempotent operations**:
  - Operations should be **idempotent** when possible. This means performing an action multiple times won’t change the result.
  - For example, updating a user’s address is idempotent because doing it once or multiple times will have the same effect. 
  - Idempotency is important when dealing with network issues like lost requests. If a client isn’t sure whether a request was received, they can safely resend it.

- **Pagination**:
  - When the response contains a large amount of data, it’s better to **paginate** the results rather than send all the data at once.
  - This improves performance and user experience, as clients only receive small, manageable chunks of data.
  - For example, a search engine returns only a few results per page, instead of all possible matches.

- **Asynchronous operations**:
  - For long-running tasks, the API should support **asynchronous operations**.
  - Instead of waiting for the task to complete, the system sends back an immediate response with a tracking ID, allowing the client to check the status of the task later.
  - This is useful for operations like generating large reports or processing large datasets.

- **Versioning**:
  - APIs should be **versioned** to accommodate future changes. Versioning allows us to introduce new features or make improvements without breaking existing clients’ functionality.
  - Maintaining multiple versions ensures clients have time to transition to newer versions gradually.

### RPC

#### What is RPC?
- **Remote Procedure Call (RPC)** allows a **client application** to execute a **subroutine** on a **remote server**.
- RPC makes the remote method call look like a **local method call** in the client’s code. This feature is called **local transparency**.
- It supports multiple programming languages, allowing applications written in different languages to communicate.

#### How does RPC work?
1. The **API and data types** are defined using an **Interface Description Language (IDL)** specific to the RPC framework.
2. The RPC framework **generates code** for two parts:
   - **Client stub**: Automatically handles sending data and making the remote call.
   - **Server stub**: Receives the request, deserializes the data, and executes the method.
3. When the client calls a method, the **client stub**:
   - **Serializes** (encodes) the data and sends it to the server.
4. The **server stub**:
   - **Deserializes** (decodes) the data, executes the requested method, and returns the result.
5. The **client stub** receives the result, deserializes it, and presents it as the return value for the method.

![image](https://github.com/user-attachments/assets/80fbb301-2275-4acb-85fa-b5852241908e)
![image](https://github.com/user-attachments/assets/812ad561-66c3-4b63-8494-c4047ba6224c)
![image](https://github.com/user-attachments/assets/bd8d7be3-fea8-47dc-bd47-9a30df2629d2)

#### Benefits of RPC
1. **Simplicity** for client developers: Once the client stub is generated, developers can call remote methods as if they were local, without needing to manage communication details.
2. **Abstraction**: All the complexities of network communication (data encoding/decoding) are hidden from the developer.
3. **Cross-language support**: RPC frameworks can enable communication between different programming languages.

#### Drawbacks of RPC
1. **Slower performance**: Remote methods are much slower than local ones because they rely on network communication.
   - This may create **unexpected performance issues**, as remote calls appear similar to fast local calls in code.
   - To mitigate this, slow methods should have **asynchronous** versions, so the client code doesn’t block waiting for a result.
2. **Unreliability**: Since the client and server are on separate machines, communication issues can arise (e.g., lost messages).
   - The client may not know whether a failure happened or whether the server processed the request.
   - One way to reduce risk is by making operations **idempotent**, so repeating a call doesn’t cause unintended side effects.

#### When to use RPC
1. **Backend-to-backend communication**: RPC is best for communication between backend systems, especially within large-scale systems.
2. **Internal system communication**: RPC can help connect different parts of the same system seamlessly.
3. **Action-oriented APIs**: RPC is suitable when the focus is on performing **specific actions** (like updating or processing data), rather than managing data resources.

#### When NOT to use RPC
1. **Frontend clients**: RPC is less common for APIs designed for web browsers or mobile apps.
2. **Data-centric APIs**: For APIs that mainly deal with data (CRUD operations), another API style (like REST) is often a better fit.
3. **Control over network communication**: If you need fine-grained control over **HTTP headers, cookies**, or other network-level details, RPC may not be suitable.

#### Summary
- RPC allows a client to call a remote server method just like a local method call.
- It involves three components: **API definition**, **client stub**, and **server stub**.
- Benefits include simplicity and local transparency, while drawbacks include performance and reliability issues.
- RPC is well-suited for backend communication but may not be the best choice for frontend clients or data-centric operations.

### REST API: Overview and Key Concepts

#### Core Characteristics of REST API:
- **Resource-Oriented**: The primary abstraction is **resources** (e.g., movies, users), not methods.
- **Representation of Resources**: Resources are exposed via URIs (Uniform Resource Identifiers), and when requested, their current **state** is returned to the client.
- **Protocol**: REST APIs commonly use **HTTP** as the protocol for communication.
- **Statelessness**: Servers do not store session data, leading to improved **scalability**.
- **Cacheable**: Responses can be marked as **cacheable** or non-cacheable to enhance performance.

####  REST API vs RPC API
- **RPC (Remote Procedure Call)**: Focuses on **methods** (actions), where the client makes method calls, and new operations require adding more methods.
- **REST API**: Focuses on **resources** (data/entities), where a few HTTP methods (GET, POST, PUT, DELETE) allow interaction with these resources.

####  REST Constraints and Benefits

1. **Scalability and Statelessness**:  
   REST APIs must be **stateless**, meaning each request from a client to the server must contain all the information necessary to understand the request. Servers don't keep track of client states, so multiple servers can handle requests from the same client, improving scalability and availability.
   
2. **Cacheability**:  
   Responses can be cached to minimize server load. REST APIs can explicitly state whether responses are cacheable, reducing unnecessary round trips between client and server.

3. **Uniform Interface**:  
   RESTful systems use a standard set of **methods** to manipulate resources, unlike RPC systems where many custom methods can be defined.

#### Hypermedia and Dynamic Nature of REST API
A key feature of RESTful APIs is **Hypermedia as the Engine of Application State (HATEOAS)**. In response to a request, along with the resource's state, REST APIs also send **hypermedia links** that provide further actions the client can take. This creates a **dynamic** system where the client's internal state can change by following the links provided in the server's responses.

#### Resources in REST API
Resources represent **entities** within a system and can be anything such as users, movies, or orders. Resources are organized in a **hierarchical** structure using **URIs**:
- Simple resource: A specific entity (e.g., `/users/1`).
- Collection resource: A set of entities (e.g., `/users` for a list of users).

#### Best Practices for Resource Naming:
1. **Use nouns, not verbs**: Resources should be named with nouns to differentiate between the resource and actions (e.g., `/users`, not `/getUsers`).
2. **Singular vs. Plural**: Use plural names for collections (e.g., `/movies`) and singular names for individual resources (e.g., `/movies/1`).
3. **Meaningful Names**: Avoid generic names like `items` or `elements`; use clear, descriptive names to ensure usability.
4. **URL-friendly**: Resource identifiers should be unique and safe for web usage.

#### HTTP Methods and REST Operations
REST APIs use the following **HTTP methods** to interact with resources:

- **GET**: Retrieve the state of a resource (read-only).
- **POST**: Create a new resource.
- **PUT**: Update an existing resource.
- **DELETE**: Remove a resource.

The **GET**, **PUT**, and **DELETE** methods are **idempotent**, meaning the effect of applying them multiple times is the same as applying them once. Additionally, **GET** requests do not alter the state of the resource and are **safe** to cache.

#### Designing a REST API Step-by-Step

Let's go through the process of creating a REST API for a **movie streaming service**.

1. **Identify Entities**:  
   The main entities in our service might be users, movies, reviews, and actors.
   
2. **Map Entities to URIs**:  
   Each entity corresponds to a resource, and URIs are used to organize them in a hierarchy:
   - `/users`: Collection of users.
   - `/users/{userId}`: A specific user.
   - `/movies`: Collection of movies.
   - `/movies/{movieId}/reviews`: Reviews for a specific movie.
   - `/actors`: Collection of actors.

3. **Resource Representation**:  
   Resources can be represented in different formats, but **JSON** is commonly used. For example, the representation of a movie resource might include details like the title, release date, and associated links to reviews and actors.

4. **Assign HTTP Methods**:
   - **POST** on `/users`: Create a new user.
   - **GET** on `/users/{userId}`: Retrieve a user's details.
   - **PUT** on `/users/{userId}`: Update a user's profile.
   - **DELETE** on `/users/{userId}`: Remove a user from the system.

