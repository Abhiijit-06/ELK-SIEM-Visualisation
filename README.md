# ELK-SIEM-Visualisation

# Overview

This project demonstrates a basic Security Information and Event Management (SIEM) solution using the Elastic Stack (Elasticsearch, Kibana, and Filebeat) to monitor and analyze SSH authentication events on a Linux system.

The objective of this project is to collect Linux system logs, index them into Elasticsearch, and visualize security events in Kibana through interactive dashboards. As a proof of concept, failed SSH login attempts are generated from a Kali Linux virtual machine and monitored in real time.

# Features
Collects Linux system logs using Filebeat
Sends logs directly to Elasticsearch
Visualizes security events in Kibana
Detects SSH failed login attempts
Displays failed login activity over time
Shows source IP, destination/server IP, and number of SSH login attempts
Demonstrates an end-to-end SIEM workflow


# Architecture
Kali Linux
      │
      ▼
Failed SSH Login Attempts
      │
      ▼
Ubuntu Server (/var/log/auth.log)
      │
      ▼
Filebeat
      │
      ▼
Elasticsearch
      │
      ▼
Kibana Dashboard


# Technologies Used:

Elasticsearch
Kibana
Filebeat
Ubuntu Server
Kali Linux
OpenSSH
Linux System Logs
Dashboards


The project includes visualizations for:

SSH Failed Login Attempts Over Time
SSH Failed Login Attempts by Source and Destination IP
System Log Distribution
Top Processes
Authentication Events

Screenshots are available in the screenshots folder.

# Project Workflow:

Failed SSH login attempts are generated from a Kali Linux VM.
Ubuntu records authentication events in /var/log/auth.log.
Filebeat collects the logs.
Filebeat forwards the logs to Elasticsearch.
Elasticsearch indexes the events.
Kibana visualizes the indexed data using dashboards.


# Repository Structure:

ELK-SIEM
│
├── configs/
├── docs/
├── screenshots/
├── README.md
└── LICENSE
Learning Outcomes

Through this project I learned:

SIEM fundamentals
ELK Stack deployment
Linux log monitoring
Filebeat configuration
Elasticsearch indexing
Kibana dashboard creation
Security event analysis
SSH authentication monitoring


# Future Improvements:

Brute-force attack detection
Email alerts for repeated failed logins
Geo-location visualization of source IPs
Additional Linux security event monitoring
