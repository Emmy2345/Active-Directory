# PROJECT: Secure Remote Desktop (RDP) Implementation
**Date:** January 2026  
**Technologies:** Windows Server 2022, Windows 11, Networking (TCP/UDP), Windows Firewall

---

## 1. Project Objective
To establish a stable and secure remote management path for a Windows Server 2022 instance from a Windows 11 client, ensuring that administrative tasks could be performed without direct physical access to the server hardware.

## 2. Implementation Steps
1. **Enabling the Protocol:** Navigated to System Properties to allow remote connections.
2. **User Access Control:** Manually added specific user accounts to the 'Remote Desktop Users' group to satisfy security requirements.
3. **Network Identification:** Assigned a static IP to the server to ensure the client always has a consistent target.
4. **Port Management:** Configured port forwarding on the gateway to route traffic on Port 3389 directly to the server's internal address.

---

## 3. Troubleshooting & Solutions

### The "Public" Profile Obstacle
**Issue:** The server was invisible to the network even though RDP was enabled.
**Discovery:** Windows had categorized the network connection as "Public," which automatically blocks most inbound traffic (including RDP) for security.
**Fix:** I used PowerShell to force the network profile to "Private," which opened the necessary communication channels for a local lab environment.
`Set-NetConnectionProfile -InterfaceIndex [Index] -NetworkCategory Private`

### Firewall Deadlocks
**Issue:** Even on a private network, the connection was being dropped by the server.
**Solution:** I deep-dived into Windows Defender Firewall Advanced Security. I found that the default RDP rules were restricted. I manually verified and enabled the Inbound Rules for:
* Remote Desktop - User Mode (TCP-In)
* Remote Desktop - User Mode (UDP-In)



### Credential & Service Issues
**Issue:** "The credentials did not work" or "An internal error occurred."
**Solution:** * **NLA:** I temporarily disabled Network Level Authentication (NLA) to rule out encryption mismatches between the two different Windows versions.
* **Service Reset:** Restarted the 'Remote Desktop Services' via `services.msc` to clear a hung state where the service was "Running" but not responding to requests.

---

## 4. Final Result
The connection was verified using the `Test-NetConnection` tool. The result confirmed `TcpTestSucceeded : True`, indicating a perfect handshake between the client and server. The server is now fully accessible for headless administration.
