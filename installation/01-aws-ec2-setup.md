# 01 — AWS EC2 Setup

## Objective

The objective of this step is to create and prepare an AWS EC2 instance that will host the Wazuh Mini SOC lab.

This instance will be used to install the following Wazuh components:

- Wazuh server
- Wazuh indexer
- Wazuh dashboard

---

## 1. Create an EC2 Instance

Go to:

```text
AWS Console → EC2 → Instances → Launch Instance
```

---

## 2. Instance Name

Set the instance name to:

```text
Refka-MiniSOC-Wazuh-Server
```

### Why?

This name clearly identifies:

- the owner of the project
- the type of lab
- the tool used
- the role of the machine

---

## 3. Choose the Operating System

Select:

```text
Amazon Linux 2023
```

### Why?

Amazon Linux 2023 is suitable for AWS cloud labs and Linux-based security tools.

---

## 4. Choose the Instance Type

Select an instance with enough resources for Wazuh.

In this lab, the instance used had:

```text
RAM: 7.8 GiB
CPU: 2 vCPU
```

### Why?

Wazuh needs enough memory and CPU because it runs multiple services at the same time.

---

## 5. Create a Key Pair

Create a new key pair:

```text
Key pair name: Refka-MiniSOC-KeyPair
Key type: RSA
Private key format: .ppk
```

### Why?

The `.ppk` format is used because PuTTY requires this format to connect to the EC2 instance.

### Security Note

The private key must never be uploaded to GitHub.

---

## 6. Configure the Security Group

Create a security group named:

```text
Refka-MiniSOC-Wazuh-SG
```

Add the following inbound rules:

| Type | Port | Source | Purpose |
|------|------|--------|---------|
| SSH | 22 | My IP | Connect using PuTTY |
| HTTPS | 443 | My IP | Access Wazuh Dashboard |

### Why?

SSH is required to connect to the server.

HTTPS is required to access the Wazuh Dashboard from the browser.

Both ports are restricted to `My IP` to reduce exposure.

---

## 7. Configure Storage

Set the storage size to:

```text
50 GiB
```

### Why?

Wazuh stores logs, alerts, and indexed security data, so more disk space is required.

---

## 8. Launch the Instance

After verifying the configuration, click:

```text
Launch Instance
```

Wait until the instance state becomes:

```text
Running
```

---

## 9. Connect to the Instance Using PuTTY

Open PuTTY and use the following format:

```text
ec2-user@<EC2_PUBLIC_IP>
```

Then select the private key:

```text
Refka-MiniSOC-KeyPair.ppk
```

If the connection is successful, the Linux terminal will appear.

Example:

```bash
[ec2-user@ip-xxx-xxx-xxx-xxx ~]$
```

---

## 10. Verify the System

Run the following commands:

```bash
cat /etc/os-release
uname -m
free -h
df -h
nproc
```

---

## 11. Command Explanation

| Command | Purpose |
|--------|---------|
| `cat /etc/os-release` | Check the Linux version |
| `uname -m` | Check system architecture |
| `free -h` | Check memory/RAM |
| `df -h` | Check disk space |
| `nproc` | Check number of CPU cores |

---

## 12. Results

| Check | Result |
|------|--------|
| Operating System | Amazon Linux 2023 |
| Architecture | x86_64 |
| RAM | 7.8 GiB |
| Disk | 50 GiB |
| CPU | 2 vCPU |

---

## 13. Conclusion

The AWS EC2 instance was successfully created and verified.

The server is now ready for the next step: installing Wazuh.