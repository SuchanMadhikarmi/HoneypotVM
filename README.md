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

## Project Walkthrough

### 1. Using a Custom PowerShell Script to Lookup the Attacker's Geolocation Information
The PowerShell script queries the attacker's IP address against an external API (such as ip-api.com) to retrieve geolocation details, including:
- Country
- Region
- City
- Latitude & Longitude
- ISP & ASN Information

This information helps identify the attacker's location and potential origin of the attack. The extracted data is then logged for further analysis.

<p align="center">
  <img src="https://i.imgur.com/FZfrTCM.jpeg" height="80%" width="80%" alt="Geolocation Lookup"/>
</p>

---

### 2. Creating a Custom Log in Log Analytics Workspace
The extracted geolocation data from the PowerShell script is sent to the Azure Log Analytics Workspace. A custom table is created within Log Analytics to store and analyze the incoming geolocation data. This allows security teams to:
- Correlate attacker IPs
- Track patterns
- Enhance threat intelligence

<p align="center">
  <img src="https://i.imgur.com/8RarqJo.jpeg" height="80%" width="80%" alt="Custom Log in Log Analytics"/>
</p>

---

### 3. Creating and Extracting Custom Fields from Raw Custom Log Data
Custom fields are created within Log Analytics to extract specific details from the raw logs. Kusto Query Language (KQL) is used to parse fields such as:
- Attacker IP
- Country
- City
- Coordinates

These fields make it easier to filter and analyze attack patterns efficiently.

<p align="center">
  <img src="https://i.imgur.com/4UUVLfw.jpeg" height="80%" width="80%" alt="Extracting Custom Fields"/>
</p>

---

### 4. Setting Up a Map in Sentinel with Latitude and Longitude
Microsoft Sentinel is configured to visualize attack sources on a world map using the extracted latitude and longitude coordinates. This provides a real-time geographic view of incoming threats, helping security teams identify attack clusters and take proactive measures.

<p align="center">
  <img src="https://i.imgur.com/AeDuRr2.jpeg" height="80%" width="80%" alt="Map in Sentinel"/>
</p>

---

### 5. Observing Live Attacks (RDP Brute Force) from Around the World
With all configurations in place, live RDP brute-force attack attempts are monitored in real-time. The Sentinel dashboard continuously updates to display attacker geolocations, helping security teams respond to threats proactively. The insights gained can be used to implement:
- IP Blocking
- Geo-fencing
- Additional Authentication Mechanisms

<p align="center">
  <img src="https://i.imgur.com/v1u8qbR.jpeg" height="80%" width="80%" alt="Live Attack Monitoring"/>
</p>

---

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
