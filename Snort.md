# Detecting Network Scans Using Snort

### Objective

The objective of this lab exercise is to use Snort Intrusion Detection System to detect network scans on a network and identify the source of the scans. Try detecting an nmap network scan to identify the source.

### Instructions

- Install and configure Snort on your Kali.
- Create a new rule to detect network scans. The rule should include the IP address range to scan and the ports to be scanned.
- Configure Snort to log alerts to a file or database.
- Install and configure a second virtual machine to perform the network scans.
- Use a scanning tool like Nmap to scan the target IP address range and ports.
- Check the Snort logs to confirm that the scans were detected.
- Analyze the Snort alerts to identify the source of the scans.

### Key Takeaways

- Snort is an open-source intrusion detection system that can be used to detect network scans and other types of network-based attacks.
- Rules can be created to customize Snort to detect specific types of attacks.
- Monitoring Snort alerts can help identify security incidents and prevent data breaches.
- Network scans are a common reconnaissance technique used by attackers to identify vulnerable systems on a network.
- Analyzing the source of network scans can provide valuable information about the attacker and their motives.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Part 1: Installing Snort

For Kali use the following command (we recommand you to use a distinct VM to install it):

1. Backup Kali's sources.list:

![image](https://github.com/user-attachments/assets/7d87a435-9ce8-408c-a68f-06fae0f9daf4)

2. Remove updates:

![image](https://github.com/user-attachments/assets/af4d9d75-9ac7-43ce-b0ca-13b24e5510eb)

3. Change sources.list content:

![image](https://github.com/user-attachments/assets/db34d8fb-abf7-45cb-a036-6f6f9dececff)

Paste content given below:

![image](https://github.com/user-attachments/assets/36d60ed3-4ceb-48ce-b823-bae79fbd5633)

If you are using Kali as a virtual machine then paste this instead, as core Ubuntu repositories do not have the ARM repositories in them:

![image](https://github.com/user-attachments/assets/2b5fc0a7-c30b-4e3e-801b-bc64daf5a4ec)

4. Add the specified public keys:

![image](https://github.com/user-attachments/assets/42718c4f-022a-4ee5-bf58-9ad4ed7ec63a)

5. Update:

![image](https://github.com/user-attachments/assets/fbf498ef-0f5e-4a43-ac51-9e78769fd4e0)

6. Now install Snort:

![image](https://github.com/user-attachments/assets/910b82e0-0491-4852-abb3-0e8be25381dc)

### Part 2: Configuring Snort

Go to /etc/snort/rules and edit the file local.rules to enable rules for detecting network scans.

Add the following rule at the end of the file:

![image](https://github.com/user-attachments/assets/bcc9c2cc-cdde-4fa5-9325-a15c6c28c0d2)

Save and close the configuration file.

### Part 3: Starting Snort

Open a terminal or command prompt on your system.
Start Snort with the following command:

![image](https://github.com/user-attachments/assets/4471e403-a6ea-4118-8a4b-60ee942b19f4)

Snort will start listening for network traffic. You can specify -W to see all interfaces and -i to specify a specific interface.

### Part 4: Analyzing Snort Alerts

Generate network traffic that includes a network scan.

![image](https://github.com/user-attachments/assets/719c450e-f0ca-488d-b5f2-54d243cac9fb)

Check the Snort console for alerts.

If Snort detects a network scan, it will display an alert with the message "Possible network scan detected".

![image](https://github.com/user-attachments/assets/3ae06f6d-d64b-4032-9ce6-65bc27e797ef)

Review the output to identify the source of the scan.

Use the information from the alert to determine if the host is conducting a network scan or if it has been compromised.

### Part 5: Stopping Snort

To stop Snort, press CTRL+C in the terminal or command prompt where Snort is running.
When everything is done, dont forget to set back default Kali's sources.list:

![image](https://github.com/user-attachments/assets/b882356b-8002-4487-8066-45c4562a1b4f)






