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

### Understanding the Datadog Agent

**1. What is the Datadog Agent?**
   - The **Datadog agent** is software installed directly on a server or resource that collects detailed, system-level metrics and sends them to Datadog.
   - Unlike cloud integrations that monitor from a high level, the agent provides deeper visibility into what’s happening **inside** each server.

**2. Why Use the Datadog Agent?**
   - The agent helps track metrics from within servers, showing CPU, memory, processes, and even specific software activity.
   - It detects services (like databases, web servers) running on the server and suggests additional **application-specific integrations**.

**3. Installing the Datadog Agent**
   - **Platform Support**: Available on Linux, Windows, and more.
   - **Installation Instructions**: The Datadog console provides specific steps for each platform.
   - **Manual Installation**: For a few servers, install manually using SSH (Linux) or RDP (Windows).
   - **Automated Installation**: For large environments, use tools like **Chef, Puppet,** or **Ansible** to automate the agent installation.

**4. Configuring the Datadog Agent**
   - After installation, configure the agent by editing the `datadog.yaml` file:
      - **Set Hostname**: This helps label each server meaningfully.
      - **Enable process_collection**: Allows tracking of all processes on the server.
   - **Restart the Agent**: To load the new configuration, run `systemctl restart datadog-agent` on Linux or restart the service in Windows.

**5. Summary**
   - The Datadog agent allows for deep visibility by monitoring metrics inside servers and detecting installed services. This makes it a powerful tool for monitoring applications and infrastructure comprehensively.

### Datadog VS Azure Application Insights
**Datadog** and **Azure Application Insights** are both tools designed to monitor applications and infrastructure, but they have distinct features, benefits, and drawbacks.

**Datadog:**

- **Overview:** A comprehensive monitoring and analytics platform that provides real-time visibility into the performance of applications, infrastructure, and logs.

- **Benefits:**
  - **Broad Integration Support:** Datadog integrates with a wide range of cloud services, including AWS, Google Cloud, and Azure, allowing for unified monitoring across different platforms.
  - **Advanced Visualization:** Offers customizable dashboards with various visualization options like graphs, heatmaps, and live updates, aiding in effective data analysis.
  - **Flexible Alerting:** Provides advanced alerting options, enabling users to set complex conditions based on metric patterns and anomalies.
  - **Scalability:** Designed to handle large-scale environments, making it suitable for organizations with extensive infrastructure.

- **Drawbacks:**
  - **Cost:** Pricing can be higher, especially for extensive monitoring needs, as it charges based on the number of hosts and features used.
  - **Learning Curve:** The wide array of features and customization options may require time to fully understand and utilize effectively.

**Azure Application Insights:**

- **Overview:** A feature of Azure Monitor, it focuses on application performance management, providing insights into application health and usage.

- **Benefits:**
  - **Seamless Azure Integration:** Tightly integrated with Azure services, offering a unified experience for applications hosted on the Azure platform.
  - **Cost-Effective for Azure Users:** Often more economical for applications running within Azure due to integrated billing and resource management.
  - **Ease of Use:** Simplified setup for monitoring applications within the Azure ecosystem, with straightforward configuration and deployment.

- **Drawbacks:**
  - **Limited Cross-Platform Support:** Primarily optimized for Azure services, with less robust support for other cloud platforms.
  - **Basic Visualization and Alerting:** Offers fewer advanced visualization and alerting features compared to Datadog, which may limit in-depth analysis capabilities.
  - **Scalability Constraints:** May face challenges in handling very large-scale environments or complex multi-cloud architectures.

**Choosing Between Datadog and Azure Application Insights:**

- **Use Datadog if:**
  - You require monitoring across multiple cloud platforms.
  - Advanced visualization and alerting features are essential for your operations.
  - Your infrastructure is large-scale and demands a highly scalable solution.

- **Use Azure Application Insights if:**
  - Your applications are primarily hosted on Azure, and you prefer tight integration with Azure services.
  - Cost considerations are a priority, and you seek a more economical solution within the Azure ecosystem.
  - You need a straightforward, easy-to-use monitoring tool for Azure-based applications.

In summary, Datadog offers a versatile, feature-rich monitoring solution suitable for diverse and large-scale environments, while Azure Application Insights provides a more streamlined, cost-effective option for applications within the Azure platform. 

### Cost Comparison for Usage, Example Scenario

For this scenario:
- **3 servers (hosts)** running applications
- **10 GB of logs** per month
- **500 custom metrics** to monitor
- **1 million requests** per month

---

### 1. **Azure Application Insights Costs**
Azure Application Insights pricing is based on **data ingestion** (in GB), **custom metrics**, and additional monitoring. Here’s the cost breakdown:

- **Data Ingestion (Logs and Metrics)**: $2.30 per GB
- **Custom Metrics**: $0.50 per 100 MB per month (500 metrics use approximately 5 MB)

#### Example Cost Calculation:
- Logs (10 GB x $2.30) = $23
- Custom Metrics (5 MB x $0.50) = $2.50

**Total for Azure Application Insights** = **$25.50 per month**

---

### 2. **Datadog Costs**
Datadog pricing is based on **hosts**, **log ingestion**, **APM (Application Performance Monitoring)**, and **custom metrics**. 

- **Infrastructure Monitoring**: ~$18 per host per month
- **Log Management (Ingestion)**: $0.10 per MB (~$100 per GB)
- **APM**: $31 per host per month
- **Custom Metrics**: ~$5 per 100 custom metrics

#### Example Cost Calculation:
- Infrastructure Monitoring (3 hosts x $18) = $54
- Log Management (10 GB x $100) = $1,000
- APM (3 hosts x $31) = $93
- Custom Metrics (5 units x $5) = $25

**Total for Datadog** = **$1,172 per month**

---

### **Cost Comparison Summary:**

| Service                 | Monthly Cost |
|-------------------------|--------------|
| Azure Application Insights | $25.50       |
| Datadog                 | $1,172       |

---

### Key Takeaway:
With lower usage, **Azure Application Insights** remains more cost-effective compared to **Datadog** due to the high cost of log ingestion and APM in Datadog. For smaller setups or budget-conscious teams, Application Insights can offer significant savings, especially within Azure-hosted environments.

**Custom metrics** are specific data points that a developer or organization chooses to track within their application or infrastructure to gain insights tailored to their needs. Unlike standard metrics (like CPU usage, memory usage, or request count), which are typically monitored by default, custom metrics are defined to monitor unique aspects of a system that are important for specific performance or business goals.

### Examples of Custom Metrics
1. **Application-Specific Metrics**:
   - **User sign-ups**: Tracking the number of users signing up per minute, hour, or day.
   - **Failed transactions**: Monitoring failed transactions to quickly identify issues in a payment processing system.
   - **Cart abandonment**: Tracking the number of users who added items to a cart but didn’t complete the checkout.

2. **Performance Metrics**:
   - **Database query time**: Measuring the time taken for specific database queries.
   - **API response time**: Monitoring the time it takes for certain APIs to respond, particularly critical ones.
   - **Cache hits/misses**: Tracking cache performance to understand if data is being fetched efficiently.

3. **Business Metrics**:
   - **Revenue per user**: Calculating how much revenue is generated per active user in an e-commerce application.
   - **Product usage**: Counting how often certain features or products are used within the app.
   - **Active sessions**: Tracking how many users are actively engaged with the application at any time.

### Benefits of Custom Metrics
- **Tailored Insights**: Provide metrics that align directly with business and application goals.
- **Granular Monitoring**: Allow teams to monitor specific parts of the system that standard metrics might not cover.
- **Early Problem Detection**: Help identify issues in areas of the application that are critical but would otherwise go unnoticed with default metrics.

### Drawbacks of Custom Metrics
- **Increased Cost**: Most monitoring platforms charge for custom metrics separately, often based on the volume of metrics or frequency of collection.
- **Complexity**: Requires identifying, defining, and maintaining relevant metrics, which can add complexity to the monitoring setup.
  
In short, custom metrics give you more control over what you monitor, making them ideal for tracking the unique aspects of your application or business.
