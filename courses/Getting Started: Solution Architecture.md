## Getting Started: Solution Architecture - https://courses.dometrain.com/courses/take/getting-started-solution-architecture

### What is software architect?
- The shared understaing that the expert developers have of the system design
- About of the important stuff, whatever that may be.
- Focus on most important characteristics and business requirements, you can create system that works well and long time
- Focus on what really matters

Example: Building architects

### The Software Architect's Elevator
The problem:
Gathering bussiness requirments, the architect need to have a lot of dissusions with bussiness people, from bussniess leaders to junior developers. The danger is if you spend too much time with higher level people in the hierarcy, you run the risk of becoming higher level architect, the one who mandating with builing things, distributing architecture decisions, just telling people what to do without understanding what's really happening on the ground, how the sistem is being build.

But, if you spent too much time on the ground, you can lose that perspective of the bigger picture and strategic directions that the bussiness is taking.

Solution: **The Software Architects Elevator**

Must understand the problem that system is solving.

### The importance of the bussiness context
It's very important to understand the bussiness context and translate to technical desing.

Very important conversation flow when talking to bussiness person and gathering information:
1. What is the primary purpose of the system?
2. Dive deeper into the business context, the use case!
3. More business ontext... It's important!
4. Clarify understanding!
5. How critical is the component? What happens if it isn't working?
6. How does the component fit into the wider business landscape?
7. What is expected load?
8. Are there any plans for that load to grow?
9. Any other integration (sytems) required?

### Optimizing for Change
Change can be unsettling, but it's also a sign of growth. Only trought change you can improve and adapt to new challenges and opportunities.
Embrace change as constant force in life and use it to get you forward for grater success.

As a software architect when design a system is very important to consider that the system will evolve and adapt to changing conditions.

You want your system to grow and change as the organisation grows.

### Impact as an Architect
Ensure you're delivering value as an architect.
- Act as enabler. (enable fast flow in dev team: collaborate closely with the teams)
- How you colaborate with the teams. (Work directly with the dev teams short periods of time and understand the challenges they are facing and take that knowlege to improve the bigger picture view.)
- Getting involved in problems (understand the team issues)

### Systems Thinking
All systems are made from 4 primary components:
- Inputs -> Process -> Output -> Feedback -> Inputs

System thinking of software architect not only involves desinging your component, but also avout designing the interaction with other components. 
- Help you manage complexity, keep you focus on the bigger picture
- Understand emergent properties(performance, resilience) 

### The Value Of Communication
Important ability as an architect, verbal, written, be confident to express your ideas clearly and translate them to techical and notechical, and vice versa

## System Design

### Functional vs non-functional requirements
Functional: Describe the specific features and capabilites that software needs to posses to fulfill users needs. (Cover the actual things that the end users of the system needs to acheve)

Non-functional: Speed, performance, scalability, security, useablity, relibility, availability, durability, latency. (Common accross all organisations, play a crucial role, grather impact than functional)

### Gathering Functional Requirements
You're builing something that meets user needs.

Non-functional questions tips:
- What are the performance requirements?
- What are the security or governance requirements?
- How critical is the system, how available should it be?
- How much impact would it have if this component was offline for 1, 2, 6, 24 hours?
- What are the peak times?

If you don't have any non-functional requirments, that's an architectual smell.

### Architectural -ilities and understanding trade offs
-ilities are critical considiration on software engineerting, use to measure the overall effectivness of your system. (performance, reliability, maintanibiliy, scalability, usability)

- Performance:
  - How quickly must your system respond?
  - Is it a background system processing batches, how quickly need to process?
  - How does the performance need to change based on the load the system is under?
- Scalability:
  - How scaleable your system needs to be?
  - What is the steady user load, what is the peak user load?
  - Is the traffic predictable?
  - What dimensions you have available to scale, horizontaly and verticaly?
- Availability & Reliability
  - How long the system to run without faliure?
  - How long it take the system to recover?
  - Mean time before failure?
  - Can downtime be scheduled?
- Security
- Evolvability
- Maintanibiliy
- Flexibility
- Usability (build MVP)
- How easy is your sytem to integrate with? (is it sync, async, cosistency between components?)

All takes down to Trade offs. If you need high avaiablity and reliability, optimizing for cost can be difficult. If you need high security, your performance can be hit.
It depends on which non-functional requirements.
Keep evolability on top of your mind!
  
### Architect in characteristics
Think in characteristics, patterns for different situations!

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/4e431ad8-9716-4893-973c-e136d58a4d22)

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/8b8831b6-9a71-4459-9f09-6eb56d94e64a)


### Modularity, Coupling and Cohesion
Modularity is dividing your system into separate modules that can be developed independently. Make system easy to understand, develop and mantain. Changes in one module should not direct impact another module.

Coupling, the degree of interdependence between different modules. 
- Target loose coupling. Runtime coupling, when one system needs to know the location of another, exaple http requests.
- Temporal coupling when two or two modules depend of timing or order of events.
- Content coupilng, when one module can modify the data of another directly, like shared database (avoid).
- Functional coupling, when 2 or more modules depend on eachother functionalities
- Sequential coupling, the output of one module feed directly into another.

Target: reduce coupling as much as possible.

Cohesion, the degree to which the elements inside a module belong together. 
- Things that change together, live together.
- Keep focus on one job
- Apply single responsibility
- Interact with other modules in loosly coupled way
- Clear focused modules with defined purpose
- A Structure is stable if cohesion if high and coupling is low!

Target: high cohesion.

### Customers & their Access Patterns
When designing a system is crucial to consider the end users, not only meets the intent of the end users, but also be efficent and effective, meeting the goals of your organisation. 

You are building software for people.

Build things right for your organisation, based on your charactericts and business requirements keeping your end users in mind!

## Architecture Styles

### Monoliths
Type of architecture where all the functionality of the system is tightly together.
Deployed as a single unit.
Simple to develop.
Fantastic when starting out.

Can be challenging to scale and mantain.
Can lead to big ball of mud. (Unregulated growth and repeated expedited repair)
Maintaining a monoloth requires a big responsability.

### Layered Architecture (N-tier)
Breaks your system down into horizontal slices.
Clearly separates concerns.
Presentation layer does not need to know what DB provider is used.
Each layer provides abstraction aroud specific task.
Allows developers to focus on individual experties. (UI, backend, Data)

**Watch out for**: Architectual sink-hole (anti-pattern), occurs when request simply passes through layers with no additional value added. If presentation layer talks to bussiness layer with nothing just passing the request to the persistence layer just to get data from db, you probably have unnecessary layers to the application, just adding unnecessary allocations, processing and could pottentialy have impact on performance.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/3a7c1ba3-5ffd-4e12-a668-7f97ca1464d7)

### Hexagonal Architecture (Onion, Clean)
Design software systems that separate core business logic from external concerns. (UI, databases, external services)
Fits well in organisation that practices Domain Driven Design.
Great on long term.
Provides a clear separation of concerns and evoleability.
The bussiness logic is the heart (central core) of the architecture.

Ensure to have right organisational structure and working practices in place when starting out.

Which style do I use, Layered or Clean...?
- Let the system complexity drive the architectual style.
- CRUD? Start with Layered Architecture.
- Complex bussiness logic and rules, change often bussiness rules without to wory about of the implemntation details? Start with Clean Architecture.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/ef6cb0a5-8fcb-429a-b183-77df74fdaddf)

### Service Oriented Architecture
Good for scaling.
Any change on one service, the other services does not need to know about the change.
Think if for example the services need to comunicatie between eachother, and one fails, how to you mange the failiure?
Introduce complexity through inter-service communication
All about flexibility and scalability, but it does need coordination for all services work together.

When to use?
- If application is large and complex
- If different part of system have different scaling requirments
- If you organisation is structured by features or domain, not by techical experties. (Separate team(ui, backend, data) for every service working independently on feature)

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/0b24644b-80b1-429a-9cad-41ac9e08cdc5)

### The Fallacies of Distributed Computing
What is distributed system? System located on different machines that work together as a single entity.
Don't assume anything, design with the fallacies in mind.

- The network is reliable. It can fail! Think about what are you going to do if the network fails.
- Latenty is zero. It needs the data to travel across network. Let say you have 10 services communicate to perform a task, and there is 100ms per service latency, that's total 1sec.
- Bandwidth is infinite. It has limits. If you have request that returns 500kb, but if that endpoint is requstes 2000 times per minute, you have 1GB transfered every single minute.
- Network is secure. It is not always true.

### Microservices
Excellent choice when done right, and extremly easy to get very wrong!

- Small self contained unit. Has one job, and does it very good.
- Scalability, Flexibiliy and Resiliance.
- Update and fix small part of the system without affecting the whole.
- Each microservice is an independently deployable unit

When to consider?
- Large application with components that have different data or scaling requirments
- Different techologies for different microservices

First consider these questions?
- What are you hoping to acheve?
- Have you considered alternatives?
- How will you define success?

Vision about the goal, what are you aming for?  Strategy about how you are going to do it?

Be comminted to the vision but very flexible with your strategy!

What is the difference between service oriented architecture and microservices?
- Both are separating in services (order, dispach, inventory)
- SOA can have services that can be large and complex, but doing a single job, one feature logic only. Communication between services.
- Microservices have services that can have multiple features within them.
- SOA and Microservices use services as they builing blocks, SOA tends to have bigger multifunctional blocks, where mictoservices breaks down in small units of deployment.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/03e019ad-81e3-4a21-8612-88127204f111)
