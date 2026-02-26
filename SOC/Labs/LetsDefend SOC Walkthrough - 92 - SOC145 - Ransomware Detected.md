# LetsDefend SOC Walkthrough
# EventID: 92 - SOC145 - Ransomware Detected
```
EventID : 92
Event Time : May, 23, 2021, 07:32 PM
Rule : SOC145 - Ransomware Detected
Level : Security Analyst
Source Address : 172.16.17.88
Source Hostname : MarkPRD
File Name : ab.exe
File Hash : 0b486fe0503524cfe4726a4022fa6a68
File Size : 775.50 Kb
Device Action : Allowed
File (Password:infected) : Download
```

## Let's Start

First, let's download the file.

## Now Let's Check It in VirusTotal

![alt text](../Assets/92SOC145/1.png)

As you can see, when we upload the ZIP file, only two antivirus engines mark it as suspicious.

I think we should check it inside an isolated VirtualBox environment by extracting the file and uploading it to VirusTotal again.

![alt text](../Assets/92SOC145/2.png)

* Now let's upload the extracted file to VirusTotal.

![alt text](../Assets/92SOC145/3.png)
![alt text](../Assets/92SOC145/4.png)

It is ransomware!

## Now Let's Start the Playbook

![alt text](../Assets/92SOC145/5.png)

## Now Let's Check If the Malware Is Quarantined

![alt text](../Assets/92SOC145/6.png)

The logs do not show anything. Let’s check the endpoints.

![alt text](../Assets/92SOC145/7.png)

It shows that the file was executed on the MarkPRD device.

## Contain the Device

![alt text](../Assets/92SOC145/8.png)

## Select Not Quarantined

![alt text](../Assets/92SOC145/9.png)

## Select Malicious

![alt text](../Assets/92SOC145/10.png)

## Select Accessed

![alt text](../Assets/92SOC145/11.png)

## Add Artifacts

![alt text](../Assets/92SOC145/12.png)

Add notes:

On May 23, 2021, at 07:32 PM, an alert was triggered indicating potential ransomware activity.

After conducting a thorough and detailed investigation, the alert was confirmed to be a true positive.  
The analysis verified that the file exhibited ransomware behavior and posed a legitimate security threat.

Immediate incident response actions were taken, including isolating and containing the affected device to prevent further spread within the network. Appropriate remediation steps were then initiated to mitigate the impact of the ransomware.

## Submit as True Positive

![alt text](../Assets/92SOC145/13.png)

# END