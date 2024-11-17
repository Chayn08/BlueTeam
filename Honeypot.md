# Objective

The objective of this lab exercise is to set up a Cowrie honeypot with fake service banners to trick and trap attackers, and to analyze the traffic and tactics used by attackers.

Honeypots such as Cowrie are deployed by BlueTeam members across the network with the aim to trick attackers. Since these systems have no functional use, standard users or administrators have no reason to connect to them.

### Prerequisites

- Docker (if possible)
- The Cowrie honeypot software
  
### Part 1: Setting up the Cowrie Honeypot

- Install and configure the Cowrie honeypot software on a separate virtual machine on the network.
- Configure Cowrie to replace service banners with fake responses, by editing the cowrie.cfg configuration file (available in the resources on the right 👉) and adding the following section:
- Configure Cowrie to log all activity and send alerts when it detects suspicious behavior.
  
### Part 2: Monitoring and Analyzing the Cowrie Honeypot

- Monitor the Cowrie logs and alerts for any suspicious activity, such as attempts to log in or bruteforce attempts.
- Analyze the attack traffic to identify the tactics and techniques used by the attackers.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Part 1: Setting up the Cowrie Honeypot

Using docker or manual install to run cowrie from https://github.com/cowrie/cowrie

![image](https://github.com/user-attachments/assets/ccc13611-539a-4a9b-b20b-175da5b4c3b2)

## Part 2: Monitoring and Analyzing the Cowrie Honeypot

On a pentest machine, run the following ssh or telnet attempt commands

![image](https://github.com/user-attachments/assets/125d0654-57c0-4765-9864-42ee5b60fc0c)

Looking at cowrie logs, we can see that the attempted password worked and was logged.

Crownie will first log all the passwords that were used during the attempt such as asd and Thisisafakepassword.

Since this is a honeypot, it will allow attackers to log into the system without raising any alert.

![image](https://github.com/user-attachments/assets/75fec30b-8dbc-4409-8b30-b77de56ade07)

Same example with telnet logins:

![image](https://github.com/user-attachments/assets/4812abc1-693d-428f-803e-d251af635614)














