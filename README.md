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

1. _time
2. IP_ADDRESS
3. DOWNLOAD_MEGABITS
4. UPLOAD_MEGABITS
5. ratio

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk2.jpg" align="center" height="100%" width="100%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk3.jpg" align="center" height="60%" width="60%" ></a>


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

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk4.jpg" align="center" height="100%" width="100%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk5.jpg" align="center" height="80%" width="80%" ></a>

Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, have an alert emailed to soc@vandalay.com.

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk6.jpg" align="center" height="70%" width="70%" ></a>

<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk7.jpg" align="center" height="70%" width="70%" ></a>

### Step 3: Drawing the (base)line
Background:  A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.

**Task:** Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.


When did the brute force attack occur?
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk8.jpg" align="center" height="70%" width="70%" ></a>

**The attack started at 8AM on Feb 21 2020**

Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.

**Since the average failed logins attempts is around 6 to 23. I put the alert trigger at 30 or higher within an hour span.**

Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk9.jpg" align="center" height="70%" width="70%" ></a>


**Master of the SOC**


Your an SOC analyst at a small company called Virtual Space Industries (VSI), which designs virtual reality programs for businesses.
VSI has heard rumors that a competitor, JobeCorp, may be launching cyberattacks to disrupt VSI's business.
As SOC analysts, you are tasked with using Splunk to monitor against potential attacks on your systems and applications.
Your Networking team has provided you with past logs to help you develop baselines and create reports, alerts, and dashboards.


You've been provided the following logs:

Windows Server Logs
This server contains intellectual property of VSI's next-generation virtual reality programs.

Apache Server Logs
This server is used for VSI's main public-facing website vsi-company.com.


Windows Server Instructions and Deliverables
Design the following deliverables to protect VSI from potential attacks by JobeCorp.


**Reports for Windows Logs:**
Design the following reports to assist VSI with quickly identifying specific information.


A report with a table of signatures and associated SignatureID.
This will allow VSI to easily view reports that show the ID number with a specific signature of the Windows activity.


A report that provides the count and percent of the severity.
This will allow VSI to quickly know the severity levels of the Windows logs being viewed.


A report that provides a comparison between the success and failure of Windows activities.
This will show VSI if there is a suspicious level of failed activities on their server.


**Alerts for Windows Logs:**
Design the following alerts to notify VSI of suspicious activity:


Determine a baseline and threshold for hourly level of failed Windows activity.

Create an alert to trigger when the threshold has been reached.
The alert should trigger an email to SOC@VSI-company.com.


Determine a baseline and threshold for hourly count of the signature: an account was successfully logged on.

Create an alert to trigger when the threshold has been reached.
The alert should trigger an email to SOC@VSI-company.com.


Determine a baseline and threshold for hourly count of the signature: a user account was deleted.


Design the alert based on the corresponding SignatureID, as the signature name sometimes changes when the Windows system updates.
Create an alert to trigger when the threshold has been reached.
The alert should trigger an email to SOC@VSI-company.com.


**Visualizations and Dashboards:**
Design the following visualizations and add them to a dashboard called Windows Server Monitoring:

A line chart that displays the different signature field values over time.
A line chart that displays the different user field values over time.
A bar, column, or pie chart that illustrates the count of different signatures.
A bar, column, or pie chart that illustrates the count of different users.
A statistical chart that illustrates the count of different users.
On your dashboard, add the ability to change the time range for all your visualizations.




**Apache Web Server Instructions and Deliverables**
Design the following deliverables to protect VSI from potential attacks by JobeCorp:


**Reports for Apache:**
Design the following reports to assist VSI with quickly identifying specific information:


A report that shows a table of the different HTTP methods (GET, POST, HEAD, etc).
This will provide insight into the type of HTTP activity being requested against their web server.


A report that shows the top 10 domains that referred to VSI's website.
This will assist VSI with identifying suspicious referrers.


A report that shows the count of the HTTP response codes.
This will provide insight into any suspicious levels of HTTP responses.



**Apache Alerts: Design the following alerts:**


Determine a baseline and threshold for hourly activity from a country other than the United States.
Create an alert to trigger when the threshold has been reached.
The alert should trigger an email to SOC@VSI-company.com.


Determine an appropriate baseline and threshold for hourly count of the HTTP POST method.
Create an alert to trigger when the threshold has been reached.
The alert should trigger an email to SOC@VSI-company.com.



**Visualizations and Dashboards:**
Design the following visualizations and add them to a dashboard called Apache WebServer Monitoring.

A line chart that displays the different HTTP methods field over time.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-1.png" align="center" height="100%" width="100%" ></a>

A geographical map showing the location based on the clientip field.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-2.png" align="center" height="100%" width="100%" ></a>

A bar, column, or pie chart that displays the number of different URIs.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-3.png" align="center" height="100%" width="100%" ></a>

A bar, column, or pie chart that displays the counts of the top 10 countries.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-4.png" align="center" height="100%" width="100%" ></a>

A statistical chart that illustrates the count of different user agents.
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-5.png" align="center" height="100%" width="100%" ></a>

On your dashboard, add the ability to change the time range for all your visualizations:


**Defend Your SOC**


VSI recently experienced several cyberattacks, likely from their adversary JobeCorp.
Fortunately, your SOC team had set up several monitoring solutions to help VSI quickly identify what was attacked.
These monitoring solutions will also help VSI create mitigation strategies to protect the organization.


You have been provided two logs files of suspicious activity:

One for a Windows server
One for an Apache web server


**Report Analysis for Severity**

Did you detect any suspicious changes in severity?


**Report Analysis for Failed Activities**

Did you detect any suspicious changes in failed activities?



**Alert Analysis for Failed Windows Activity**

Did you detect a suspicious volume of failed activity?


If so, what was the count of events in the hour(s) it occurred?


When did it occur?


Would your alert be triggered for this activity?


After reviewing, would you change your threshold from what you you previously selected?



**Alert Analysis for Successful Logons**

Did you detect a suspicious volume of successful logons?


If so, what was the count of events in the hour(s) it occurred?


Who is the primary user logging in?


When did it occur?


Would your alert be triggered for this activity?


After reviewing, would you change your threshold from what you you previously selected?



**Alert Analysis for Deleted Accounts**

Did you detect a suspicious volume of deleted accounts?



**Dashboard Analysis for Time Chart of Signatures**
Analyze your new dashboard results and answer the following questions:


Does anything stand out as suspicious?


What signatures stand out?


What time did it begin/stop for each signature?


What is the peak count of the different signatures?



**Dashboard Analysis for Users**
Analyze your new dashboard results and answer the following questions:


Does anything stand out as suspicious?


Which users stand out?


What time did it begin and stop for each user?


What is the peak count of the different users?



**Dashboard Analysis for Signatures with Bar, Graph, and Pie Charts**
Analyze your new dashboard results and answer the following questions:


Does anything stand out as suspicious?


Do the results match your findings in your time chart for signatures?



**Dashboard Analysis for Users with Bar, Graph, and Pie Charts**
Analyze your new dashboard results, and answer the following questions:


Does anything stand out as suspicious?


Do the results match your findings in your time chart for users?



**Dashboard Analysis for Users with Statistical Charts**
Analyze your new dashboard results, and answer the following question:

What are the advantages and disadvantages of using this report, compared to the other user panels you created?



**Apache Web Server Logs**


**Report Analysis for Methods**


Did you detect any suspicious changes in HTTP methods? If so which one?


What is that method used for?



**Report Analysis for Referrer Domains**


Did you detect any suspicious changes in referrer domains?


**Report Analysis for HTTP Response Codes**


Did you detect any suspicious changes in HTTP response codes?


**Alert Analysis for International Activity**


Did you detect a suspicious volume of international activity?


If so, what was the count of the hour it occurred in?


Would your alert be triggered for this activity?


After reviewing, would you change the threshold you previously selected?



**Alert Analysis for HTTP POST Activity**


Did you detect any suspicious volume of HTTP POST activity?


If so, what was the count of the hour it occurred in?


When did it occur?


After reviewing, would you change the threshold that you previously selected?




**Dashboard Analysis for Time Chart of HTTP Methods**
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-6.png" align="center" height="100%" width="100%" ></a>

Does anything stand out as suspicious?


Which method seems to be used in the attack?


At what times did the attack start and stop?


What is the peak count of the top method during the attack?



**Dashboard Analysis for Cluster Map**
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-7.png" align="center" height="100%" width="100%" ></a>

Does anything stand out as suspicious?


Which new city, country on the map has a high volume of activity?


What is the count of that city?



**Dashboard Analysis for URI Data**
Analyze your dashboard panel of the URI data and answer the following questions:
<a href="https://github.com/jcassiday/Splunk-Project/"><img src="https://github.com/jcassiday/Splunk-Project/blob/main/Images/splunk-apache-dashboard-8.png" align="center" height="100%" width="100%" ></a>

Does anything stand out as suspicious?


What URI is hit the most?


Based on the URI being accessed, what could the attacker potentially be doing?