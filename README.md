
# My Results for first task

## Step 1: Install Nmap
I already had Nmap installed on my system, so I skipped this step.

---

## Step 2: Identify Local IP Range
I used the `ifconfig` command in my Kali Linux WSL to identify my local IP address and network range. Based on this, I found my local IP range was `192.168.29.0/24`.

---

## Step 3: Perform Nmap SYN Scan
I ran the following command:
```bash
nmap -sS 192.168.29.0/24
```
This performed a TCP SYN scan on all devices in my local subnet.

---

## Step 4: Record Live Hosts and Open Ports
From the scan results, I noted all **live hosts** and their corresponding **open ports**. This included common ports like `80`, `443`, `8080`, `8443`, etc.

---

## Step 5: Analyze Packets with Wireshark
I used Wireshark to observe packet behavior during the SYN scan.  
Applied the following display filter:
```wireshark
tcp.flags.syn == 1 && tcp.flags.ack == 1
```
This helped confirm open ports — I specifically observed SYN-ACK responses from `192.168.29.1` on **ports 80 and 8080**, validating my Nmap results.

---

## Step 6: Research Services Running on Open Ports
I researched the services corresponding to the open ports discovered:

- **Port 80 (HTTP)** → Can expose router login panel and is vulnerable to brute-force attacks.
- **Port 1900 (UPnP/SSDP)** → Commonly abused in **malware-based port forwarding** (e.g., Mirai botnet).
- **Ports 8080, 8443** → Alternate HTTP/HTTPS dashboards, often exposed by admin panels or proxies.
- **Port 135 (MSRPC)** → Found on a Windows device, known to be exploited in network-based attacks like WannaCry.

This confirmed that my **router has potential vulnerabilities** and should be hardened (e.g., disabling UPnP, avoiding HTTP access, etc.).

---

## Step 8: Save Results
I saved my Nmap scan results to a text file as instructed, fulfilling the 8th step.

---

