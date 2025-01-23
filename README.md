<h1>Azure-Sentinel-Honeypot VM</h1>



<h2>Description</h2>
Honeypot Setup:Configured a Windows-based VM in Azure with RDP access exposed to the internet to attract potential attackers.<br/>
Monitoring:Integrated the VM with Microsoft Sentinel to collect and analyze security logs.<br/>

Visualization:Utilized Sentinel's mapping capabilities to display the geographic origins of failed RDP login attempts.
<br />

<h2>Tools Used</h2>

- <b>Microsoft Azure</b> 
- <b>Microsoft Sentinal</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>

<h2>Project walk-through:</h2>

<p align="center">
  Using a custom PowerShell script to lookup the attacker's Geolocation information:  <br/>
<img src="https://i.imgur.com/FZfrTCM.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creating a custom log in Log Analytics Workspace: <br/>
<img src="https://i.imgur.com/8RarqJo.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creating and extracting custom fields from raw custom log data:  <br/>
<img src="https://i.imgur.com/4UUVLfw.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Setup map in Sentinel with Latitude and Longitude: <br/>
<img src="https://i.imgur.com/AeDuRr2.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Obesrving live attacks (RDP Brute Force) from all around the world:  <br/>
<img src="https://i.imgur.com/v1u8qbR.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h2>Outcomes:</h2>
- Successfully set up a Windows-based honeypot to simulate an exposed environment for attackers.<br/>
- Monitored and collected security logs of failed RDP login attempts, gaining insights into real-world attack patterns.<br/>
- Visualized geographic origins of attacks using Sentinel's mapping features, revealing high-risk regions.<br/>
- Demonstrated the value of using honeypots for proactive threat intelligence and cybersecurity awareness.<br/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
