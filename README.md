**Network Port Scanner & Risk Identifier**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
This project uses nmap to scan a local network for open TCP ports and helps identify potential security risks based on discovered services.


**Project Objective**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
To scan all active devices on the local network, detect open TCP ports, identify common services, and evaluate possible security vulnerabilities.


**Tools Used**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Nmap — powerful network discovery and security auditing tool
2. macOS Terminal (or Linux shell)
3. Local network access


**📸 Screenshots**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**1. Download Nmap from the official site:🔗 https://nmap.org/download**

<img width="1429" alt="Screenshot 2025-05-26 at 13 32 51" src="https://github.com/user-attachments/assets/bdbe34d3-8c08-4359-8e84-35151d371d59" />

**2. Scanning Local Network with TCP SYN Scan**

<img width="784" alt="Screenshot 2025-05-26 at 12 43 15" src="https://github.com/user-attachments/assets/a526e30f-9286-412d-9c57-90729dbd2c15" />

This command scans all devices on your subnet and checks for open TCP ports using a SYN scan.


**Step-by-Step Usage**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**Step 1: Install Nmap**
Go to nmap.org/download and install the correct version for macOS.

**Step 2: Identify Your Local IP Range**
Run: ifconfig
Look for your IP (e.g., 192.168.1.X) and infer the subnet, usually /24. Example: 192.168.1.0/24

**Step 3: Perform a TCP SYN Scan**
sudo nmap -sS 192.168.1.0/24
This scans all hosts in the network and detects which TCP ports are open.

**Step 4: Record IPs and Open Ports**
Note devices that are up and which ports are open.

**Step 5: Identify Services Running on Ports**
Use nmap -sV to detect service versions:
sudo nmap -sV 192.168.1.X
Then research the services on common ports (e.g., SSH, HTTP, SMB, etc.).

**Step 6: Analyze Potential Security Risks**
| Risk                          | Likelihood        | Severity            | Mitigation                     |
| ----------------------------- | ----------------- | ------------------- | ------------------------------ |
| Unauthorized AirPlay use      | Medium (LAN only) | Medium              | Enable authentication          |
| Known AirPlay vulnerabilities | Low to Medium     | High (if exploited) | Update device firmware         |
| Information disclosure        | High              | Low                 | Acceptable, minimal impact     |
| Network reconnaissance        | Medium            | Medium              | Firewall, network segmentation |


**Step 7: Save Scan Results**
Save the output:
nmap -sS 192.168.1.0/24 -oN scan-results.txt


**License**
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
This project is licensed under the MIT License.
