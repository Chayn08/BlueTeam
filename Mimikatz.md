# Mimikatz Protection Exercise

Mimikatz is a tool that can extract plaintext passwords, hashes, and other sensitive information from memory on a Windows system. In this lab exercise, we will focus on securing a system from Mimikatz attacks and testing the hardening by attempting to recover a user's password before and after applying the security measures.

By completing this lab exercise, you will have gained valuable experience in understanding Mimikatz attacks and applying security hardening measures to prevent them.

You will also have learned how to test the effectiveness of the hardening measures by attempting to recover a user's password before and after applying the security measures. This lab will give you a better understanding of how to protect your systems from Mimikatz attacks and how to test the effectiveness of your security measures.

## Objectives:
The objectives of this lab are to:

Learn the common techniques used to prevent Mimikatz attacks
Apply security measures to protect against Mimikatz attacks on a test environment
Test the effectiveness of the security measures by attempting to recover a user's password before and after hardening

## Requirements :
To successfully complete the lab you will need:

A virtual or physical test environment with a Windows system
Mimikatz tool : https://github.com/gentilkiwi/mimikatz/releases/
Security hardening tools (e.g. EMET, LSA Protection, Credential Guard, etc.)

## 1. Lab Steps 🔬

Perform a Mimikatz attack:
Perform a Mimikatz attack on the Windows system and extract the password of a user account. If you only have a user based on your microsoft account you should only be able to retrieve the mail address.
Document the steps taken to perform the attack and extract the password
Apply security hardening measures:
Research and apply security hardening measures to protect against Mimikatz attacks (e.g., LSA Protection, Credential Guard, etc.)
Document the steps taken to apply each hardening measure
Test the hardening measures:
Attempt to recover the same user's password after applying the security hardening measures
Document the steps taken to attempt to recover the password
Evaluate the effectiveness of the hardening measures:
Compare the steps taken to recover the password before and after the hardening measures were applied
Determine if the hardening measures were effective in preventing the Mimikatz attack
Evaluate the effectiveness of each individual hardening measure

--------------------------------------------------------------------------------------------------------------------------------------

This correction is that of protection from Mimikatz attakcs which are to be carried out in an interactive way during the course.

We consider that the tested machine is not hardened and does not have WDigest disabled

Testing Mimikatz without hardening:

Download and run Mimikatz as administrator.

Run the following commands to attempt to extract passwords from the memory

![image](https://github.com/user-attachments/assets/7951ca41-7479-4393-a90f-bbacfeff86fd)

If the system is not hardened we can gather the user password in cleartext

![image](https://github.com/user-attachments/assets/7ed36882-2e43-4df9-b170-6e3eca648d78)

### 2.0 Disabling Wdigest

Powershell Command:

![image](https://github.com/user-attachments/assets/e384e823-2848-4ee1-9847-b38252a90a9e)

![image](https://github.com/user-attachments/assets/1be43597-7457-4dff-85f4-0837a60682ff)

### 2.1. Enabling LSA Protection
Registry Edit:

Open the Registry Editor and navigate to HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa
Create a new DWORD value named RunAsPPL and set its value to 1

Or PowerShell Command:

![image](https://github.com/user-attachments/assets/f7126f3b-7602-4f35-ba8b-099967902727)

### 2.2. Disabling Clear-Text Password Storage
Group Policy Command:

Open the Registry Editor and navigate to HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa
Modify the DWORD value named NoLmHash and set its value to 1

PowerShell Command:

![image](https://github.com/user-attachments/assets/6dd19458-fa11-4cf0-8c90-68b11c676e2f)

### 2.3. Enabling Credential Guard
Group Policy Command:

Open the Registry Editor and navigate to HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\DeviceGuard
Modify the DWORD value named EnableVirtualizationBasedSecurity and set its value to 1

PowerShell Command:

![image](https://github.com/user-attachments/assets/fa41cd39-98e8-4413-81a5-a844951c2b14)

### 2.4. Disabling Remote Credential Guard:
Group Policy Command:

Open Group Policy Editor and navigate to Computer Configuration > Administrative Templates > System > Credential Delegation
Enable the Disallow delegation of fresh credentials with NTLM-only server authentication policy

PowerShell Command:

![image](https://github.com/user-attachments/assets/69231108-5412-4250-bf1f-b688d157b64f)

### Re-execute Mimikatz

After executing Mimikatz, we can see that the password is no longer stored in memory and thus extracted using Mimikatz.

![image](https://github.com/user-attachments/assets/a8e549ab-bcda-4312-b81f-267dd42941d6)







