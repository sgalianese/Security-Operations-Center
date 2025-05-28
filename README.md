<h1>Security Operations Center (SOC) and Honeynet in Azure </h1>

 ### [YouTube Demonstration](https://www.youtube.com/watch?v=g5JL2RIbThM&t=202s)

<h2>Description</h2>
This project demonstrates the process of setting up a Security Operations Center (SOC) and Honeynet in Azure to monitor and analyze security threats in real-time. It leverages Microsoft Sentinel to collect logs, visualize attack patterns, and implement security controls.
<br />


<h2>Features Utilized</h2>

- <b>Log Collection: Ingests Windows Event Logs, Linux Syslogs, and Azure Network Analytics data.</b> 
- <b>Threat Detection: Uses Microsoft Sentinel to trigger alerts and create security incidents.x</b>
- <b>Security Hardening: Compares security metrics before and after applying security controls.</b>
- <b>Attack Maps: Visualizes malicious traffic sources and authentication failures.</b>

<h2>Technologies Used </h2>

- <b>Microsoft Azure</b> (21H2)
- <b>Microsoft Sentinel</b> (21H2)
- <b>Network Security Groups (NSGs)</b> (21H2)
- <b>KQL Queries</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Project Overview: <br/>
<img src="https://i.imgur.com/n9fZpk3.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Build Server//Install Windos Server OS:  <br/>
<img src="https://i.imgur.com/8cFVmdl.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/1YkPB9m.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Install Active Directory Services: <br/>
<img src="https://i.imgur.com/VRwzOBz.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/fE684WZ.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Configure Network Interface Card:  <br/>
<img src="https://i.imgur.com/JR91KZW.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Configure Remote Access:  <br/>
<img src="https://i.imgur.com/6IVhy6o.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Install DHCP and add Scope displayed in project overview:  <br/>
<img src="https://i.imgur.com/9s5oybd.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Run Powershell script to create 1,000 users to my Active Directory Lab\\Create Admin organizational unit and add my account:  <br/>
<img src="https://i.imgur.com/DIpbKPO.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/IaVjuwM.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Create Windows 11 VM and Confirm Client Receiving Address via DHCP:  <br/>
<img src="https://i.imgur.com/9QcNqBr.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
