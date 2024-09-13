
<h5>Directory</h5> 

<b>[Tech Portfolio Home](https://github.com/Jays1115/Jalen-Smith.git)</b>

# VSI's Custom Splunk Environment

<h2>Part 1 Description</h2>
Scenerio: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandalay has been experiencing DDOS attacks against their web servers. Not only were Vandalay web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage.
<br>
<br>
Assignment: Create a report to determine the impact of the DDOS attack on upload and download speed. Create an additional field to calculate the ratio of the upload speed to the download speed.

<h2>Program walk-through:</h2>

<p align="center">
Used the eval command to create a field called ratio that shows the ratio between the upload and download speeds. Then, created a report using Splunk's table command to display the _time, IP_ADDRESS, DOWNLOAD_MEGABITS, UPLOAD_MEGABITS, ratio fields in a statistics report.
<br/>
<img src="images/1.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<img src="images/2.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Findings</b>
 <br/>
Based on the report generated above, 2/23/2020 @ 2:30 was the approximate time of the DDOS attack on Vandalay. Its reasonable to infer that the attack took place during that time due to the sharp decline in download and upload speeds recorded during that time. I took Vandlay's system approximately 6 hours to recover.
 
<h2>Part 2 Description</h2>
Scenerio: Due to the frequency of attacks, your manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, you have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.
<br>
<br>
Assignment: Create a report determining how many critical vulnerabilities exist on the customer data server. Then, build an alert to notify your team if a critical vulnerability reappears on this server.

<h2>Program walk-through:</h2>

<p align="center">
After uploading the Nessues vulnerability scan to Splunk, created a report that shows the count of critical vulnerabilities from the customer database server (10.11.36.23) and counted the number vulnerabilities by their level of severity (informational, low, medium, high, critical).
<br/>
<img src="images/3.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
 <br/>
 <br/>
 From the above report, built an alert that monitors every day to see if this server has any critical vulnerabilities. If a critical vulnerability exists, the alert will send an email to soc@vandalay.com.
 <br/>
 <img src="images/4.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
 
 <h2>Part 3 Description</h2>
Scenerio: A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again
<br>
<br>
Assignment: Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.

<h2>Program walk-through:</h2>

<p align="center">
After uploading the admin logs to Splunk, created a timechart that shows the number of failed logon attempts over the entirety of the dataset. Decided to visualize this data as a column chart to better understand the data. This allowed me to easily determine a threshold of greater than 24 failed logon attempts for the Brute Force Attack Alert I created below.
<br/>
<img src="images/5.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
 <br/>
 <br/>
 From the above timechart, built an alert that monitors failed logon attempts evey hour. If greater than 24 failed logon attempts are detected, the alert will send an email to soc@vandalay.com.
 <br/>
 <img src="images/6.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
