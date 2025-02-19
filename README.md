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


 1.) First, I login into Client-1 as mydomain.com\jane_admin to go into settings for remote desktop connection and allow it for non administrative users.
 
![image](https://github.com/user-attachments/assets/9d0ebb20-899f-475a-bdf8-dc4c5009c7f8)


<p>
Next, We log into Domain Controller as mydomain.com\jane_admin and open Powershell ISE to use the create user script.
</p>
<br />


![image](https://github.com/user-attachments/assets/1b8d8882-fc97-4095-a483-af7d6d988e39)

<p>
I run the user creation script and powershell will start to create random users and place them in the OU(Organizational Unit) we created in the previous section that we named "_EMPLOYEES".
</p>
<br />

![image](https://github.com/user-attachments/assets/4af66bd1-b77e-44d3-964c-51b6ccead66d)
