<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
Active Directory is the identity backbone of every Windows enterprise environment. In this lab I will build one from scratch — setting up a domain controller, structuring departments as Organizational Units, creating users and security groups, and enforcing security policies across every machine in the domain.
<br />

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Server Manager</b>
- <b>Azure</b>

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

Select Add a new forest and for the root domain name insert Lab.local and select next. Create a password ( disater recovery, etc) and click next until you are able to click install
<br />
<br />
<img width="1816" height="1156" alt="image" src="https://github.com/user-attachments/assets/11fcceb6-8680-41cb-9e83-dae775c7a5b1" />


Open Active Users users and computers. Right click the domain (lab.local) hover over new and select Organizational Unit and name it. (Manual way)

<img width="1644" height="1110" alt="image" src="https://github.com/user-attachments/assets/d337cfff-714b-48d1-8120-342708d33390" />
<br />
<br />

(Scripted way) Open powershell and insert the script and  press the green play button to add multiple OU as once.
<br />
<br />

<img width="1610" height="628" alt="image" src="https://github.com/user-attachments/assets/6817e8b7-4671-410c-be63-d7e28615e3a5" />
<br />
<br />

To do a security Group right click the domain, hover over new, and select group and give a name.( Manually)

<img width="1428" height="1036" alt="image" src="https://github.com/user-attachments/assets/4ceb383e-ad8d-4d1f-ab5e-fd726d2c09e4" />
<br />
<br />

(Scripted) Insert the script and press the green play button. To add multiple Security Groups at once

<img width="1976" height="1076" alt="image" src="https://github.com/user-attachments/assets/b76d0f5e-2b82-43c0-991c-26975225941e" />
<br />
<br />

Click on user, right click a white empty space, hover over new and select user. Create a user name and password for the user and select next

<img width="865" height="574" alt="Screenshot 2026-08-16 at 12 15 39 PM" src="https://github.com/user-attachments/assets/e2f7d362-6cd0-4ebd-8ddc-351a1e6ef7c7" />

<img width="898" height="766" alt="image" src="https://github.com/user-attachments/assets/9eb5f4dc-f672-42e4-a208-811253a1ddc9" />
<br />
<br />
(Scripted) Insert the script, and it will create A password for everyone, Four users including their first name, surname, account name, Principal name. Also, for the four users they are being added to their department / group. 

<img width="1994" height="1290" alt="image" src="https://github.com/user-attachments/assets/e766682a-0c19-4502-ba90-e8ba89695035" />


Step #5 Group Policy 
Open Server Manager, Hover over tools, and select Group Policy Management. Click on forest and then domain.
<img width="2242" height="1142" alt="image" src="https://github.com/user-attachments/assets/7c2d1a67-afa2-447a-b946-39650f1a52f2" />

Drop down domain, lab.local, and right click IT and select Create a GPO in this domain, and link it here. and name it. 
<img width="1004" height="538" alt="image" src="https://github.com/user-attachments/assets/9dfc3ecc-08c0-490c-8dda-f4d26c42bd79" />

Go through the drop downs and right click the one you named and select edit
<img width="750" height="538" alt="image" src="https://github.com/user-attachments/assets/71b0e79d-2d31-417e-a60f-6ecb571da541" />

Drop down Computer configuration, Policies, Windows Settings, Security Settings, Account policies, Click on password policy and right click minimum password length and select properties then, check the define this policy setting and set the characters to 12 and then apply

<img width="1552" height="602" alt="image" src="https://github.com/user-attachments/assets/80c780d2-0ffb-4794-b44a-3b2676037e71" />

For Password Complexity, Select the same drop downs and right click on Password must meet complexity requirements. Select Properties and check the define this policy setting box then click enable and ok.
<img width="1566" height="548" alt="image" src="https://github.com/user-attachments/assets/ce73201f-0060-4330-86c5-2ce18d4c74f0" />

For Machine inactivity. Do the drops downs of Computer configuration, Policies, Windows Settings, Security Settings, Local polices, then select Security Options. Right click Interactive logon, machine inactivity limit. select properties, check the define this policy setting box and set to 900 seconds ( 15 minutes)
<img width="1974" height="522" alt="image" src="https://github.com/user-attachments/assets/77d96e78-e1de-4ed5-b7c7-5fcecc9c364e" />

Removable storage, Drop down computer configuration, policies, Administrative Templates: Policy definition, Systems, Click on Removable Storage Access, right click all removable storage classes: Deny all access, select edit, Enable and apply then ok.
<img width="2786" height="1378" alt="image" src="https://github.com/user-attachments/assets/9f98aa7a-9269-4f10-b04a-6c0db4bb1606" />

Step 6 
Reset Passwords: Open Active Directory, click on the HR file, and right click on user( Carol) and reset password and unlock account.
<img width="1216" height="506" alt="image" src="https://github.com/user-attachments/assets/2b8cd5dd-26ee-44ad-be40-92c6c8d5d6c4" />
<img width="882" height="578" alt="image" src="https://github.com/user-attachments/assets/f266caa7-16cc-4c84-ac23-3b30cb40b8fd" />
<img width="1350" height="884" alt="image" src="https://github.com/user-attachments/assets/dc55933f-1045-4cf0-99ef-46ed29e240b7" />


(Scripted) Unlock account / rest password / Disable user: Inserter the scripts in powershell
<img width="1480" height="1018" alt="image" src="https://github.com/user-attachments/assets/cf0d9b3b-f050-40b2-8038-e52a07e8e426" />
<img width="1384" height="894" alt="image" src="https://github.com/user-attachments/assets/2226e0c9-ffec-44aa-afa5-0bd0e849c70a" />

Manually Disable user account: Right click user account and select disable. 
<img width="1078" height="524" alt="image" src="https://github.com/user-attachments/assets/1267288f-ff75-4463-9820-8a644ad85e0a" />

Auditing and reporting script to check to see who has been inactive
<img width="2030" height="1370" alt="image" src="https://github.com/user-attachments/assets/bb7063a4-95ec-4531-8fbc-51928cbcbd9f" />





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
