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

- Step 1: Create virtual machines ( 1 windows, 1 linux), must be in the same network.
- Step 2: Install wireshark, observe ICMP, SSH, RDP, DHCP, and DNS traffic.
- Step 3:Configure Firewall (Network Security Group)

  
<h2>Lab Prerequisets</h2>
<p>
<img width="849" alt="image" src="https://github.com/user-attachments/assets/af763d83-8846-435d-bafa-280312109acf" />
</p>

  - Step 1: VM's must be in the same resource group
- Step 2: VM's must be in the same virtual network
- Step 3: Note -> Windows uses RDP, Linux uses SSH to connect to remote clients.

<h2>Actions and Observations</h2>

<p>
<img width="918" alt="image" src="https://github.com/user-attachments/assets/4fed5d3f-ed49-4cad-8691-ac2bb71d7c78" />
<img width="847" alt="image" src="https://github.com/user-attachments/assets/b6a83238-afee-41f0-9fc9-ee104cb7abf1" />
<img width="948" alt="image" src="https://github.com/user-attachments/assets/d67d6dd3-4014-4750-881d-68879e6fb698" />

</p>

  - Step 1: install wiresahrk from Wireshark.org, in this case we download the windows versions and keep all defaults and install
- Step 2: open wirshark an choose ethernet option
- Step 3: wireshark is recieving traffic, search bar used to isolate traffic such as icmp, dns, dhcp, etc.
  
<p>
<img width="958" alt="image" src="https://github.com/user-attachments/assets/153285ed-ff0b-4f7a-805c-eb6945fd59ad" />
<img width="959" alt="image" src="https://github.com/user-attachments/assets/47c68b2e-93ab-4def-927e-a92b0f8d727a" />

</p>

- In this case, search ICMP, no traffic will be displayed yet
- Obtain the PRIVATE IP address of the linux vm and ping, request and reply icmp packets will be displayed
- You can do the same with pinging a website, connection can be confirmed with a "0% loss" reply.
  
<br />

<p>
<img width="946" alt="image" src="https://github.com/user-attachments/assets/d7ad0903-5bc2-44dd-b85d-bd3746dbd386" />
<img width="932" alt="image" src="https://github.com/user-attachments/assets/51b12f83-0d82-4e42-ab18-69507e881edc" />
<img width="928" alt="image" src="https://github.com/user-attachments/assets/61619c52-3452-4ed6-ad1d-b92cc2f9ada0" />
<img width="694" alt="image" src="https://github.com/user-attachments/assets/741542ef-6df1-4093-98b9-12d6100e82e3" />

</p>

- We can do the same for other protocols such as, ssh, dhcp, dns, and rdp traffic as show in the images above.
- Note: for ssh on the linux vm you will need the command : <ssh username@privateipaddress>
- Note: rdp traffic is continuos because remote connection is live.
<p>
