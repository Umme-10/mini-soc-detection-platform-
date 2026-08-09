# Initial Setup

This document covers the initial setup required to prepare the SOC server for deploying the Mini SOC Detection & Response Platform.

---

## Lab Environment

| Component | Configuration |
|----------|---------------|
| Hypervisor | VMware Workstation |
| Host OS | Windows 10 |
| SOC Server | Ubuntu Server 24.04 LTS |
| Attacker VM | Kali Linux |
| Endpoint VM | Windows 10 |
| Endpoint VM | Ubuntu Desktop |
| RAM | 32 GB (Host) |
| Network | NAT |

---

## Ubuntu Server Installation

### VM Configuration

| Resource | Value |
|---------|-------|
| CPU | 4 vCPUs |
| Memory | 8 GB |
| Storage | 20 GB |
| Network Adapter | NAT |

Install Ubuntu Server using the default installation options and create a non-root user.
<img width="514" height="290" alt="image" src="https://github.com/user-attachments/assets/5d47e455-9dd2-4204-b686-2e52afb78273" />

---
## Enable Remote Access (SSH)

Install the OpenSSH server (if not already installed).

```bash
sudo apt update
sudo apt install openssh-server -y
```
Verify the SSH service is running.

```bash
sudo systemctl status ssh
```

Find the server IP address.

```bash
ip a
```

From the Windows host, connect to the Ubuntu Server using PowerShell or Windows Terminal.

```powershell
ssh <username>@<server-ip>
```

Example:

```powershell
ssh umme@192.168.5.232
```

Verify the connection by logging in successfully and accessing the Ubuntu Server terminal from the Windows host.
## System Update

Update the operating system.

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Install Required Packages

```bash
sudo apt install curl wget git unzip net-tools tree -y
```

Verify the installation.

```bash
git --version
curl --version
```

---

## Install Docker

Download and run the official Docker installation script.

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Add the current user to the Docker group.

```bash
sudo usermod -aG docker <username>
newgrp docker
```

---

## Verify Docker Installation

```bash
docker --version
docker compose version
docker run hello-world
```

Expected result:

- Docker Engine installed successfully.
- Docker Compose available.
- `hello-world` container executes successfully.
<img width="587" height="386" alt="image" src="https://github.com/user-attachments/assets/5cef6401-c1a5-40a8-83a5-49d8a4f25859" />

---


---

## Wazuh Deployment

Wazuh is deployed as a single-node environment using Docker Compose. The deployment includes the Wazuh Manager, Wazuh Indexer, and Wazuh Dashboard.

### Clone Wazuh Docker Repository

```bash
cd ~
git clone -b v4.14.6 https://github.com/wazuh/wazuh-docker.git
cd wazuh-docker/single-node
```
### Deployment Verification

Verify that all Wazuh services are running:

```bash
docker compose ps
```

<img width="1919" height="855" alt="image" src="https://github.com/user-attachments/assets/87c48607-ddfc-41ee-a2b4-ea01056a09fe" />

