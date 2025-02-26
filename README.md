<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project demonstrates the implementation of an on-premises Active Directory (AD) environment within Microsoft Azure Virtual Machines. It covers the deployment and configuration of Active Directory Domain Services (AD DS) using Windows Server 2022 and Windows 10 (21H2) while utilizing technologies such as Remote Desktop, PowerShell, and Azure Compute resources. By following a structured step-by-step approach, this tutorial provides insights into setting up a cloud-hosted AD environment that mirrors traditional on-premises deployments. This project highlights my skills in cloud infrastructure, directory services, and IT administration within a virtualized environment.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Preparing Active-Directory Infrastructure in Microsoft Azure
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<ins>Preparing Active-Directory Infrastructure in Microsoft Azure</ins>

<p>
<img src="https://i.imgur.com/rKSCjWX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Created and deployed a Domain Controller (DC) and a client machine in Microsoft Azure to simulate an on-premises Active Directory environment. I created a Resource Group, set up a Virtual Network and Subnet, and deployed a Domain Controller VM (DC-1) using Windows Server 2022. Additionally, I configured Client-1 (Windows 10), ensuring it was attached to the same region and Virtual Network as DC-1 for proper domain connectivity.
</p>
<br />

<p>
<img src="https://i.imgur.com/NMWmyDE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/4FM0EaH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configured a Virtual Network and Subnet and deployed DC-1 (Windows Server 2022) with a static Private IP to ensure network stability. To test connectivity, I disabled the Windows Firewall on the Domain Controller, allowing seamless communication within the environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
