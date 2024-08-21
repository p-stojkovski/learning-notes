# Software Architecture & Design of Modern Large Scale Systems

## Introduction

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

## System Requirements & Architectural Drivers

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



