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
- Deploying Active Directory
- Creating Users with Powershell
- Group Policy and Managing Accounts

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
<img src="https://i.imgur.com/4FM0EaH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configured a Virtual Network and Subnet and deployed DC-1 (Windows Server 2022) with a static Private IP to ensure network stability. To test connectivity, I disabled the Windows Firewall on the Domain Controller, allowing seamless communication within the environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/IzE5Rrk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the VM, I set Client-1’s DNS settings to DC-1’s Private IP address to enable proper domain communication. I then restarted Client-1 from the Azure Portal to apply the new network configuration. Once the restart was complete, I logged into Client-1 to verify connectivity with the Domain Controller. This step ensured that Client-1 could properly resolve domain resources and communicate within the Active Directory environment in Azure.
</p>
<br />

<p>
<img src="https://i.imgur.com/SNtq8bT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Attempted to ping DC-1’s Private IP address from Client-1 to test network connectivity. The ping request succeeded, confirming that Client-1 could communicate with the Domain Controller. This verified that the network configuration, including the Virtual Network, Subnet, and DNS settings, was correctly set up. Ensuring successful connectivity was a crucial step in establishing a fully functional Active Directory environment in Azure.
</p>
<br />

<p>
<img src="https://i.imgur.com/CQRUuGR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From Client-1, I opened PowerShell and ran the command ipconfig /all to verify the network configuration. The output confirmed that DC-1’s Private IP address was correctly set as the DNS server. This validation ensured that Client-1 was properly configured to communicate with the Domain Controller for domain-related services. Verifying the DNS settings was a critical step in ensuring a stable and functional Active Directory environment in Azure.
</p>
<br />

<ins>Deploying Active Directory</ins>

<p>
<img src="https://i.imgur.com/PNCVwz8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Logged into DC-1 and installed Active Directory Domain Services (AD DS) to enable domain management. After installation, I promoted DC-1 to a Domain Controller by setting up a new forest with the domain mydomain.com. Once the configuration was complete, I restarted DC-1 and logged back in as mydomain.com\labuser to verify the setup. This step ensured that the domain was successfully established and ready for managing authentication and network resources.
</p>
<br />

<p>
<img src="https://i.imgur.com/aHjKQe6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers (ADUC), I created two Organizational Units (OUs) named "_EMPLOYEES" and "_ADMINS" to organize user accounts. I then added a new employee, Jane Doe, with the username "jane_admin" and assigned the password Cyberlab123!. To grant administrative privileges, I added jane_admin to the "Domain Admins" Security Group, giving her elevated permissions. After completing the setup, I logged out of DC-1 and logged back in as "mydomain.com\jane_admin", establishing this account as the primary administrator for the domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/6vy6rbb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Logged into Client-1 as the local administrator (labuser) and joined it to the domain, triggering an automatic restart. After the restart, I logged into the Domain Controller (DC-1) and verified that Client-1 appeared in Active Directory Users and Computers (ADUC) as part of the domain. To better organize devices, I created a new Organizational Unit (OU) named "_CLIENTS". Finally, I moved Client-1 into the "_CLIENTS" OU, ensuring a structured and manageable domain environment.
</p>
<br />

<ins>Creating Users with Powershell</ins>

<p>
<img src="https://i.imgur.com/aKMXvpq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Logged into Client-1 as the local administrator (labuser) and joined it to the domain, which prompted a system restart. After the restart, I verified in Active Directory Users and Computers (ADUC) on DC-1 that Client-1 was successfully added to the domain. To keep the environment organized, I created a new Organizational Unit (OU) named "_CLIENTS" and moved Client-1 into it.
</p>
<br />

<p>
<img src="https://i.imgur.com/A8p6k65.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Opened PowerShell ISE as an administrator, created a new script file, and pasted the contents of a prebuilt script designed to generate user accounts. After running the script, I observed the automatic creation of multiple user accounts in Active Directory. I then opened Active Directory Users and Computers (ADUC) to verify that the accounts were correctly placed in the "_EMPLOYEES" Organizational Unit (OU).
</p>
<br />

<p>
<img src="https://i.imgur.com/wsOFIAo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To confirm functionality, I attempted to log into Client-1 using one of the newly created accounts, ensuring the credentials from the script were working properly.
</p>
<br />

<ins>Group Policy and Managing Accounts</ins>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
