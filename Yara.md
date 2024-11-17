# Yara

To prevent the malware from spreading to other machines in the network, you decide to create a YARA rule to add it to the antivirus.

You decide to scan the malware to create your YARA rule, and you notice the following information:

- The malware is written in C#,
- The malware retrieves data from the clipboard every 10s,
- The malware exfiltrates these data to a .ru site (ex: http://c2server.ru) OR to a .cn site (ex: http://c2server.cn),
- The character string V\x02j\x02k\x02q\x02 is present in the malware.

Search for ways to detect the information you found out about the malware and complete the following YARA rule:

![image](https://github.com/user-attachments/assets/921c49f5-b00a-4712-8f54-83dfe75e8f2a)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![image](https://github.com/user-attachments/assets/a4cb9486-dbe6-499b-b598-87c06ba71ef2)

As you can see, we have used the strings we found during the analysis of the malware to create our YARA rule.

- $clipboard = "Clipboard.GetText": We have used the string Clipboard.GetText to detect the malware's behavior of retrieving data from the clipboard.
- $tld1 = ".ru" and $tld2 = ".cn": We have used the strings .ru and .cn to detect the malware's behavior of exfiltrating data to a .ru or .cn site.
- $text = "V\x02j\x02k\x02q\x02": We have used the string V\x02j\x02k\x02q\x02 to detect the malware's behavior of exfiltrating data to a .ru or .cn site.
