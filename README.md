
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
<img src="https://i.imgur.com/CUFypy6.png" height="80%" width="80%"/>
<br />
<br />
Here's the virtual machine that I created. I also made a resource group to group together the resources that I needed for this lab <br/>
<img src="https://i.imgur.com/Pz2BCFu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Creating the log analytics workspace, and connecting it to the VM<br/>
<img src="https://i.imgur.com/oOgzlHS.png" height="80%" width="80%"/>
 <img src="https://i.imgur.com/mBD9sBt.png" height="80%" width="80%"/>
<br />
<br />
Connecting the analytics workspace to microsoft sentinel<br/>
<img src="https://i.imgur.com/YvFal3B.png%60" height="80%" width="80%"/>
<br />
<br />
Using remote desktop connection to connect to the virtual machine<br/>
<img src="https://i.imgur.com/PI8YOkW.png" height="80%" width="80%"/>
<br />
<br />
Checking event viewer, with failed and successful login attempts into the vm<br/>
<img src="https://i.imgur.com/8hJ95yS.png" height="80%" width="80%"/>
<br />
<br />
Disabling the firewalls inside of the virtual machine. We also created an inbound rule whenever we created the virtual machine to allow all traffic in<br/>
<img src="https://i.imgur.com/Bm7pdkQ.png" height="80%" width="80%"/>
<br />
<br />
This is the API we used to generate a code for our powershell script to gather IP info for users<br/>
<img src="https://i.imgur.com/unBdN9Z.png" height="80%" width="80%"/>
<br />
<br />
This is the powershell script that I used to gather info on users who tried to brute force the virtual machine. This script is going to gather the info of the
 attacker and collect their information<br/>
<img src="https://i.imgur.com/KkWAnNf.png" height="80%" width="80%"/>
<br />
<br />
<img src=" https://i.imgur.com/hBodet0.png" height="80%" width="80%"/>
<br />
<br />
This is a custom log thats used to show Azure what the data were collecting is supposed to look like<br/>
<img src="https://i.imgur.com/hBodet0.png" height="80%" width="80%"/>
<br />
<br />
The powershell script takes data from the log and dislays it as shown<br/>
<img src="https://i.imgur.com/1DzNXQd.png" height="80%" width="80%"/>
<br />
<br />
I ran simple one line script to make sure the login failures(4625) is working. ((THIS COMES FIRST BEFORE PREVIOUS PHOTO))<br/>
<img src="https://i.imgur.com/iZQoR2y.png" height="80%" width="80%"/>
<br />
<br />
x9<br/>
<img src="https://i.imgur.com/1DzNXQd.png" height="80%" width="80%"/>
<br />
<br />
x10<br/>
<img src="https://i.imgur.com/MY7wSYJ.png" height="80%" width="80%"/>
<br />
<br />







