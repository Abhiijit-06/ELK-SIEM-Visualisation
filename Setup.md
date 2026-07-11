# ELK SIEM Setup Guide

## Prerequisites

- Ubuntu Server
- Docker
- Internet Connection
- Kali Linux VM (for SSH testing)

---

## Components Used

- Elasticsearch
- Kibana
- Filebeat
- OpenSSH Server

---

## Project Workflow

Kali Linux → SSH Failed Login → Ubuntu (/var/log/auth.log) → Filebeat → Elasticsearch → Kibana Dashboard

---

## Installation Steps

### 1. Install Docker

Install Docker on Ubuntu and verify it is running.

### 2. Deploy Elasticsearch

Run the Elasticsearch container and expose port **9200**.

### 3. Deploy Kibana

Run the Kibana container and expose port **5601**.

### 4. Install Filebeat

Install Filebeat on the Ubuntu server.

### 5. Configure Filebeat

- Enable the **filestream** input.
- Monitor:
  - `/var/log/syslog`
  - `/var/log/auth.log`
- Configure Elasticsearch as the output.
- Configure Kibana for dashboard setup.

### 6. Start Services

Start:
- Elasticsearch
- Kibana
- Filebeat

Verify that all services are running correctly.

---

## Generating Security Events

From the Kali Linux VM:

1. Connect to the Ubuntu server using SSH.
2. Enter an incorrect password multiple times.
3. The failed authentication attempts are recorded in `/var/log/auth.log`.
4. Filebeat forwards these logs to Elasticsearch.

---

## Viewing Logs

Open Kibana and:

- Navigate to **Discover**
- Select the Filebeat data view
- View SSH authentication events

---

## Dashboard

The dashboard includes:

- Number of Events
- Top Processes
- Event Dataset Distribution
- SSH Failed Login Attempts
- SSH Login Attempts by Source and Destination IP

---

## Learning Outcomes

- ELK Stack deployment
- Filebeat configuration
- Linux log monitoring
- Elasticsearch indexing
- Kibana visualization
- Basic SIEM implementation
- SSH failed login monitoring

---

## Future Improvements

- Brute-force attack detection
- Email alerting
- Geo-location of attacker IP addresses
- Additional Linux security event monitoring
