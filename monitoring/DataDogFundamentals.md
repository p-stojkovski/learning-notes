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
