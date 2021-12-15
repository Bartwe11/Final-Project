# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology

The following machines were identified on the network:
- Kali
  - **Kali Linux**:
  - **Attack Machine**:
  - **192.168.1.9**:
- ELK
  - **Linux**:
  - **ELK stack**:
  - **192.168.1.100**:
- Target 1
  - **Linux**:
  - **Target MAchine**:
  - **192.168.1.110**:
- Capstone
  - **Linux**:
  - **Server**:
  - **192.168.1.105**:

### Description of Targets

The target of this attack was: `Target 1` 192.168.1.110

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### Excessive HTTP Errors

Excessive HTTP Errors is implemented as follows:
  - **WHEN count() GROUPED OVER top 5 'http.response.status_code'**
  - **IS ABOVE 400 FOR THE LAST 5 minutes**
  - **Brute Force**
  - **High Reliabilty** 
#### HTTP Request Size Monitor
HTTP Request Size Monitor is implemented as follows:
  - **WHEN sum() of http.request.bytes OVER all documents**
  - **IS ABOVE 3500 FOR THE LAST 1 minute**
  - **DDOS**
  - **Medium Reliabilty** 

#### CPU Usage Monitor
CPU Usage Monitor is implemented as follows:
  - **WHEN max() OF system.process.cpu.total.pct OVER all documents**
  - **IS ABOVE 0.5 FOR THE LAST 5 minutes**
  - **Malicious Software**
  - **High Reliability**


