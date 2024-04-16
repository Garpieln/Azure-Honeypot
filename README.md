<h1>Azure Honeypot</h1>

<h2>Introduction</h2>
<h3>Overview</h3>

This was one of the first lab projects I completed. The main goal here is to get some exposure to a SIEM, get some experience within the azure environment setting up a virtual machine as well as the systems behind the telemetry. As the title says, this project's goal was to create a vulnerable machine and expose it to the internet for attacks to discover and attempt to brute force. Once discovered by ICMP, the attacker can attempt to remotely access the machine likely through RDP and attempt to login to the machine by using common or random usernames/passwords. All of these attempst to login to our machine generates a windows event #4625 for a failed login attempt. We will set a powershell script to pull information from these windows events and send to a 3rd party API to get geolocation data like latitude, longitude, State, Country, etc. From this we create the custom log that is ingested into Microsoft Log Analytics and subsequently quieried by Microsoft Sentinel and plotted on a map.


<h3>Objectives</h3>

- <b>Gain hands on experience within Microsoft Azure environment.</b> 
- <b>Gain experience with Microsoft Sentinel SIEM</b>

<br />


<h2>Skills Learned</h2>

- <b>Learned how to use powershell to forward logs to a 3rd party api and generate a custom log</b> 
- <b>Learned how to query a custom log with KQL within Microsoft Sentinel</b>
- <b>Learned how to extract fields from a custom log and create a attack map</b>

<h2>tools Used</h2>

- <b>Microsoft Azure Sentinel</b>
- <b>Microsoft Analytics Workspace</b>
- <b>Powershell</b>
- <b>Virtual Machines</b>
- <b>KQL</b>

<h2>Steps Used</h2>


1. Create windows vm, turn off firewall and enable ICMP</b>
2. Create and set up log analytics workspace to ingest logs, connect to VM</b>
3. Use powershell script to send IP address into geolocation API, to get back latitude and longitude of IP address; used in the custom logs</b>
4. Ingest custom logs into Log Analytics Workspace; extract fields from rawdata. (latitude, longitude, username, sourcehost IP, state/provice, Country, timestamp)</b>
5. Query custom log in Azure Sentinel, including sourcehost, and Country and plot on world map </b>

<br />
<div>
  <img src="attack-map.png" height="100%" width="100%"/>
  <p style="text-align: center;">Failed RDP attack map</p>
</div>

<br />
<br />


### [Project Reference](https://www.youtube.com/watch?v=RoZeVbbZ0o0)

Disclaimer: this is not a step by step guide for you to follow, please visit the link above to see the source video and follow along with that. 
