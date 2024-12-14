<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial showcases my knowledge of on-premises Active Directory within Azure Virtual Machines.<br />


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
- First, a resource group and a virtual network should be created in the Azure portal. Then, create two virtual machines, one Windows 22 server and another Windows 10 pro. Make sure they are on the same virtual network. Set the server's IP address to a static address. 
<p>
- Then, the DNS of the client PC (the Windows 10 VM) is set to the server's IP address. Once complete, Remote desktop into the server and install AD users and computers.
</p>
<p>
- Promote the server to the domain controller and set up a new forest, giving it a domain name. 
</p>
<p>
- From there, you can create new organizational units and users. I gave some users special rights by adding them to the Administrator's security group. Other accounts I added to the domain users group.
</p>
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/29ac9d24-5878-4ec1-83e4-87bdbd5c3de2"/>

</p>
<p>
- Log into the client VM and add it to the domain; this can be done in system -> rename this PC -> advanced. Once completed, give domain users remote access to the desktop on the client's PC. 
<p>
- Then, you can check in AD on the server to see if the Client has been added to the domain. Next, in the domain controller, I ran a script on PowerShell ISE that added 1000 random new users. 
<p>
- Log in to the client computer remotely using one of the accounts created. 
</p>
<p>
- Then, I set rules for password lockouts by configuring group policy. To do this, in the domain controller, you can search "gpmc.msc," and then it should take you to group policy management. You can right-click on group policy objects to create a new GPO. 
</p>
<p>
- Then, in the group policy management editor, navigate to Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy. And edit the rules to apply them to users on the domain. I set it to five failed logins, which locks out the account for thirty minutes. 
</p>
<p>
- Then, I practiced locking and unlocking a random user. I also changed the user's password. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/7e97173c-0c63-4b5b-b68c-dc7b9ad0baa8"/>

</p>
<p>
- This project showcases my knowledge of Active Directory. Utilizing Active Directory would be helpful for any business running a Windows infrastructure that wants to give access to its employees but keeps some information, such as files in specific directories or computers, separate. 
</p>
<p>
- It also shows my knowledge of Azure and setting up virtual machines and networks in the cloud. Active Directory helps keep a local network secure by authenticating users and sharing resources across a network, which is essential in a business environment. 
</p>
<br />
