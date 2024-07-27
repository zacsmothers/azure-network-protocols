<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Inspecting Traffic Between Azure Virtual Machines and Network Security Groups</h1>
In this tutorial, I experiment with DNS manager and Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Various Command-Line Tools
- Network Security Groups
- DNS Manager

<h2>Operating Systems Used </h2>

- Windows 10
- Windows Server 2022

<h2>High-Level Steps</h2>

- Configure DNS Manager to create a new host
- Enable File Sharing to give users access on the Domain Controller
- Create a Security Group within Active Directory

<h2>Actions and Observations</h2>

<p>
<h3>Configure DNS Manager to create a new host</h3>
<img src="https://i.imgur.com/DhpQCqE.png" height="80%" width="80%" alt="DNS manager to create new host"/>
</p>
<p>
To create a new host I first opened DNS manager form within the Windows Server Manager on the Domain Controller, and then to access the list of A records I opened the forward lookup zone and domain folders. Within the domain I created a new A record named mainframe with the same ip address as the domain.
</p>
<br />

<p>
<h3>Enable File Sharing to give users access on Domain Controller</h3>
<img src="https://i.imgur.com/A4NKaZy.png" height="80%" width="80%" alt="Enable File Sharing to give access to users"/>
</p>
<p>
In order to enable file sharing for a user who is connected to the domain I first accessed the file needed by the user in this example as seen in the picture above that is the "no-access" folder, after accessing the sharing feature within the folder's properties I gave access to the domain admins, in the other folders titled "read-access," and "write-access" I gave access to domain users.
</p>
<br />

<p>
<h3>Create a Security Group within Active Directory</h3>
<img src="https://i.imgur.com/x8gfoyg.png" height="80%" width="80%" alt="Create Security Group within Active Directory"/>
</p>
<p>
In this example as seen in the picture above I created a network security group for accountants as they often work with sensitive data a network security group can be effective for giving only the accounting department access to specific files within a domain. This is done by adding an organizational unit within Active Directory and then within the organizational unit creating a group and giving the group the security type.
</p>
<br />
