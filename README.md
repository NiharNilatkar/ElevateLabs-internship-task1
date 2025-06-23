# ElevateLabs-internship-task1
**Results for first task**
I already had nmap downloaded, skipped the first step.
For the 2nd step, I ran the command ifconfig in order to discover my local ip range. I sucessfully noted my IP and proceeded towards next step
For the 3rd step, in my kali-linux wsl, I ran nmap scan on 192.168.29.0/24 which was my local ip range. I got the results sucessfully and saved them to a text file which covers my 8th step as well.
Based on my nmap scan results, I noted all open ports and live hosts that I found on my scan.
For the 5th step, I used Wireshark to analyze SYN scan behavior. Applied tcp.flags.syn == 1 && tcp.flags.ack == 1 filter to confirm open ports. Observed SYN-ACK responses from 192.168.29.1 on ports 80 and 8080, validating Nmap results
In the 6th step, I researched about the common services running on the ports that I scanned. Most common were HTTP,HTTPS,HTTP-proxy services.
I further research that one of the open ports on my router was port 80 which is used by HTTP. On researching, I got to know that it can be exploited for brute force login attacks on router. I also got to know that open port 1900 on my router, is often used for malware-based port forwarding attacks, confirming that my rouoter is vulnerable.

