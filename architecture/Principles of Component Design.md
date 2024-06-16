### In software development there are 3 Types of complexity: 
1. Complexity in the domain (simplify bussiness processes and concepts can help, but that is often beyond control of developers)
2. Complexity in the implementation (local to a class or small set of classes, to manage it we apply Clean Code, SOLID and design patterns)
3. Complexity in the architecture and design (global, resulting from unclear responsibilites and tangled dependencies of multiple components, this type can ultimatly determine the success or faliure of endtire software project).

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/ad50bbf4-9cc4-4259-b176-c44397cc8fd8)

### What is a component?
- Reusable indendent deployable unit of software that performs specific function and interacts with other components through defined interfaces.
- Allows teams to focus on isolated components without worrying too much about the entire system.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/4067e03c-278c-4883-99de-4e49e37415cd)

### 1st principle of component design is: **Reuse/Release equivalence principle**
- "The granule of reuse is the granule of release"

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/5e51013b-a530-4b99-9f4e-3b81d5034a3a)

### 2nd principle of component design is: **Common reuse principle**
- The classes in a component are used together. If you reuse one the classes in a component, you reuse them all.
- Well design components should be inseparateable.
- Classes that are not tightly coupled should not be in the same component.
- Applying this principle results in smaller components with high cohesion amoung the classes inside the component.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/693e059a-5196-46bc-8fd9-cd4effa04dce)

### 3rd principle of component design is: **Common closure principle**
- The classes in a component should be closed together against the same kind of changes. A change that affects a component affects all the classes in that component, and no other components.

![image](https://github.com/p-stojkovski/learning-notes/assets/3589356/0587274e-065d-42bd-b323-430bbd2e7567)

### How to apply?
- Use a high-level breakdown of functions as a guide for initial class and component design.
- Examine the existing classes within the system to understand their roles and relationships.
- Group these classes into components based on their functions and interdependencies.
- Ensure components are logically partitioned and minimize tightly coupled dependencies.
- Continuously monitor how components and their classes evolve.
- Apply refactoring as needed to adapt to changes in class responsibilities and dependencies.
- Focus on maintaining clear, cohesive components.
- Regularly revisit and refine component boundaries and responsibilities to ensure they align with the system's current needs.


