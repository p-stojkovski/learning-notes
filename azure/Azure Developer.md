
# Azure Developer

CLOUD SKILLS CHALLENGE

Azure Developer
Participate in all phases of cloud development to create end-to-end solutions. Design, build, test, and maintain cloud applications using compute, storage, management, and security services on Azure. In under 30 hours, you'll learn about storing data in Azure, creating serverless applications, connecting your services together, and more.




## Roadmap

- Common business issues
- Design-first technologies


## Notes

## Common business issues

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
