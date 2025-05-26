🔍 Network Port Scanner & Risk Identifier

This project uses nmap to scan a local network for open TCP ports and helps identify potential security risks based on discovered services.

📌 Project Objective

To scan all active devices on the local network, detect open TCP ports, identify common services, and evaluate possible security vulnerabilities.

🛠️ Tools Used

Nmap — powerful network discovery and security auditing tool

macOS Terminal (or Linux shell)

Local network access

📸 Screenshots

1. Downloading Nmap



Download Nmap from the official site:🔗 https://nmap.org/download

2. Scanning Local Network with TCP SYN Scan



This command scans all devices on your subnet and checks for open TCP ports using a SYN scan.

📋 Step-by-Step Usage

✅ Step 1: Install Nmap

Go to nmap.org/download and install the correct version for macOS.

✅ Step 2: Identify Your Local IP Range

Run:

ifconfig

Look for your IP (e.g., 192.168.1.X) and infer the subnet, usually /24. Example:

192.168.1.0/24

✅ Step 3: Perform a TCP SYN Scan

sudo nmap -sS 192.168.1.0/24

This scans all hosts in the network and detects which TCP ports are open.

✅ Step 4: Record IPs and Open Ports

Note devices that are up and which ports are open.

✅ Step 5: Identify Services Running on Ports

Use nmap -sV to detect service versions:

sudo nmap -sV 192.168.1.X

Then research the services on common ports (e.g., SSH, HTTP, SMB, etc.).

✅ Step 6: Analyze Potential Security Risks

Ask:

Is this port necessary?

Is the service outdated?

Is it encrypted?

Is it exposed beyond the local network?

Example:

Port 445/tcp (SMB) is a common attack vector. Disable it if not used.

✅ Step 7: Save Scan Results

Save the output:

nmap -sS 192.168.1.0/24 -oN scan-results.txt

Or save in HTML format (requires a script or post-processing).

⚠️ Security Reminder

Only scan networks you own or have permission to audit. Unauthorized scanning is illegal and unethical.

📂 License

This project is licensed under the MIT License.

🙌 Acknowledgements

Nmap Documentation

Exploit Database
