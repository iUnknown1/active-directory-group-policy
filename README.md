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

<p>
Next, We can check by searching "Active Directory Users and Computers" > mydomain.com > _EMPLOYEES. Here we will pick a user and log into client-1 using this username and the password the script sets for all of these users which is "Password1"
</p>
<br />

![image](https://github.com/user-attachments/assets/fd48a52e-0cb0-4b82-9029-c1de1ed007bb)

<p>
Now, I log into DC-1 and pick a random user account I created previously. Then
Attempt to log in with it 10 times with a bad password. Make sure to configure Group Policy to Lockout the account after 5 attempts:
</p>
<br />

![image](https://github.com/user-attachments/assets/8fd1a8d9-9286-407b-a675-d71d40401571)

<p>
Attempt to sign back into it with our random user with an invalid password 5 times. A lockout message will appear:
</p>
<br />

![image](https://github.com/user-attachments/assets/d21325b9-d793-419b-93c3-b5d92db57919)

<p>
To unlock the users account, hlogin to DC and go to Active Directory Users and Computers, then _EMPLOYEES, Account tab and check the "Unlock account" box:
</p>
<br />

![image](https://github.com/user-attachments/assets/cfd4b55f-4d53-48c9-9917-8079d187b60f)

