---

## Wazuh Agent Deployment

The Wazuh Agent is installed on the Windows 10 endpoint to collect security events and forward them to the Wazuh Manager.

### Network Configuration

The Wazuh Manager is hosted on the Ubuntu Server:

```text
Wazuh Manager: 192.168.5.233
Endpoint: Windows 10 VM
```

Connectivity was verified from the Windows endpoint:
```bash
ping 192.168.5.233
```
<img width="571" height="341" alt="image" src="https://github.com/user-attachments/assets/b747b80d-e920-49db-a486-8882647c8b3d" />

### Access Wazuh Dashboard

Open the Wazuh Dashboard from the Windows host using the Ubuntu Server IP:
```text
https://<wazuh-manager-ip-address>
https://192.168.5.233
```
Log in using the configured Wazuh administrator credentials.
<img width="1887" height="678" alt="image" src="https://github.com/user-attachments/assets/692e09e6-aa5a-4e86-963b-5e571f635964" />


### Deploy Wazuh Agent

Navigate to:

Agents → Deploy new agent

Configure the agent:

```text
Operating System: Windows
Architecture: x86_64
Server Address: 192.168.5.233
Agent Name: Windows10-Endpoint
```
The dashboard provides the installation command for the selected configuration.

Install the Agent

Run the generated installation command in PowerShell as Administrator on the Windows 10 endpoint.

Start the Wazuh Agent
```bash
Start-Service WazuhSvc
```
Verify the service:
```bash
Get-Service WazuhSvc
```
The service should show a Running status.

Agent Verification

Return to:

Wazuh Dashboard → Agents

The Windows10-Endpoint should appear with an Active status, confirming successful communication with the Wazuh Manager.
<img width="840" height="386" alt="image" src="https://github.com/user-attachments/assets/43eb02d5-1b89-4543-a0d5-03b5bbd17c6a" />

