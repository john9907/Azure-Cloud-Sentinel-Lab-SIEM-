
<h1>Azure Cloud Sentinel Lab (SIEM)</h1>

<h2>Description</h2>
In this SIEM lab, Microsoft Azure is employed to create a virtual machine. Firewalls are disabled to permit brute force attempts by others on the virtual machine. PowerShell is utilized to extract metadata from Windows Event Viewer, and geolocation data is gathered using a third-party API. The resulting data is displayed through the creation of an Azure Sentinel workbook, showcasing the location of the attacks on a world map via custom fields in a Log Analytics workspace.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Azure</b>

<h2>Environments Used </h2>

- <b>Azure Virtual Desktop (Windows 10)</b>

<h2>Program walk-through:</h2>

<p align="center">
Creating an inbound rule to allow all traffic into my VM<br/>
<img src="https://i.imgur.com/CUFypy6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Here's the virtual machine that I created. I also made a resource group to group together the resources that I needed for this lab <br/>
<img src="https://i.imgur.com/Pz2BCFu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creating the log analytics workspace, and connecting it to the VM<br/>
<img src="https://i.imgur.com/oOgzlHS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/mBD9sBt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

