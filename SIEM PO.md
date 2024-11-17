# SIEM Powershell

Following the previous exercice, create a dedicated rule in order to detect the following command in Powershell.

## Materials Required:

- A Wazuh Cloud Account (trial versions are free for 14 days)
- A Windows machine for Wazuh client Agent
- The MITRE ATT&CK framework

## Lab Steps:

- Set up a Wazuh Cloud Account:
- Enable PowerShell Script Block Logging on your Workstation
- Create a Custom rule to detect a specific set of commands in Wazuh
- Execute the command and verify the alert details

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This correction is that of the creation of a custom Powershell rule which are to be carried out in an interactive way during the course.

- Go to your Wazuh environment

## Create a new Custom rule

- Go to the Management > Rules page
- https://<your tenant>.cloud.wazuh.com/app/wazuh#/manager/?tab=rules
- Inside the rule create a rule named Powershell-Jedha that will log scriptBlockText events and look for a specific term "Hello Jedha"
- Copy and paste the following xml code:

![image](https://github.com/user-attachments/assets/c78c0910-9ebc-496d-8187-b6f43e78bec7)

Save your new rule

## Enable Powershell logging on Windows using Powershell

- Before running the rule, you need to ensure that your Windows is logging Powershell commands. This can be enabled by default but in case it is not follow the following process :
- Use Powershell to execute the following commands in order to enable the policy

![image](https://github.com/user-attachments/assets/4b88f418-38c6-45bf-b475-25adf41fcb7b)

## Configure the agent to send the new logs

- Wazuh relies on an agent to send out logs. Now that Powershell logs are enabled, we need to ensure that the agent is sending these logs to the SIEM for analysis
- On your Windows workstation, go to : C:\Program Files (x86)\ossec-agent
- Open ossec.conf and add the following configuration at the end of the file

![image](https://github.com/user-attachments/assets/fb558c07-264c-4aca-ab41-70100a7c3691)

- Restart the agent using the binary located in :
- C:\Program Files (x86)\ossec-agent\win32ui.exe

## Execution

- Now that everything is set, open Powershell and run the command "Hello Jedha"
- Looking at your dashboard you'll find your new custom alert

![image](https://github.com/user-attachments/assets/535e7218-d690-4852-8954-84cdc3559c39)























