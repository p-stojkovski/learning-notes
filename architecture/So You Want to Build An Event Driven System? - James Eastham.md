- An event driven architecture lets you tell the story of your business, through it's techical implementation, the language of your bussiness it's what's drives the functionality.

- Communication pattern (between two services or human communication)

- "You learn much more in failure, than you do in success"

![image](https://github.com/user-attachments/assets/616ddcbc-421a-45d9-8417-3ec3711b27a4)

- "Aim for low coupling and high cohesion"

- Types of coupling:
![image](https://github.com/user-attachments/assets/41f09fcf-24dc-4411-aed0-40c99e39b8a0)

- "The appropriate level of coupling depends on the level of control you have over the endpoints" - Gregor Hohpe

- What is an event?
  - An event is an immutable fact, something that has happened in the past and cannot be changed. 

- What is event driven?
  - An event driven system triggers business functionality from business events.

- Events are first class citizens.
  
- Types of messages: Commands, Events, Queries
- Types of events:
  - Notification event: simple, small package of data that notifies another system something has happened. 

- Event message structure:
![image](https://github.com/user-attachments/assets/6ca9cfdc-79d4-4462-a2da-36de209e2033)


- Event-Driven Architecture (EDA) is a communication pattern that models system integration. It enables systems to communicate through events, promoting loose coupling and asynchronous communication.

- EDA can improve system scalability, resilience, and developer velocity. By decoupling systems, you can make changes independently and reduce the blast radius of failures.
- Start small when implementing EDA. Begin with a small, non-critical part of your system to gain experience and minimize risks.
- Use a consistent event schema. This promotes interoperability and reduces coupling between systems. Consider using the CloudEvents specification for a standardized approach.
- Be conservative in what you send in events. Include only essential information to minimize coupling.
- Leverage patterns like transactional outbox and change data capture. These patterns can help you reliably publish events and manage data consistency.
- EDA is not a silver bullet. It has its own challenges and trade-offs. Carefully evaluate if it's the right approach for your specific use case. 


