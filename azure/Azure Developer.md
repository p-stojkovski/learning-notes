
# Azure Developer

CLOUD SKILLS CHALLENGE

Azure Developer
Participate in all phases of cloud development to create end-to-end solutions. Design, build, test, and maintain cloud applications using compute, storage, management, and security services on Azure. In under 30 hours, you'll learn about storing data in Azure, creating serverless applications, connecting your services together, and more.

## Roadmap

- Common business issues
- Design-first technologies

## Choose the best Azure service to automate your business processes 

### Common business issues

Business processes modeled in software are often called workflows. Azure includes four different technologies that you can use to build and implement workflows that integrate multiple systems:

- Logic Apps
- Microsoft Power Automate
- WebJobs
- Azure Functions

### Logic Apps
Logic Apps is a service within Azure to automate, orchestrate, and integrate disparate components of a distributed application.

So, let's say you want to automate sending an email whenever someone fills out a form on your website. You can use Azure Logic Apps to connect your form app to your email app. Then, whenever someone submits the form, the Logic App will automatically send an email without you having to do anything. You have different tasks you want to do on your computer, like sending an email when a new file appears in a folder, or posting a tweet when someone fills out a form. Instead of doing each of these tasks manually, Azure Logic Apps lets you create a set of instructions, like a recipe, for your computer to follow.

These instructions are called workflows, and they're made up of different steps, like mixing ingredients in a recipe. With Azure Logic Apps, you can connect different apps and services together, like Lego blocks, to build these workflows.

### Microsoft Power Automate
Microsoft Power Automate is a service to create workflows even when you have no development or IT Pro experience.

There are four different types of flow that you can create:

- Automated: Starts by a trigger from some event. For example, the event could be the arrival of a new short post or a new file being uploaded.
- Button: Runs a repetitive task with a single click from your mobile device.
- Scheduled: Runs regularly. For example, once a week, on a specific date, or after 10 hours.
- Business process: Models a business process such as the stock ordering process or the complaints procedure. The flow process can have: notifications to required people; with their approval recorded; calendar dates for steps; and recorded time of flow steps.

Here's the deal: Power Automate helps you automate tasks on your computer without needing to do them yourself. It's like having a digital assistant that follows your instructions to get stuff done.

So, how does it work? Well, you create what's called a "flow," which is basically a set of instructions for the computer to follow. These instructions tell the computer what to do when certain things happen, like when you receive an email or when a file is added to a folder.

### WebJobs
The Azure App Service is a cloud-based hosting service for web applications, mobile back-ends, and RESTful APIs. These applications often need to perform some kind of background task. For example, in your bike rental system, when a user uploads a photo of a bike, you may need to generate a smaller thumbnail photograph.

WebJobs are a part of the Azure App Service that you can use to run a program or script automatically. 
There are two kinds of WebJob:

- Continuous. Starts immediately when the WebJob is created and runs in a continuous loop. For example, you could use a continuous WebJob to check a shared folder for a new photo.
- Triggered. Starts based on a binding event, on a schedule, or when you trigger it manually (on demand).

Here's how it works: You create a WebJob by giving your digital assistant a set of instructions. These instructions can be simple, like "run this program every day at 8 AM," or more complex, like "process these files as soon as they're uploaded."

Once you've set up your WebJob, it sits quietly in the background, waiting for its turn to do its job. And when the time comes or when a trigger occurs, like a new file being uploaded, your digital assistant springs into action and gets the job done, just like you asked.

### Azure Functions

An Azure Function is a simple way for you to run small pieces of code in the cloud, without having to worry about the infrastructure required to host that code.

So, here's the deal: Azure Functions let you write little bits of code that do specific things. These bits of code are called functions. And just like saying a word triggers a spell, something called a "trigger" makes an Azure Function run.

Now, what can these functions do? Well, pretty much anything you want! You can use them to process data, respond to events, or even build entire applications.

Here's an example: Let's say you have a website, and you want to send a welcome email to every new user who signs up. You can create an Azure Function that listens for new sign-ups (that's the trigger), and when someone signs up, the function automatically sends them a welcome email.

### Analyze the decision criteria

There are several different business processes that run your bicycle rental business. For example, there's the bike rental process, a return process, a bike booking process, and processes that don't directly relate to bikes, such as holiday booking for the staff.

How to choose a service?

The first question to ask is whether you prefer to design the workflow in a GUI designer tool or by writing code. Valid reasons for using a design-first tool include:

- People who design the workflow have no coding experience.
- Later designers and users can consult the graphical design to clearly understand how the workflow proceeds.

Alternatively, you can choose to use a code-first tool because:

- People who design the workflow are developers and prefer to work entirely in code.
- You want the details of a workflow to be hidden from non-coders.

### Choose a design-first technology

If you want to plan how work gets done, you can choose between Microsoft Power Automate and Azure Logic Apps.

With Azure Logic Apps, you draw out the plan visually and can also edit the code if you're into coding.

With Microsoft Power Automate, you get lots of ready-made plans, but you can't change the code. It's more for people who don't know how to code but understand the work process.

### Choose a code-first technology

If you prefer coding to plan how work gets done, you can choose between WebJobs and Azure Functions.

Azure Functions is usually the better choice because it offers more features, like different ways to start tasks, supports more programming languages, allows testing code online, and charges based on how much you use it.

However, there are times when WebJobs might be a better fit:

1. If you already have an app on Azure App Service and want to add the workflow directly into it.
2. If you need to customize the JobHost in ways that Azure Functions doesn't support.
3. If you want more control over how your app handles retrying tasks.

### Mixing technologies

Imagine you have a business process where you need to process customer orders.

You start by creating a workflow in Microsoft Power Automate to receive and validate the order details submitted by customers through a form on your website. Once the order is validated, you want to trigger a series of actions, like updating your inventory database and sending a confirmation email to the customer.

Here's where mixing technologies comes in handy:

1. Receive and Validate Order (Microsoft Power Automate): You design a flow in Microsoft Power Automate to receive the order details and validate them. For example, checking if all required fields are filled and if the items are in stock.

2. Inventory Update (Azure Function): After the order is validated, you use an Azure Function to update your inventory database automatically. This function is triggered by the successful validation of the order from the Power Automate flow.

3. Send Confirmation Email (Azure Logic App): Finally, you set up a Logic App in Azure to send a confirmation email to the customer. This Logic App is triggered by the successful completion of the inventory update function.

By using a mix of Microsoft Power Automate, Azure Functions, and Azure Logic Apps, you've created a seamless process where each technology handles a specific part of the workflow. This not only allows for better control and customization but also enables you to leverage the strengths of each tool for different tasks within the overall process.

### Choose the best design-first technology to automate your business process
#### Scenario: https://learn.microsoft.com/en-us/training/modules/choose-azure-service-to-integrate-and-automate-business-processes/4-logic-apps-and-flow

### When to choose Azure Functions to run your business logic
#### Scenario: https://learn.microsoft.com/en-us/training/modules/choose-azure-service-to-integrate-and-automate-business-processes/5-web-jobs-and-functions

### Use cases

#### Design-First Approach:

1. Expense Approval Workflow:
    - Scenario: Employees submit expense reports for approval.
    - Use Case: Design the workflow visually in Microsoft Power Automate, where users can submit expense reports through a form, managers receive notifications to review and approve/reject, and finance teams get notified for payment processing.
2. Customer Support Ticketing System:
    - Scenario: Handling customer support tickets efficiently.
    - Use Case: Use Azure Logic Apps to design a workflow where incoming support emails are automatically converted into tickets, assigned to the right department based on keywords, and tracked until resolution, all without writing code.

#### Code-First Approach:

1. Real-Time Data Processing:
    - Scenario: Processing real-time data from IoT devices.
    - Use Case: Develop an Azure Function to process incoming sensor data, perform complex calculations or analytics, and store results in a database. This approach allows for fine-grained control over data processing logic and scalability.
2. E-Commerce Order Fulfillment:
    - Scenario: Fulfilling orders from an online store.
    - Use Case: Create a WebJob to handle order fulfillment tasks such as inventory management, order processing, and shipment tracking. This code-first approach enables customization of business logic and integration with existing systems like ERP or warehouse management.
