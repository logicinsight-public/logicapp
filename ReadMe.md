# Executive Summary  

The **Logic Insight Appliance** is the next-generation **Nutanix monitoring platform**, designed to provide **deep visibility, near-time analytics, and proactive insights** into Nutanix environments. It offers **advanced metrics collection, improved anomaly detection, and intelligent alerting** to optimize infrastructure performance and ensure operational efficiency.  

Seamlessly integrating with **Nutanix Prism Central** and **Prism Element**, Logic Insight enhances observability by gathering **granular system data** across compute, storage, and networking layers. Powered by **Datadog’s AI-driven analytics engine**, it enables IT teams to **predict potential failures, optimize workloads, and automate issue resolution** before business operations are affected.  

With a focus on **scalability, security, and efficiency**, the **Logic Insight Appliance** empowers organizations to **maximize the value of their Nutanix deployments** through data-driven insights and predictive intelligence.  

## Prerequisites  

This solution supports the following **Nutanix software editions**:  

- **Nutanix Prism AOS** (AOS 6.5+)  
- **Nutanix Prism Central**  

## Minimun Requirements

| CPU | vCPU | RAM | Disk |
|-----|------|-----|------|
|  4  |  1   | 8GB | 50GB |


## Logic Insight Appliance Port Breakdown  

| Port(s) | Protocol | Source | Destination | Service | Description |
|---------|----------|----------------|----------------|----------------|--------------------------------------------|
| 443     | TCP      | LogicApp       | Pulsehub Logic Insight | License | License verification |
| 9440    | TCP      | LogicApp       | Nutanix Prism Central | Prism Central Wizard | TCP communication with Prism Central to add Prism Element Clusters |
| 9440    | TCP      | LogicApp       | Nutanix Prism Element | Nutanix Prism Element Collector | SSL communication between LogicApp and Prism Element APIs |
| 443     | TCP      | LogicApp       | Datadog | Datadog Communication | SSL communication between LogicApp and Datadog Data Ingestion API |
| 443     | TCP      | LogicApp       | AWS | Update Server | Default port where LogicApp retrieves updates. [Update Server](https://logicappupdate.s3.us-east-1.amazonaws.com) |
