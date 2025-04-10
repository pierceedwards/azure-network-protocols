<p align="center">
  <img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1 align="center">Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>

<p align="center">
  This tutorial explores the use of Network Security Groups and Wireshark to analyze traffic between Azure Virtual Machines across various protocols.
</p>

---

## 🧰 Environments and Technologies Used

- **Microsoft Azure** – Virtual Machines and Networking  
- **Remote Desktop Protocol (RDP)**  
- **Wireshark** – Network Protocol Analyzer  
- **Command-Line Tools** – Ping, SSH, etc.  
- **Network Protocols** – ICMP, SSH, RDP, DNS, DHCP, HTTP/HTTPS

## 💻 Operating Systems Used

- **Windows 10 (21H2)**
- **Ubuntu Server 20.04**

---

## 🔄 High-Level Steps

1. Create two VMs (Windows + Linux) in the same virtual network
2. Install and use Wireshark to observe network traffic
3. Configure and test Network Security Group (NSG) rules

---

## 📅 Lab Prerequisites

![Lab Prerequisites](https://github.com/user-attachments/assets/af763d83-8846-435d-bafa-280312109acf)

- Both VMs must be in the **same resource group**
- Both VMs must reside in the **same virtual network**
- Use **RDP for Windows VM** and **SSH for Linux VM** to connect

---

## 🚀 Actions and Observations

### Step 1: Install Wireshark on Windows VM

- Download from [Wireshark.org](https://www.wireshark.org/)
- Use default settings during installation
- Open Wireshark and select your network interface (usually **Ethernet**)

![Wireshark Setup](https://github.com/user-attachments/assets/4fed5d3f-ed49-4cad-8691-ac2bb71d7c78)  
![Wireshark Interface](https://github.com/user-attachments/assets/b6a83238-afee-41f0-9fc9-ee104cb7abf1)  
![Traffic Filters](https://github.com/user-attachments/assets/d67d6dd3-4014-4750-881d-68879e6fb698)

---

### Step 2: Analyze ICMP (Ping) Traffic

- Use filter: `icmp`
- No traffic appears until a ping is sent
- From Windows VM, ping the Linux VM using its **private IP**:

### Step 3: Analyze Other Protocols

Observe different types of traffic:
- SSH (Linux VM):
- ssh username@10.0.0.5
- RDP (Windows VM): Traffic is continuous due to active remote session
- DNS: Occurs when resolving hostnames
- DHCP: Observe during VM startup or IP refresh


### 🧪 Final Notes

- Wireshark is a powerful tool to observe live traffic and verify communication between systems
- NSGs can be tested by allowing/blocking specific ports to observe effect on traffic
- Filtering traffic (e.g., icmp, dns) makes protocol analysis simpler and more efficient

