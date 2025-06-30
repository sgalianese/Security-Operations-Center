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

- <b>Microsoft Azure</b> 
- <b>Microsoft Sentinel</b> 
- <b>Network Security Groups (NSGs)</b> 
- <b>KQL Queries</b> 

<h2>Program walk-through:</h2>

<p align="center">
Project Overview: <br/>
<img src="https://i.imgur.com/dmhtkam.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Create Resource Group, Virtual Network, and Virtual Machine in Azure:  <br/>
<img src="https://i.imgur.com/28Efhy1.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Create Custome Inbound Traffic Rule, allowing any type of connection to the Virtual Machine: <br/>
<img src="https://i.imgur.com/rOIj1UY.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Turn off firewall on Virtual Machine, ping from local device to confirm device is "open" to the internet:  <br/>
<img src="https://i.imgur.com/Z5kVEFU.jpeg" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/zImXKgD.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Fail sign in to device several times, review local logs on virtual machine:  <br/>
<img src="https://i.imgur.com/hm0UUoF.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/1dp7RoB.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Isolate failed log in attempts:  <br/>
<img src="https://i.imgur.com/IFK5VYb.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/iWMTHJz.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Create a Log analytics workspace and connect to a Microsoft Sentinel:  <br/>
<img src="https://i.imgur.com/RyJZZ6K.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/qjReJLN.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<br />
<br />
Connect AzureMonitorWindowsAgent Extension to my Virtual machine, confirm securtiy events:  <br/>
<img src="https://i.imgur.com/tBj8q9u.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/MSMK25m.png" height="80%" width="80%" alt="Active Directory Home Lab"/>

<br />
<br />
We are going to import a spreadsheet (as a “Sentinel Watchlist”) which contains geographic information for each block of IP addresses:  <br/>
Observe the logs now have geographic information, so you can see where the attacks are coming from
<br />
let GeoIPDB_FULL = _GetWatchlist("geoip");
let WindowsEvents = SecurityEvent
    | where IpAddress == <attacker IP address>
    | where EventID == 4625
    | order by TimeGenerated desc
    | evaluate ipv4_lookup(GeoIPDB_FULL, IpAddress, network);
WindowsEvents
<br />
<br />
Run JSON script to create attack map using data from honeypot:
<img src="https://i.imgur.com/9LRcCov.png" height="80%" width="80%" alt="Active Directory Home Lab"/>
<img src="https://i.imgur.com/XvB1PtR.png" height="80%" width="80%" alt="Active Directory Home Lab"/>



</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
