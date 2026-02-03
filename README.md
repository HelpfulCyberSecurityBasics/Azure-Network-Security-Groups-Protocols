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

- Azure Account and Resource Group Setup: The process begins with ensuring you have an Azure account, preferably a free one, and then creating a dedicated resource group to house all your virtual machines and related resources.
- Virtual Machine Creation (Linux and Windows): The tutorial focuses on deploying two virtual machines: one Linux (Ubuntu) and one Windows. This involves configuring their size, user credentials, and ensuring they are connected to the same virtual network.
- Wireshark Installation and Initial Traffic Inspection: Once the Windows VM is set up, Wireshark is installed to analyze network traffic. The first inspection involves using ICMP (ping) to observe communication between the Windows and Linux machines.
- Network Security Group (NSG) and Traffic Manipulation: The core of the tutorial involves experimenting with NSGs to control and deny specific traffic types (like ICMP) between the VMs. It also demonstrates inspecting SSH, DHCP, DNS, and TCP port traffic using Wireshark.


<h2>Actions and Observations</h2>

<p>
  1. Creating a Resource Group:
- Action: Start by creating a new Resource Group in Azure, naming it "lab to virtual machines."
- Observation: This action establishes the foundational environment for deploying 

</p>
<p>
</p>
<br />

<p>
2. Deploying the Linux Virtual Machine:
- Action: A Linux virtual machine (Ubuntu 22.04) is configured and deployed within the created resource group, with a "lab user" and password.
- Observation: The deployment process begins, and the Linux VM starts appearing within the resource group, indicating successful provisioning.
  <img width="973" height="500" alt="image" src="https://github.com/user-attachments/assets/e2533421-795b-4554-8da2-3eea2c43e957" />

</p>
<p>
</p>
<br />

<p>
3. Deploying the Windows Virtual Machine:
- Action: A Windows 10 Pro virtual machine is configured and deployed in the same resource group and virtual network as the Linux VM, using the same "lab user" and password.
- Observation: The Windows VM deployment also initiates, setting up the second 
<img width="972" height="544" alt="image" src="https://github.com/user-attachments/assets/85d2ceaa-d837-43b7-89d2-c65cad40d72d" />

</p>
<p>
</p>
<br />
4. Installing Wireshark on Windows VM:
- Action: The presenter downloads and installs Wireshark, a network traffic analyzer, directly onto the Windows virtual machine.
- Observation: Wireshark is successfully installed and launched, ready to capture and display network traffic.
<img width="1205" height="401" alt="image" src="https://github.com/user-attachments/assets/98488c67-b718-479a-b5b2-a51a07b64ad5" />
<img width="948" height="421" alt="image" src="https://github.com/user-attachments/assets/8dc44345-9bf1-4813-b3c5-a24059b017d8" />
<img width="549" height="465" alt="image" src="https://github.com/user-attachments/assets/28202b45-0c04-4247-9500-fcff7c2e5d97" />

<br />

5. Observing ICMP Traffic (Ping) between VMs:
- Action: A ping command is executed from the Windows VM to the private IP address of the Linux VM, and Wireshark is used to filter for ICMP traffic.
- Observation: Wireshark clearly displays the ICMP request and reply packets, showing communication between the source (Windows VM) and destination (Linux VM), confirming connectivity.
<img width="1113" height="520" alt="image" src="https://github.com/user-attachments/assets/69bd1f8f-2e92-4493-a6c6-aa21aa621900" />

<br />
<br />
<br />
