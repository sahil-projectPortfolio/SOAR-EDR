# SOAR-EDR PROJECT

## Overview
This project is a Security Orchestration, Automation, and Response (SOAR) solution with Endpoint Detection and Response (EDR) capabilities. It integrates **LimaCharlie**, **Tines**, and **Slack** to create an automated incident detection and response workflow, helping organizations respond to security threats efficiently and in real-time. The primary goal of this project is to demonstrate automated alerting and incident management for potential security incidents.

### Key Platforms/Technologies
- **LimaCharlie**: For real-time detection and monitoring of host endpoints.
- **Tines**: As a no-code orchestration platform to automate incident responses based on alerts from LimaCharlie.
- **Slack**: For real-time alert notifications sent directly to security channels.

## Project Objectives
- **Automated Detection**: Automatically detect potential threats using LimaCharlie agents on monitored endpoints.
- **Orchestrated Response**: Use Tines to automate incident response workflows based on detected threats.
- **Efficient Notification**: Send real-time alerts to designated Slack channels for quick visibility by the security team.
- **Reduced Response Time**: Enable faster incident response with automated and orchestrated workflows.

## Features
- **Real-Time Endpoint Monitoring**: Deploy LimaCharlie agents to monitor and collect telemetry from endpoints in real-time.
- **Automated Incident Response**: Use Tines to automate responses to incidents detected by LimaCharlie, reducing manual intervention.
- **Slack Alerts**: Receive real-time alerts in Slack for immediate visibility and response to security threats.

### Prerequisites
1. **AWS Account** (if deploying on EC2) **/ Oracle VirtualBox**: Windows Server or Linux installed on it.
2. **LimaCharlie Account**: [Sign up here](https://limacharlie.io).
3. **Tines Account**: [Sign up here](https://www.tines.com).
4. **Slack Workspace**: [Create or sign in here](https://slack.com).
5. Basic knowledge of API integrations and workflows.

