# NetSentinel – Rogue Device Detection & Network Behavior Profiling

## Overview

**NetSentinel** is a network security monitoring application designed to identify unauthorized devices, monitor network activities, and detect suspicious behavior within a network environment. It helps administrators gain visibility into connected devices, investigate potential security threats, and manage device access through a centralized dashboard.

The system combines device identification, approved-device verification, network behavior profiling, threat alerting, and administrator-controlled actions to support improved network security.

## Problem Statement

Unauthorized devices and suspicious network activities can pose significant security risks to network environments. Traditional network monitoring approaches may not provide a centralized interface for identifying unknown devices, investigating suspicious traffic patterns, and managing access efficiently.

NetSentinel aims to address these challenges by providing a centralized monitoring solution that identifies unknown devices, analyzes network activity for suspicious behavior, and notifies administrators about potential threats.

## Objectives

- Identify devices connected to the monitored network.
- Maintain device information using available network identifiers such as IP and MAC addresses.
- Distinguish approved devices from unknown devices.
- Monitor network traffic and profile device behavior.
- Detect indicators of suspicious activity, including port scanning, DoS-like traffic anomalies, ARP spoofing, and rogue DHCP behavior.
- Generate popup alerts and maintain a notification history.
- Provide administrator workflows for device approval, monitoring, and blocking.
- Maintain device records, security events, and action history.

## Features

### Device Monitoring & Identification
- Detect and display available network device information.
- Track device IP and MAC addresses.
- Maintain a centralized device inventory.

### Rogue Device Detection
- Compare discovered devices against the approved-device list.
- Identify unknown devices.
- Flag unauthorized or unrecognized devices for administrator review.

### Network Behavior Profiling
- Observe network traffic patterns.
- Analyze communication behavior.
- Identify suspicious activity based on configured detection rules.

### Threat Detection
- Port scanning indicators
- DoS-like traffic anomalies
- ARP spoofing indicators
- Rogue DHCP activity

### Device Access Management
- Review unknown devices.
- Approve legitimate devices.
- Initiate blocking actions.
- Maintain device status and administrator action records.

### Notification Management
- Popup notifications for important events.
- Notifications for device detection and security alerts.
- Approval and blocking action notifications.
- Centralized notification history.

### Dashboard
- Centralized network monitoring interface.
- Device inventory and security information.
- Threat alerts and investigation views.
- Network traffic and behavior insights.
- System settings and health information.

## System Architecture

NetSentinel follows a modular architecture consisting of the following components:

1. **Network Monitoring Module** – Observes network traffic and collects available network information.
2. **Device Identification Module** – Extracts device identifiers and maintains device records.
3. **Authorization Verification Module** – Checks discovered devices against the approved-device list.
4. **Behavior Profiling Module** – Examines network activity for unusual communication patterns.
5. **Threat Detection Engine** – Evaluates traffic against configured detection rules.
6. **Notification Module** – Generates and stores security and device-related notifications.
7. **Administrator Control Module** – Supports device approval and blocking workflows.
8. **Database Module** – Stores device records, alerts, notifications, and action history.
9. **Dashboard Module** – Presents monitoring information through a unified interface.

## Technologies Used

- **Python** – Backend processing and network monitoring logic
- **Scapy** – Network packet capture and packet analysis
- **SQLite** – Database for persistent storage
- **HTML, CSS, JavaScript** – User interface development
- **Packet Capture Libraries** – Network traffic capture support, depending on the environment

> Update this section if your implementation uses additional frameworks or libraries.

## Project Workflow

```text
Network Monitoring
       |
       v
Device Identification
       |
       v
Approved Device Verification
       |
       +------ Approved Device ------> Continue Monitoring
       |
       +------ Unknown Device -------> Generate Alert
                                         |
                                         v
                                Behavior Profiling
                                         |
                                         v
                                  Threat Detection
                                         |
                                         v
                                Administrator Review
                                         |
                           +-------------+-------------+
                           |                           |
                        Approve                     Block
                           |                           |
                           v                           v
                     Update Records              Record Action
                           |                           |
                           +-------------+-------------+
                                         |
                                         v
                               Notification History
```

## Detection Capabilities

| Detection module | Purpose |
|---|---|
| Unknown Device Detection | Identifies devices not present in the approved-device list |
| Port Scan Detection | Detects suspicious connection attempts to multiple ports |
| Traffic Anomaly Detection | Identifies unusually high network traffic |
| ARP Anomaly Detection | Detects suspicious IP-to-MAC mapping changes |
| Rogue DHCP Detection | Identifies DHCP responses from unexpected servers |

Detection is based on available network visibility and configured rules. Alerts indicate suspicious activity and may require administrator investigation.


### Prerequisites

- Python 3.x
- Git
- Compatible packet capture support
- Required network monitoring permissions
- Operating system compatible with the project's dependencies

### Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/NetSentinel.git
cd NetSentinel
```

### Install dependencies

If the project contains a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### Run the application

Use the startup command corresponding to the project's configured entry point.

For example, if your backend entry file is `app.py`:

```bash
python app.py
```

> Replace the example commands with the exact installation and startup commands used in your project.

## Testing

The project can be evaluated using the following test scenarios:

- Network monitoring initialization
- Device identification
- Approved device verification
- Unknown device detection
- Port scan detection
- DoS-like traffic anomaly detection
- ARP and DHCP anomaly detection
- Device approval and blocking workflows
- Notification generation and history
- Database persistence

Testing should be performed in an authorized lab environment or using appropriate recorded network traffic.


## Limitations

- Device identification relies on observable network information, which may change or be spoofed.
- Detection accuracy depends on traffic visibility and configured thresholds.
- Packet capture may require elevated permissions and compatible capture drivers.
- Detection of ARP and DHCP anomalies depends on whether the monitoring interface can observe relevant traffic.
- A device status marked as blocked does not guarantee network disconnection unless an actual network enforcement mechanism is integrated and verified.

## Future Enhancements

- Machine learning-based anomaly detection.
- Improved device fingerprinting and identification.
- Adaptive detection thresholds.
- Integration with firewalls and managed switches for verified automated enforcement.
- Advanced network traffic visualizations.
- Enhanced alert severity and filtering.
- Role-based administrator access control.
- Detailed incident reports and analytics.
- Improved scalability for larger networks.

## Contributors

Developed as a course-based project focused on network security monitoring, rogue device detection, and network behavior profiling.

**NetSentinel — Monitor. Detect. Investigate. Secure.**
