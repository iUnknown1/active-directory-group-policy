<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Creating Users, Managing Accounts, Group Policy in Azure</h1>

In this section of my project, I setup Remote Desktop for non-administrative users on Client-1, then I create a bunch of additional users and attempt to log into client-1 with one of the users
 <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop Connection
- Windows Powershell ISE

<h2>Operating Systems Used </h2>

- Windows Server 2022, 2vCPUs, 8GM RAM
- Windows 10 Pro (22H2), 2vCPUs, 8GB RAM

<h2>High-Level Steps</h2>

- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users


<h2>Deployment and Configuration Steps</h2>


 1.) First, I login to DC-1 using remote computer connection and install Active Directory Domain Services using the server manager dashboard
 
![image](https://github.com/user-attachments/assets/04d6ebd5-0387-4122-bb58-31d0bb0c9f25)



<p>
Next, I have to promote this machine as a DC by configuring it as a new forest as "mydomain.com" (this can be anything, mydomain.com is just easy to remember) In the top right, I will click on the flag icon with the caution symbol and promote it as a Domain Controller.
</p>
<br />
