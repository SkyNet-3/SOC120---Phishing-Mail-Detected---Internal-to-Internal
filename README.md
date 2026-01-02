<h1>SOC120 - Phishing Mail Detected - Internal to Internal</h1>


<h2>Description</h2>
At first glance, the email appears to be sent internally between employees, which may be an attempt by an attacker to spoof the company’s email domain to gain trust. The generic subject line “Meeting” is commonly used in phishing campaigns to prompt user interaction. Although the email was allowed to reach the user, the alert indicates potential internal spoofing or compromised credentials and warrants further investigation.
<br />


<h2> Utilities Used</h2>

- <b>LetsDefend SIEM</b> 
- <b>LetsDefend Email Security</b>
- <b>LetsDefend EDR</b>
- <b>AnyRun</b>
- <b>VirusTotal</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (22H2)

<h2>Alert walk-through:</h2>

<p align="center">
Go to investigation channel in Monitoring to get the context of the alert: <br/>
<img src="https://i.imgur.com/tLRNvuT.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After taking ownership of the case, parse the email for the needed information to perform analyses:  <br/>
<img src="https://i.imgur.com/4Re6cZL.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In order to see if the email had any URLs or attachments, check the Email Security by searching the subject name and matching the sender, recipient, date, and time. There's no URLs or attachments so proceed by answering “No” in the case management section: <br/>
<img src="https://i.imgur.com/oEREseX.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Although, its prompting me to add the artifacts (as if this is showing it a false positive and moving me to the last steps) im first going to verify with another data source to validate if the SMTP IP matches the senders before proceeding to the final steps:  <br/>
<img src="https://i.imgur.com/84qA7mf.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
SMTP IP was verified in EDR and confirmed to belong to the organization’s Exchange server. feeling reassured, I will now proceed with the final steps:  <br/>
<img src="https://i.imgur.com/210HblU.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Add the artifacts collected from your investgation in the case:  <br/>
<img src="https://i.imgur.com/tAJ78LG.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
write your analyst notes from the case. click confirm and youre finished! Next closing the case..:  <br/>
<img src="https://i.imgur.com/7t2GaCB.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Lastly, close out your case by identifying this alert as a false Positive because the security system incorrectly identified this as malicious. Write your notes, close it out, and youre done!:  <br/>
<img src="https://i.imgur.com/bfajoqG.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
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
