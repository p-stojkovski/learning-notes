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

#### Introduction to System Design & Architectural Drivers
Requirements - Motivation:
- Format description of what we need to build
- Large scale system requirements are different than the usual requirements we typically get for implementing:
  - A method
  - An algotithm
  - Class

High Level of Ambiguity
- System Design has high level of ambiguity
- Two reasons: 
  - The persion providing the requirements is often not an engineer and may even br not very techical
  - Getting the requirements is part of the solution: The client doesn't always know what they need, only what prblem they need solved.
 
Importance of Gathering Requirements
- What happens if we don't get the requirements right?
  - We can simply build something and then fix it.
  - Seemingly there is no cost of materials in software so changes should be cheap?
  - Large scale systems are big projects that cannot be easily changed.
  - Many engineers are involved.
  - Many months of engineering work
  - Hardware and Software costs
  - Contracts include financial obligations
  - Reputation and brand

Requirements - Classification:
