# Implement a SIEM

Deploy your own SIEM using Wazuh Cloud or Wazuh VM and Detect known attacks using the MITRE Method! Also detect bruteforce attacks on your Windows Workstation!

## The objectives of this lab are to:

- Understand the basics of SIEM and its role in cybersecurity
- Learn the features and functionality of Wazuh
- Implement a SIEM using Wazuh on a test environment
- Understand the MITRE ATT&CK framework and its use in detecting known attacks
- Use the MITRE ATT&CK framework to detect known attacks in the test environment using Wazuh

## Materials Required:

- A Wazuh Cloud Account (trial versions are free for 14 days) or a Wazuh Virtual Machine.
- A Linux or Windows machine for Wazuh client Agent

## Lab Steps:

1. Set up a Wazuh Cloud Account:

- Go to : https://console.cloud.wazuh.com/sign-up?landing=trial

Or set up the Wazuh VM:

- Download the VM here (OVA file)
- Import the OVA to the virtualization platform.

If you're using VirtualBox, set the VMSVGA graphic controller. Setting another graphic controller freezes the VM window.

Select the imported VM.

Click Settings > Display

In Graphic controller, select the VMSVGA option.

- Start the machine.

Access the virtual machine in terminal using the following user and password. You can use the virtualization platform or access it via SSH. (Be carefull it's a QWERTY keyboard)

![image](https://github.com/user-attachments/assets/653ac366-5f95-4e29-9916-3275addd66f0)

Shortly after starting the VM, the Wazuh dashboard can be accessed from the web interface by using the following credentials:

![image](https://github.com/user-attachments/assets/9efe987e-eee4-45f8-8761-c9ae380264ca)

- Configure Wazuh to collect logs from the system(s) to be monitored
- Set up the Wazuh dashboard for visualization

2. Trigger an Alert:

- Create a new user
- Record the log data generated during the attacks
- Wazuh also provides sample data to review and understand how SIEM system detect alerts based on logs and events

3. Analyze log data using Wazuh:

- Use Wazuh to analyze the log data generated

------------------------------------------------------------------------------------------------------------------------------------------------------

This correction is that of the deployment of a SIEM which are to be carried out in an interactive way during the course.

- Go to https://console.cloud.wazuh.com/console/new-environment to create a new environment. Chose the minimum requirements.
- To create the environment you only need a name. Use Jedha as a company name.

Or follow the guide in the exercise to install the virtual machine

![image](https://github.com/user-attachments/assets/4de434e0-38f4-4662-bbc4-b186e626e4a0)

Once configured, login to the your dedicated platform. The login credentials are provided by Wazhu after deployment

![image](https://github.com/user-attachments/assets/913e85e6-b8e1-4f07-8bb5-d60a867225c1)

First thing is to deploy a new agent. Click on "Add Agent"

![image](https://github.com/user-attachments/assets/e0ee1b76-252d-4732-9f03-9f966d8dc8b3)

Chose the type of agent to install. Either Windows or Linux in most cases. Wazuh will provide the installation scripts

![image](https://github.com/user-attachments/assets/71262414-7e8f-468c-bf39-f7a46b99b061)

Copy paste the script into terminal for Linux or Powershell for Windows. Make sure to run the command with administrator priviliges. Then run the service

![image](https://github.com/user-attachments/assets/46386cc7-b308-4299-bfe4-d26abc59132b)

On Wazuh dashboard you'll then be able to see the new machine connected. For ease of use Wazuh provides sample data in Settings. To help students get some data, add sample data to their dashboard

![image](https://github.com/user-attachments/assets/6c28cca3-7ea9-4cbb-97c3-868e526ee7ba)

Once live, you'll be able to locate your machine with the different dashboards provided by Wazuh

![image](https://github.com/user-attachments/assets/b27eed8c-f68e-42ba-a83a-bdc831048ee3)

The Mittre Dashboard will also be useful for stutdents to visualise how SIEMs classify attacks by Attack TTPs.

![image](https://github.com/user-attachments/assets/fd328fcb-3603-4003-8141-716f36dc3d08)

## Detecting new events

Create a new user in your Windows System. For example:

![image](https://github.com/user-attachments/assets/02d78ede-73a9-4e1c-9e27-271eafd271df)

Going back to Wazuh, go to the security dashboard and check for recent alerts
















