# Datadog Fundamentals

### Notes on Infrastructure and Application Monitoring with Datadog

**1. Key Aspects of Monitoring:**
   - **Infrastructure Monitoring**: Tracks server performance, availability, and resource usage (e.g., CPU, RAM, storage).
      - These are recorded as **metrics** that represent measurements over time, like CPU utilization percentage or errors per minute.
   - **Application Performance Monitoring**: Provides an overview of the entire system, combining both infrastructure and application metrics.

**2. Features Needed in a Monitoring Solution:**
   - **Cloud-Based Service**: Allows Globomantics to focus on their work without setting up additional systems.
   - **Flexible Data Collection**: Should easily gather data from various resources like servers, databases, and containers.
   - **Filtering Capabilities**: Should allow tagging and filtering of metrics for targeted analysis.
   - **Visualization**: Supports creating dashboards, graphs, and other visuals to help analyze data.
   - **Alerts and Notifications**: Provides timely notifications for issues via email, text, or other channels.

**3. Why Datadog?**
   - Datadog offers the flexibility, visualization, and alert capabilities Globomantics needs for efficient, global monitoring.

### Datadog Features Overview

**1. Introduction to Datadog:**
   - Datadog is a **cloud-based monitoring platform** that provides real-time insights into infrastructure and application performance.
   - It’s designed for system administrators, DevOps, site reliability engineers, and developers to monitor and optimize systems.

**2. Key Features of Datadog:**
   - **SaaS Application**: As a cloud-based service, Datadog doesn't require users to manage hardware or software installations.
   - **Integrations**: Datadog supports hundreds of integrations, allowing metrics to be easily collected from various resources. Each integration has its own documentation, making setup straightforward.
   - **Agents**: Datadog offers an open-source agent that collects data and sends it back to the platform. The agent code is available on GitHub, providing transparency and flexibility.

**3. Tagging, Filtering, and Querying Data:**
   - **Tags** help organize and filter data, especially useful when monitoring thousands of resources.
   - **Custom Query Language**: Datadog offers a query language for selecting specific metrics, performing advanced analysis, and setting up monitors.

**4. Advanced Visualization:**
   - Datadog supports various types of **visualizations** like time series graphs, pie charts, and heat maps. These tools help users quickly interpret data and identify trends.

**5. Alerts and Notifications:**
   - **Continuous Monitoring**: Datadog can be set to monitor resources and trigger alerts when specific conditions are met.
   - **Integration with Messaging Systems**: Datadog works with tools like Slack and PagerDuty, enabling notifications and assisting with incident response when issues arise.

### Overview of Datadog Integrations

**1. What Are Integrations in Datadog?**
   - **Integrations** are one of Datadog's most powerful features, providing an easy way to collect metrics from applications, infrastructure, and cloud services.
   - These integrations enable applications and infrastructure components to consistently send data to Datadog without manual setup.
     
**2. Sources for Metrics Collection:**
   - **Applications and Code**: Collects data on application performance and any errors, helping with debugging and ensuring the application is functioning as intended.
   - **Infrastructure**: Includes servers, databases, containers, and serverless functions where code is run. This layer provides metrics on how the infrastructure supporting the application is performing.
   - **Cloud Services**: Covers cloud platforms like AWS, Google Cloud, and Azure, where applications and infrastructure are hosted. Cloud service metrics give insight into the environment running the applications.

**3. How Integrations Work:**
   - Each integration acts like a **connector** that sends metrics from a specific resource to Datadog.
   - Integrations are **pre-configured** to simplify data collection, packaging, and sending, so users don’t have to worry about the technical setup.
   - Many integrations come with **ready-made dashboards** and visualizations, allowing users to start monitoring without creating custom views.

**4. Using Integrations in Practice:**
   - By integrating each layer (cloud account, server, application), users get a **comprehensive view** of the entire system.

**Example**: 
Imagine you have a web application hosted on AWS. To monitor this setup, you start by installing the AWS integration in Datadog. This integration automatically pulls in metrics from your cloud resources—like CPU usage, memory, and network traffic for EC2 instances.

Then, you add an integration for MySQL if your application uses a MySQL database. This integration will send data on query performance, connection status, and database size to Datadog.

Finally, you set up an integration for Docker if your application runs in containers. The Docker integration will collect metrics on container health, resource usage, and restarts.

By combining these integrations, Datadog provides a complete view of your application's performance across the cloud infrastructure, database, and containers, all visible from a single dashboard.

**5. Starting with the AWS Integration:**
   - Installing the AWS integration first allows Datadog to collect high-level cloud metrics.
   - Integrating at the cloud level often triggers automatic installations of other relevant integrations, streamlining the process of setting up a full monitoring solution. 

Integrations in Datadog simplify monitoring by automating data collection and providing out-of-the-box visualization for each component in the application stack.
