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

- Azure Account and Resource Group Setup: If you have not followed the Active Directory training, the process begins with ensuring you have an Azure account, preferably a free one, and then creating a dedicated resource group to house all your virtual machines and related resources.
- Virtual Machine Creation (Linux and Windows): The lab focuses on deploying two virtual machines: one Linux (Ubuntu) and one Windows. This involves configuring their size, user credentials, and ensuring they are connected to the same virtual network.
- Wireshark Installation and Initial Traffic Inspection: Once the Windows VM is set up, Wireshark is installed to analyze network traffic. The first inspection involves using ICMP (ping) to observe communication between the Windows and Linux machines.
- Network Security Group (NSG) and Traffic Manipulation: The core of the lab involves experimenting with NSGs to control and deny specific traffic types (like ICMP) between the VMs. It also demonstrates inspecting SSH, DHCP, DNS, and TCP port traffic using Wireshark.


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
  <p>
</p>
  <br />
  <img width="973" height="500" alt="image" src="https://github.com/user-attachments/assets/e2533421-795b-4554-8da2-3eea2c43e957" />

</p>
<p>
</p>
<br />

<p>
3. Deploying the Windows Virtual Machine:
- Action: A Windows 10 Pro virtual machine is configured and deployed in the same resource group and virtual network as the Linux VM, using the same "lab user" and password.
- Observation: The Windows VM deployment also initiates, setting up the second machine for inter-VM communication and traffic inspection.
  <p>
</p>
  <br />
<img width="972" height="544" alt="image" src="https://github.com/user-attachments/assets/85d2ceaa-d837-43b7-89d2-c65cad40d72d" />

</p>
<p>
</p>
<br />
4. Installing Wireshark on Windows VM:
- Action: The presenter downloads and installs Wireshark, a network traffic analyzer, directly onto the Windows virtual machine.
- Observation: Wireshark is successfully installed and launched, ready to capture and display network traffic.
 <p>
</p>
  <br />
<img width="1205" height="401" alt="image" src="https://github.com/user-attachments/assets/98488c67-b718-479a-b5b2-a51a07b64ad5" />
<img width="948" height="421" alt="image" src="https://github.com/user-attachments/assets/8dc44345-9bf1-4813-b3c5-a24059b017d8" />
<img width="549" height="465" alt="image" src="https://github.com/user-attachments/assets/28202b45-0c04-4247-9500-fcff7c2e5d97" />

<br />

5. Observing ICMP Traffic (Ping) between VMs:
- Action: A ping command is executed from the Windows VM to the private IP address of the Linux VM, and Wireshark is used to filter for ICMP traffic.
- Observation: Wireshark clearly displays the ICMP request and reply packets, showing communication between the source (Windows VM) and destination (Linux VM), confirming connectivity.
 <p>
</p>
  <br />
<img width="1113" height="520" alt="image" src="https://github.com/user-attachments/assets/69bd1f8f-2e92-4493-a6c6-aa21aa621900" />

<br />
6. Blocking ICMP Traffic with a Network Security Group Rule:
- Action: An inbound port rule is created in the Linux VM's network settings to deny ICMP traffic with a high priority.
- Observation: Immediately, the ping commands from the Windows VM start timing out, and Wireshark stops showing ICMP communication, demonstrating the 
 <p>
</p>
  <br />
<img width="1307" height="541" alt="image" src="https://github.com/user-attachments/assets/4bab433b-c198-4e02-8875-074fed383430" />
<img width="1306" height="609" alt="image" src="https://github.com/user-attachments/assets/17487f3d-ba91-40ad-8144-8e165aa35dd3" />
<img width="974" height="622" alt="image" src="https://github.com/user-attachments/assets/da9a490c-3e6a-40e1-9b47-e09b903ab703" />

<br />
7. Inspecting SSH Traffic:
- Action: The presenter uses SSH from the Windows VM to connect to the Linux VM, while Wireshark is configured to filter for SSH traffic.
- Observation: As commands are typed and executed in the SSH session, Wireshark captures and displays the corresponding SSH packets, illustrating the ongoing communication between the two virtual machines.
 <p>
</p>
  <br />
<img width="1076" height="647" alt="image" src="https://github.com/user-attachments/assets/82a2331d-1f71-4163-b364-19c6aeb1c83d" />

<br />
