# System Protection Exercise

## Objectives

You've been asked to provide a secure Windows system that would be used in a corporate environement.
Attempt to implement the L1 security measures from the CIS benchmark for Windows.

## Prerequisites

A Windows system (Windows 10 or higher)
Administrative access to the Windows system

Instructions:

Download and install the CIS Benchmark for Windows.
Review the CIS benchmark guidelines and recommendations.
Implement the following security recommendations:
Set a strong password policy for all user accounts.
Disable guest account and rename the default administrator account.
Enable the Windows firewall and configure it to block all incoming connections except for required services.
Disable unnecessary services and protocols, such as Telnet and FTP.
Enable Windows Defender or install an antivirus software that meets CIS recommendations.
Configure User Account Control (UAC) settings to always notify users when changes are made to the system.
Enable BitLocker or a similar full-disk encryption software for protecting data at rest.
Configure Windows Update to automatically install security updates.
Verify that the security recommendations have been implemented correctly.
Test the system to ensure that it is still functional after the security changes have been made.
Document the changes and create a report on the security status of the Windows system.
Test out the effectiveness of the configurations using CIS-CAT lite. CIS-CAT is an assessment tool provided by CIS in order to evaluate the security parameters on a system. The light version is free to download and use.
Go to https://learn.cisecurity.org/cis-cat-lite, and sign-up for CIS-CAT lite.
An email will be sent out with the executable files
Run CIS-CAT lite on your Windows workstation

![image](https://github.com/user-attachments/assets/3ab05e7a-9409-431d-9f01-16d6fdf89a74)

Select the appropriate benchmark to your system

![image](https://github.com/user-attachments/assets/f02c31d8-cc71-4240-871a-b14172b931bf)

Following the analysis, analyse the generated report to evaluate the current security level of your system

![image](https://github.com/user-attachments/assets/5b7e62fc-dc2c-4c3b-86a6-b721519a5e82)

----------------------------------------------------------------------------------------------------------------------------------------

# Hardening the system

Visit the CIS website and download the latest version of the CIS benchmark for Windows

Implement the following security recommendations:

Password Policy:

- Open the Local Security Policy editor by typing secpol.msc in the Run dialog box (Win + R).
- In the left pane, navigate to Security Settings > Account Policies > Password Policy.
- Set a minimum password length of characters.
- Set the password expiration.
- Enable password complexity and history.
- In the left pane, navigate to Security Settings > Account Policies > Account Lockout Policy.
- Set account lockout duration to 15 minutes and the account lockout threshold to 5 invalid login attempts.

![image](https://github.com/user-attachments/assets/8c689c29-08eb-489e-aaba-f00881dfc6aa)

Guest Account and Administrator Account:

Disable the guest account by typing net user guest /active:no in an elevated command prompt.

![image](https://github.com/user-attachments/assets/86c627d5-13d4-4818-956f-01f3afdfd6b7)

Rename the default administrator account by typing : net user administrator "New Name" in an elevated command prompt.

![image](https://github.com/user-attachments/assets/968671c2-4cf5-4dbd-b84a-161c31c7e03a)

Firewall Settings:

- Open the Windows Defender Firewall with Advanced Security by typing wf.msc in the Run dialog box (Win + R).

- Click on Inbound Rules in the left pane and select New Rule.

- Select the Port option and click Next.

- Choose the TCP option and specify the port numbers for the required services (e.g., 80 for HTTP, 443 for HTTPS).

- Select the Block the connection option and click Next.

- Choose the Domain, Private, and Public options and click Next.

- Name the new rule and click Finish.

- Repeat this process for all required services. Services and Protocols:

- Disable unnecessary services and protocols by typing services.msc in an elevated command prompt and stopping the services or disabling them.

![image](https://github.com/user-attachments/assets/a9063cd7-f176-4a9a-b3ad-e73b899245d9)

Windows Defender:

- Enable Windows Defender by typing Windows Security in the Start menu and selecting Virus & threat protection.
- Click on Manage settings and enable Real-time protection.
- Scan the system for malware and threats.

![image](https://github.com/user-attachments/assets/2208827c-1b97-4f5a-bc2a-7d93ec928257)

User Account Control:

- Configure User Account Control (UAC) settings by typing UAC in the Start menu and selecting Change User Account Control settings.
- Set the notification level to Always notify.

![image](https://github.com/user-attachments/assets/13ac4f3b-567d-4c43-8345-5d976f55c1b5)

Full-disk Encryption:

- Enable BitLocker by typing BitLocker in the Start menu and selecting Manage BitLocker.
- Follow the prompts to encrypt the system drive or other drives.

![image](https://github.com/user-attachments/assets/4031643f-435d-472c-9817-ad205c464fb4)

Windows Update:

- Configure Windows Update to automatically install security updates by typing Windows Update in the Start menu and selecting Check for updates.
- Click on Advanced options and select the option to automatically install updates.

![image](https://github.com/user-attachments/assets/d3293d23-f90e-4aeb-a923-76e121112ad1)

### Automate hardening

Amongts other tools, HardeningKitty has published build scripts to secure Windows systems following the CIS Benchmark :

- HardeningKitty Repo and Installation Guide : https://github.com/scipag/HardeningKitty

![image](https://github.com/user-attachments/assets/6f22d0df-f73a-4fc7-a65d-769022a03a4a)
![image](https://github.com/user-attachments/assets/a663b899-ac9b-49b9-8d99-d11e7b139af8)
![image](https://github.com/user-attachments/assets/bf138bd2-403d-4dc2-9af1-60f0aca2d026)
![image](https://github.com/user-attachments/assets/610a30dd-d221-4617-80f3-b10e1a5d5040)

### Executing CIS-CAT Lite to evaluate the effectiveness of the parameters
Final step is using CIS-CAT to evaluate the parameters we've just assigned.

- Go to https://learn.cisecurity.org/cis-cat-lite, and sign-up for CIS-CAT lite.
- An email will be sent out with the executable files
- Run CIS-CAT lite on your Windows workstation

![image](https://github.com/user-attachments/assets/8f6b8557-9092-49a3-b497-f36dadff4da6)

Select the appropriate benchmark to your system

![image](https://github.com/user-attachments/assets/7915fd2f-5bbb-4a34-837b-c38b7840a94c)

Following the analysis, analyse the generated report to evaluate the current security level of your system

![image](https://github.com/user-attachments/assets/56ba4a0b-d6cd-4962-b7f8-6398606ea9cb)




