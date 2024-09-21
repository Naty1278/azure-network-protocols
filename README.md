<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resources
- Observe ICMP and SSH Traffic 
- Observe DHCP and DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<p>
<img width="1235" alt="Screen Shot 2024-09-21 at 4 21 02 PM" src="https://github.com/user-attachments/assets/ea248a21-2603-49cd-ad48-2ee0ca3cfba8">
</p>
<p>
In Azure created a resource group and two virtual machines, one using Linux machine and other using Windows 10 Pro. 
</p>
<br />

<p>
<img width="1345" alt="Screen Shot 2024-09-21 at 5 31 20 PM" src="https://github.com/user-attachments/assets/b70f289d-11a6-43d2-9357-773a199ad56b">
</p><img width="1140" alt="Screen Shot 2024-09-21 at 6 01 18 PM" src="https://github.com/user-attachments/assets/868d6531-5222-4ddd-8fa4-0e8936e01024">

In Windows VM, opened up Powershell and Wireshark. Filtered for ICMP (Internet Control Message Protocol) in Wireshark and pinged Linux VM private IP address in Powershell and observed network traffic. In second image filtered for Linux Ubuntu SSH (Secure Shell) traffic spam on the Windows VM. 
</p>
<br />

<p>
<img width="1393" alt="Screen Shot 2024-09-21 at 6 21 15 PM" src="https://github.com/user-attachments/assets/8595664f-3b23-47df-860e-43f69cc28c37">
</p><img width="1153" alt="Screen Shot 2024-09-21 at 7 16 27 PM" src="https://github.com/user-attachments/assets/3b412aae-cd73-4a8e-8342-4a7e058439b5">

<p>
In Azure filtered for DHCP Dynamic Host Configuration Protocol traffic only and attempted to issue a new IP address for Windows VM. In Wireshark filtered for DNS (Domain Name System) traffic only and conducted an nslookup for web addresses like disney.com and google.com. 
<img width="1377" alt="Screen Shot 2024-09-21 at 7 26 14 PM" src="https://github.com/user-attachments/assets/bd04f727-bb62-4d22-b47f-c5a1aa701a91">

<br /> In Wireshark filtered for RDP (tcp.port == 3389) and observed non-stop spam of traffic. RDP protocol constantly shows live stream from one computer to another. 
