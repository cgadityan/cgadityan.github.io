---
layout: project
title:  Synthetic Server Data Augmentation for Cyber security Testing
date:   2022-12-01
image:  images/project2/cover.jpg
tags:   server netwrok alerts utility severity router ipaddress
---

*On the cover: Guy working on a Background Server (pinterest)*

I was handed a dataset of server alerts—ranging from CPU utilization spikes to system crashes and various security issues—recorded over a few days. The goal? Generate augmented (synthetic) data that mirrors the underlying patterns of these alerts to improve our cybersecurity testing framework.

Below, I walk you through the journey—from cleaning a messy dataset with inconsistent alert names, system IDs, and irregular time stamps, to selecting an advanced algorithm that truly “gets” the time-dependent nature of our data, and even incorporating an anomaly detection module using Isolation Forest.

## The Challenge: Messy Data and Temporal Complexity
At first glance, the raw dataset was overwhelming. Inconsistencies in alert labels, mismatched system names, and irregular IDs made it clear that thorough data cleaning was the essential first step. Once the dataset was tidied up, the next hurdle emerged: understanding and replicating the inherent time series patterns in these alerts.

Server alerts aren’t just individual points—they come in sequences. The timing between events can stretch or shrink, and it’s crucial that any synthetic data generated captures this temporal structure. Traditional data generation methods might overlook these nuances, which could lead to unrealistic or even misleading test scenarios.

Alert Types: Understanding the Data
Before diving into the synthetic data generation process, it’s essential to understand the range of alert types present in the dataset. Here’s a breakdown of the available alerts:

Interface, DBMS, INSTANCE: Indicators of the health and status of core services and databases.
CPU Load Monitoring, CPU Utilization, CPU: Alerts related to processing power and load management.
Disk, File System Capacity, Mount, InodeMount: These alerts focus on storage health—tracking disk usage, mount points, and filesystem capacities.
Memory: Critical for monitoring system RAM and preventing resource exhaustion.
URL Monitoring, Event Monitoring: Help track external dependencies and internal system events.
Data Protection - Job Failed: Points to issues in backup or data protection routines.
MediaAgents - MediaAgent went Offline, Device Status - Mount Path went Offline: Monitor the status of auxiliary services and connectivity.
Missing Network Mapping for the Remote Site, Remote site connectivity not normal: Highlight network or connectivity issues between different locations.
"Cluster Service Restarting Frequently": Indicates instability in cluster services.
NGT Update Available: Could represent alerts for software or firmware updates.
Each alert provides a unique perspective on the system’s behavior. By analyzing patterns across these diverse categories, we gain a comprehensive view of both normal operations and potential security incidents.

<Insert visual: “Alert Categories Overview” diagram showing a breakdown of these alert types and their interrelations>

## Exploring Generative Approaches
Considering GANs and CTGAN
Initially, I explored using Generative Adversarial Networks (GANs) and even a variant called CTGAN (Conditional GAN for tabular data) for data augmentation. These models have shown promise in generating synthetic data for many applications by “hallucinating” new samples from the existing distribution. However, there was a catch:

Time Series Constraints: While GANs work wonderfully for images and static tabular data, our data is fundamentally a time series. Server alerts have critical timing elements that can’t simply be ignored or treated as independent samples. If the timing is off, the synthetic data loses the sense of “realism” necessary for effective cybersecurity testing.
(For more on CTGAN’s approach to synthetic tabular data, see 
[CTGAN](https://github.com/sdv-dev/CTGAN)
.)

## The Shift to a Hybrid Model: Enter PARNN
Realizing the limitations of pure GAN-based approaches for time series, I began exploring models that blend generative capabilities with robust time series forecasting. This is where Probabilistic AutoRegressive Neural Networks (PARNN) came into play.

PARNN combines traditional autoregressive models with neural network strengths to capture the intricate dependencies in time series data. It’s especially adept at handling:

### Non-stationarity and Nonlinearity: Server alert data can vary dramatically over time.
Temporal Stretching/Shrinking: PARNN can simulate variability in timing—meaning it learns not just what the alerts look like, but also when they occur.
Uncertainty Quantification: It provides prediction intervals that offer a “confidence band” around the generated data, which is critical for realistic testing scenarios.
(For an in-depth look at PARNN’s capabilities, check out 
[PARNN](https://arxiv.org/abs/2204.09640)
.)

## Anomaly Detection with Isolation Forest
In addition to synthetic data generation, our project incorporated an anomaly detection module. Using the Isolation Forest algorithm, we identified and isolated anomalies within the server data. Here’s how we tackled this challenge:

Score Thresholding: Each example was assigned an anomaly score by the Isolation Forest. By closely analyzing the distribution of these scores, we determined a suitable threshold that distinguishes normal events from anomalies.
Dynamic Thresholding: Recognizing that server behavior can vary over time, we also implemented dynamic threshold methods. These methods adjust the threshold value based on the average behavior observed within specific time windows. This adaptive approach helps capture transient changes and ensures the anomaly detection system remains sensitive during periods of both normal operation and potential disruption.

![alt](/images/project2/anomaly.png)
<Insert visual: “Dynamic Threshold Selection vs. Static Threshold” plot showing score distributions over time>

This additional layer of anomaly detection ensures that any unexpected behavior in the server data is promptly flagged for further investigation—providing another critical layer to our cybersecurity testing framework.

Embracing a hybrid model like PARNN allowed us to generate synthetic data that mirrors the patterns of real alerts, while our anomaly detection module using Isolation Forest—with its dynamic thresholding—ensures that unexpected behaviors are swiftly flagged.

This journey underscores the importance of choosing the right tool for the job—especially when dealing with time-sensitive data in critical domains like cybersecurity.




