# Splunk-Project

### Basic Splunk Homework

### Scenario
You have just been hired as an SOC Analyst by Vandalay Industries, an importing and exporting company.


Vandalay Industries uses Splunk for their security monitoring and have been experiencing a variety of security issues against their online systems over the past few months.


You are tasked with developing searches, custom reports and alerts to monitor Vandalay's security environment in order to protect them from future attacks.

### System Requirements
You will be using the Splunk app located in the Ubuntu VM.

### My Objective
Utilize Splunk to design a powerful monitoring solution to protect Vandaly from security attacks.

### Step 1: The Need for Speed
Background: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandaly has been experiencing DDOS attacks against their web servers.
Not only were web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage. Your networking team provided results of a network speed run around the time of the latest DDOS attack.

**Task:** Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.


Using the eval command, create a field called ratio that shows the ratio between the upload and download speeds.

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk1.jpg" align="center" height="100%" width="100%" ></a>




Create a report using the Splunk's table command to display the following fields in a statistics report:

_time
IP_ADDRESS
DOWNLOAD_MEGABITS
UPLOAD_MEGABITS
ratio

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk2.jpg" align="center" height="50%" width="50%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk3.jpg" align="center" height="100%" width="100%" ></a>


Based on the report created, what is the approximate date and time of the attack?
**2020-02-23 14:30:00pm**

How long did it take your systems to recover?
**Systems recovered at 2020-02-23 22:30:00pm. 8 hours total**


### Step 2: Are We Vulnerable?
Background:  Due to the frequency of attacks, your manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, you have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.

**Task:** Create a report determining how many critical vulnerabilities exist on the customer data server. Then, build an alert to notify your team if a critical vulnerability reappears on this server.

Create a report that shows the count of critical vulnerabilities from the customer database server.

The database server IP is 10.11.36.23.
The field that identifies the level of vulnerabilities is severity.

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk4.jpg" align="center" height="50%" width="50%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk5.jpg" align="center" height="80%" width="80%" ></a>

Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, have an alert emailed to soc@vandalay.com.

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk6.jpg" align="center" height="50%" width="50%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk7.jpg" align="center" height="50%" width="50%" ></a>

### Step 3: Drawing the (base)line
Background:  A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.

**Task:** Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.


When did the brute force attack occur?
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk8.jpg" align="center" height="50%" width="50%" ></a>

**The attack started at 8AM on Feb 21 2020**

Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.

**Since the average failed logins attempts is around 6 to 23. I put the alert trigger at 30 or higher within an hour span.**

Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk9.jpg" align="center" height="50%" width="50%" ></a>
