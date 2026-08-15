<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
Active Directory is the identity backbone of every Windows enterprise environment. In this lab you will build one from scratch — standing up a domain controller, structuring departments as Organizational Units, creating users and security groups, and enforcing security policies across every machine in the domain.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Server Manager</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">

Create an Account on Azure and make a Virtual Machine. After creating a name for your VM you would set your zone, region, and image. <br/>
<img width="1440" height="900" alt="Screenshot 2026-08-14 at 12 04 33 PM" src="https://github.com/user-attachments/assets/17e2aa30-45bb-4058-946a-2138bb9143bf" />


<br />
<br />
Select a size and Create a username and password for the VM <br/>
<img <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/07da886f-6fb9-479e-b963-c58c4c602adb" />
" />

<br />
<br />
Click go to resources, click connect and download RDP file:  <br/>
<img s<img width="1884" height="1104" alt="image" src="https://github.com/user-attachments/assets/8c2cbc19-ed9d-4e7c-8d2a-baa76c1736b0" />
<img width="1522" height="312" alt="image" src="https://github.com/user-attachments/assets/e9e979fb-92aa-4540-9f03-122470ac120c" />
<img width="1388" height="292" alt="image" src="https://github.com/user-attachments/assets/07ce8e8c-c2c8-4f06-b41f-7323f71dc223" />

<br />
<br />
Once you gotten into your VM you would exit out and open windows. At the top right you would click the plus symbol and click ad PC. You will then Insert the IP address in for PC Name.  <br/>
<img width="1416" height="1288" alt="image" src="https://github.com/user-attachments/assets/d1e7ee47-a056-4981-943a-48a5d7e40dba" />


<br />
<br />
CLick on devices and audios, and make sure it is set to Bidirectional and click add  <br/>
<img width="1080" height="822" alt="image" src="https://github.com/user-attachments/assets/bbacc38b-d547-49f9-9605-1555c5d0712b" /> 

Click on the VM and login with the username and password you created for that VM

<br />
<br />
Click manage and then Add roles and Features. From there you will continue to click next until you get to Server Roles  <br/>
<img width="1962" height="568" alt="image" src="https://github.com/user-attachments/assets/3c71f388-c8a8-4822-aa07-e4e1cbc0849d" />

</p>
<br />
<br />
When you get to server roles, click Active Directory Domain Services and then Add Features. You will then continue to click next until you are able to click install. <br/>
<img width="1536" height="446" alt="image" src="https://github.com/user-attachments/assets/4d3d4037-0f68-4409-9530-523822af8d24" />

<br />
<br />
Once its finish installing you will click close for now and search powershell ISE and run it as adminastrator <br/>
<img width="1540" height="1012" alt="image" src="https://github.com/user-attachments/assets/44bed834-70c8-4968-b47a-340eb7fe1d1b" />
<img width="1596" height="1154" alt="image" src="https://github.com/user-attachments/assets/d132a5af-e0b5-4cab-a332-b69af7840ae4" />

<br />
<br />
Click on the white page like symbol in the top left corner that says new script. Insert the script below " Install-WindowsFeature -Name GPMC " and press the green play button to install the GPMC <br/>

<img width="693" height="477" alt="Screenshot 2026-08-15 at 12 18 52 PM" src="https://github.com/user-attachments/assets/3974f129-a1c2-40af-aed6-3795ac55e192" />

Minimize powershell and click the flag with the caution symbol and select promote this server to a domain controller

<img width="796" height="306" alt="image" src="https://github.com/user-attachments/assets/ab61f51e-73d7-4478-93be-a3f04bd19aa1" />


<!--<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
