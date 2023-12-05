<h1>SOC-Lab-Incident-report </h1>

 

<h2>Description</h2>
Project consists of a simple PowerShell script that walks the user through "zeroing out" (wiping) any drives that are connected to the system. The utility allows you to select the target disk and choose the number of passes that are performed. The PowerShell script will configure a diskpart script file based on the user's selections and then launch Diskpart to perform the disk sanitization.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Splunk</b>
- <b>Linux VM</b>
- <b>Windows sandbox vm</b>
- <b>ANY.RUN(Sand Box Tool)</b>
- <b>Virus Total)</b>
<h2>Environments Used </h2>

- <b>Windows 7 sandbox VM</b>
- <b>Linux </b> 


<h2>Program walk-through:</h2>

<p align="center">
Splunk event alert : <br/>
<img src="https://i.imgur.com/TtKAjut.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Splunk event alert :  <br/>
<img src="https://i.imgur.com/258BqEd.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Cyber Chef: <br/>
<img src="https://imgur.com/YPxZFGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Virus Total report:  <br/>
<img src="https://i.imgur.com/TalzEiR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
: Spunk Incident Report <br/>
<img src="https://imgur.com/3D2toHo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sand box results :  <br/>
<img src="https://imgur.com/xHssB4C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sand Box threat Results:  <br/>
<img src="https://imgur.com/LxViLQq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
