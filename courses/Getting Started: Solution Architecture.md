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
