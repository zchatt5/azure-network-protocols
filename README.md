<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. We will also focus on controlling and managing network traffic. Various protocols will be usesd such as ICMP, SSH, DHCP, DNS, and RDP. The protocols will be observed with Wireshark to understand the communication between the Virtual Machines. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>Connect to VMs</h2>

- If using a Mac, install Microsoft Remote Desktop
- Using RDP, connect to the Windows 10 VM
- Install Wireshark withing the Windows 10 VM.
- Open Wireshark to capture incoming packets. 

<h2>Actions and Observations</h2>

**1. Installing Wireshark**
<p>
<img width="1591" height="440" alt="image" src="https://github.com/user-attachments/assets/4887c284-937c-4215-9dbd-89d5fe441c21" />
</p>
<p>
Get the public IP address from your windows 10 Virtual Machine. Open Remote Desktop Protocol and use that IP address to connect to the Virtual Machine. 
</p>
<br />

<p>
<img width="1908" height="994" alt="image" src="https://github.com/user-attachments/assets/1ef516ec-12f8-42be-a353-69f7af59b8cb" />
<img width="1916" height="1037" alt="image" src="https://github.com/user-attachments/assets/9ed36a0d-411f-4c08-a91c-0fbc05858dbc" />
</p>
<p>
Open Microsoft edge or any other browser and go to https://www.wireshark.org/download.html to download wireshark. When Wireshark is opened after installing, select ethernet and start capturing the packets (the sharkfin in the topleft will start the capture).
</p>
<br />

**2. ICMP Traffic**
<p>
<img width="670" height="418" alt="image" src="https://github.com/user-attachments/assets/8c85519e-41b8-436a-9ace-445bc93df688" />
</p>
<p>
In the search/filter bar type "icmp" so only icmp traffic will appear.
</p>
<br />

<p>
<img width="1273" height="862" alt="image" src="https://github.com/user-attachments/assets/82c3741b-1be7-415c-8bd8-60f0bb9a2a50" />
</p>
<p>
Back in Azure in your Mac/Desktop go to the "Linux-VM" and find the private IP address under networking. 
</p>
<br />

<p>
<img width="1782" height="998" alt="image" src="https://github.com/user-attachments/assets/9edbf945-bdb1-43d2-b992-11f00df65af1" />
</p>
<p>
In the Windows Virtual Machine open Powershell. In Powershell type "ping" then use your Linux Virtual Machines private IP. Observe the request and reply traffic in Wireshark.
</p>
<br />

**3. Configure a Firewall (NSG)**
<p>
<img width="1463" height="729" alt="image" src="https://github.com/user-attachments/assets/8ae43ae0-4dce-45a6-87f8-d73272bdd440" />
</p>
<p>
In Powershell start a perpetual ping (ping *IP* -t).
</p>
<br />

<p>
<img width="1871" height="585" alt="image" src="https://github.com/user-attachments/assets/cb4ee129-d187-4c12-b70c-6a5401d4fe95" />
</p>
<p>
Go back into the Azure portal. Go to the Linux-VM -> Networking -> Network Settings -> Click Network Security Group -> Settings -> Inbound security rules. 
</p>
<br />

<p>

</p>
<p>

</p>
<br />

<p>

</p>
<p>

</p>
<br />
