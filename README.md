# Mini SOC Wazuh on AWS

## Project Overview

This project demonstrates the deployment of a basic Mini SOC lab using Wazuh on an AWS EC2 instance.

The goal of this project is to monitor a Linux server, collect security logs, detect suspicious activities, and document the results in a professional cybersecurity report.

This lab is designed for learning and portfolio purposes.

---

## What is a SOC?

A SOC, or Security Operations Center, is responsible for monitoring systems, analyzing security events, detecting suspicious activities, and responding to potential cyber threats.

In this project, I created a small SOC-style environment using Wazuh.

---

## Technologies Used

- AWS EC2
- Amazon Linux 2023
- Wazuh
- Linux
- PuTTY
- SSH
- Security Groups
- GitHub Documentation

---

## Project Objectives

The main objectives of this project are:

- Create an AWS EC2 instance for a cybersecurity lab
- Secure remote access using SSH and a key pair
- Configure AWS Security Groups properly
- Verify Linux system resources before installation
- Install Wazuh as a SIEM/XDR platform
- Access the Wazuh Dashboard
- Generate and analyze security alerts
- Document each step with explanations and screenshots

---

## Project Architecture

```text
Analyst / User
     |
     | SSH / HTTPS
     |
AWS EC2 Instance
     |
     | Amazon Linux 2023
     |
Wazuh Server + Wazuh Indexer + Wazuh Dashboard
     |
Security Logs and Alerts
```

---

## Repository Structure

```text
Mini-SOC-Wazuh-AWS/
│
├── README.md
├── installation/
│   └── 01-aws-ec2-setup.md
├── report/
│   └── part1-aws-ec2-setup.md
├── screenshots/
└── .gitignore
```

---

## Part 1 — AWS EC2 Setup

In the first part of this project, an AWS EC2 instance was created and prepared to host the Wazuh Mini SOC lab.

### EC2 Instance Configuration

| Component | Configuration |
|----------|---------------|
| Instance name | Refka-MiniSOC-Wazuh-Server |
| Operating System | Amazon Linux 2023 |
| Architecture | x86_64 |
| RAM | 7.8 GiB |
| Storage | 50 GiB |
| CPU | 2 vCPU |
| Purpose | Host Wazuh server, indexer, and dashboard |

---

## Security Group Configuration

The security group was configured to allow only the required inbound traffic.

| Type | Port | Source | Purpose |
|------|------|--------|---------|
| SSH | 22 | My IP | Remote access using PuTTY |
| HTTPS | 443 | My IP | Access Wazuh Dashboard |

Restricting access to `My IP` reduces the attack surface and prevents public exposure of the server.

---

## SSH Key Pair

A key pair was created to connect securely to the EC2 instance using PuTTY.

The private key was downloaded in `.ppk` format because PuTTY uses this format for SSH authentication.

The private key is not included in this repository for security reasons.

---

## System Verification

After connecting to the EC2 instance, the following commands were used to verify the system:

```bash
cat /etc/os-release
uname -m
free -h
df -h
nproc
```

### Command Explanation

| Command | Purpose |
|--------|---------|
| `cat /etc/os-release` | Check the Linux distribution |
| `uname -m` | Check system architecture |
| `free -h` | Check available RAM |
| `df -h` | Check disk space |
| `nproc` | Check number of CPU cores |

---

## Current Progress

| Part | Description | Status |
|------|-------------|--------|
| Part 1 | AWS EC2 Setup and System Verification | Completed |
| Part 2 | Wazuh Installation | In Progress |
| Part 3 | Wazuh Dashboard Access | Not Started |
| Part 4 | Security Alert Generation | Not Started |
| Part 5 | Final Report and Screenshots | Not Started |

---

## Screenshots

Screenshots will be added in the `screenshots/` folder.

Planned screenshots:

```text
01-aws-instance-configuration.png
02-security-group-rules.png
03-memory-check.png
04-disk-check.png
05-wazuh-installation.png
06-wazuh-dashboard-login.png
07-security-alerts.png
```

Sensitive information such as public IP addresses, passwords, private keys, and AWS account details will be hidden before publishing.

---

## Security Notes

The following information must never be uploaded to GitHub:

- AWS private key files such as `.pem` or `.ppk`
- Wazuh passwords
- AWS Access Key or Secret Key
- AWS Account ID
- Public IP address if not required
- Any secret or credential file

---

## Skills Demonstrated

This project demonstrates the following cybersecurity and cloud skills:

- AWS EC2 deployment
- Linux system administration
- SSH secure access
- Security Group configuration
- Basic cloud security
- SIEM/XDR deployment preparation
- Security documentation
- GitHub project organization

---

## Next Step

The next step is to install Wazuh on the AWS EC2 instance using the official Wazuh installation script.

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
sudo bash ./wazuh-install.sh -a
```

---

## Author

**Refka Kalboussi**  
Cybersecurity Engineering Student  
Interested in SOC, Linux Security, Cloud Security, SIEM, and Threat Detection.