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


<h2>Installation Steps</h2>

<img src="https://github.com/user-attachments/assets/44ad84bb-e0fe-4663-9f1f-9a7adff930ef"/>

</p>
<p>
Create a resource group and virtual network that we will be hosting both our domain controller and client machine on.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/b8669fc5-d14a-42f5-ba66-ecf5dc0a5d46"/>

</p>
<p>
Create the domain controller machine, make sure it is in the same region as our Virtual Network. Additionally, it is extremely important that we create the Domain Controller in the 2022 Windows SERVER Datacenter Image as otherwise it will not be capable of functioning as a domain controller. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/02e77c0d-66a9-47c0-9bf6-0da61f2bc19b"/>

</p>
<p>
Next, create the Client Machine in the same Virtual network as your domain controller but this time use the Windows 10 Pro Image as this machine will not need to be running a server.
</p>

<p>
<img src="https://github.com/user-attachments/assets/0b9af793-c5eb-459c-8af7-c489438d8913"/>

</p>
<p>
Next, navigate to the network settings in our domain controller machine so that we can change the IP Address Allocation to Static instead of Dynamic.
</p>

<p>
<img src="https://github.com/user-attachments/assets/88ed4589-448c-4303-a50f-b4948136b442"/>

</p>
<p>
Change the Client Machine's DNS Settings to DC-1's Private IP Address in Network Settings. 
</p>

<img src="https://github.com/user-attachments/assets/77342aa7-5a1a-48a3-9387-b00c39b4a129"/>

</p>
<p>
Log in to your client machine and attempt to ping the domain controller's private IP address. 
</p>

<img src="https://github.com/user-attachments/assets/a44a4fef-14b9-446c-808a-6bcc0d25655f"/>

Finally, run ipconfig /all to confirm that our DNS Settings outputs matches the domain controller's private IP Address.


<br />
