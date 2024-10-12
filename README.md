<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Create a Windows server VM and another Windows 10 VM; set the Server's IP to a static address and join them on the same virtual network.
- Step 2: Install AD users and computers and promote the server to the domain controller, adding a new forest and giving it a domain name. 
- Step 3: In Active Directory, create new OUs and users and add them to specific security groups.
- Step 4: Join client 1 (the Windows 10 VM) to the domain and give domain users RDP access.
- Step 5: Practice resetting passwords and locking/unlocking accounts.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/7722d16b-b0a1-403d-99e9-2c70cd353126"/>

</p>
<p>
first, create a resource group and a virtual network in the Azure portal. Then, create two virtual machines, one Windows 22 server, and another Windows 10 pro. Make sure they are on the same virtual network. Set the IP address of the server to static. Then set the DNS of the client PC (the Windows 10 VM) to the server's IP address. Once complete, Remote into the server and install AD users and computers. Promote the server to the domain controller and set up a new forest, giving it a domain name. From there, you can create new organizational units and users. I gave some users special rights by adding them to the Administrator's security group. Other accounts I added to the domain users group.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/29ac9d24-5878-4ec1-83e4-87bdbd5c3de2"/>

</p>
<p>
After I logged into the client VM and added it to the domain. This can be done in rename this pc advanced. Once completed, I gave domain users remote access to the desktop on the client's PC. Then, you can go and check in AD on the server to see if the Client has been added to the domain. Next, in the domain controller, I ran a script on PowerShell ISE that added 1000 random new users and used one of them to log in to the client computer remotely. Then I set rules for password lockouts and locked and unlocked a random account created by the script to practice changing passwords in AD
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7e97173c-0c63-4b5b-b68c-dc7b9ad0baa8"/>

</p>
<p>
This project showcases my knowledge of how to use Active Directory. Utilizing Active Directory would be useful for any business running a Windows infrastructure that wants to give access to its employees but keeps some information, such as files in specific directories or computers, separate. It also shows my knowledge of Azure and setting up virtual machines and networks in the cloud. Active Directory is useful in keeping a local network secure, authenticating users, and sharing resources across a network, which are essential in a business environment. 
</p>
<br />
