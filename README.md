
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
A Microsoft Azure subscription was created, and navigation to the virtual machine tab was performed. The screenshots below depict the steps executed to complete the lab.
<br />
<br />
Configuration of the network security group for the VM included creating an inbound rule to allow all traffic into the VM.
<br />
<br />
<img src="https://i.imgur.com/CUFypy6.png" height="80%" width="80%" href="Sample"/>
<br />
<br />
Here's the virtual machine that was created, along with addition to the resource group designated for every tool in this lab.
<br />
<br />
<img src="https://i.imgur.com/Pz2BCFu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creation of the log analytics workspace to ingest information from VM's event viewer, and establishment of a custom log to gather geographic information, followed by connection to the VM.
<br />
<br />
<img src="https://i.imgur.com/oOgzlHS.png" height="80%" width="80%"/>
 <img src="https://i.imgur.com/mBD9sBt.png" height="80%" width="80%"/>
<br />
<br />
Connecting the analytics workspace to Microsoft Sentinel.
<br />
<br />
<img src="https://i.imgur.com/YvFal3B.png%60" height="80%" width="80%"/>
<br />
<br />
Usage of remote desktop connection to connect to the virtual machine.
<br />
<br />
<img src="https://i.imgur.com/PI8YOkW.png" height="80%" width="80%"/>
<br />
<br />
Inspection of event viewer in the VM reveals failed and successful login attempts into the VM, where metadata such as IP and username can be extracted.
<br />
<br />
<img src="https://i.imgur.com/8hJ95yS.png" height="80%" width="80%"/>
<br />
<br />
The firewall within the virtual machine was disabled, and additionally, an inbound rule was configured at the Azure Network Security Group to allow all traffic into the virtual machine regardless of its source. These actions compromise the security of the virtual machine, as it lacks the ability to inspect incoming or outgoing traffic at the network level.
<br />
<br />
<img src="https://i.imgur.com/Bm7pdkQ.png" height="80%" width="80%"/>
<br />
<br />
This is the API key required for the PowerShell script. The API key will be used in the PowerShell script for the subsequent steps.
<br />
<br />
<img src="https://i.imgur.com/unBdN9Z.png" height="80%" width="80%"/>
<br />
<br />
<br />
<br />
The PowerShell script utilizes the API Key from ipgeolocation.io to gather geo data from the IP address derived from Windows Event Viewer failed login attempts. The powershell script then logs this information into a custom log file.
<br />
<br />
<img src="https://i.imgur.com/KkWAnNf.png" height="80%" width="80%"/>
<br />
<br />
<img src=" https://i.imgur.com/hBodet0.png" height="80%" width="80%"/>
<br />
<br />
This is a custom log used to demonstrate to log analytics the format of the data being collected. Log analytics retrieves the logs from the VM that are generated and stored in the failed_rdp.log file, and utilizes these logs for the Azure tools used in the subsequent steps.
<br />
<br />
<img src="https://i.imgur.com/hBodet0.png" height="80%" width="80%"/>
<br />
<br />
Validation that the logs are functioning and log analytics is ingesting the failed login attempts, as shown utilizing Kusto Query Language (KQL) to display event failure ID's.
<br />
<br />
<img src="https://i.imgur.com/iZQoR2y.png" height="80%" width="80%"/>
<br />
<br />
Geographic data from the failed_rdp.log file is sorted and organized using KQL for use in the next step.
<br />
<br />
<img src="https://i.imgur.com/1DzNXQd.png" height="80%" width="80%"/>
<br />
<br />
In the final step, log analytics was utilized in conjunction with the virtual machine and the PowerShell script to gather all of the failed login attempts. Then, the KQL script from the previous step was used with Microsoft Sentinel map workbook to plot the geographic data on a world map.
<br />
<br />
<img src="https://i.imgur.com/MY7wSYJ.png" height="80%" width="80%"/>
<br />
<br />
















