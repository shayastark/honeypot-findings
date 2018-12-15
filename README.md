# honeypot-findings


  I deployed three intentionally vulnerable web applications and studied the activity as they gained the attention of attackers around
the world. I setup and monitored these honeypots using the open source project, Modern Honey Network (MHN) and used Amazon Web Services (AWS) to host 
my admin and honeypot virtual machines. Additionally, I used GaurdDuty, an AWS service, to monitor suspicious activity related to my 
Electronic Cloud Compute (EC2) instances.
  MHN's architecture comes with many options for deploying different types of honey pots and analyzing
attack signatures from unique IP addresses. I installed the MHN server on my admin VM and each honeypot on its own VM. The honeypots are refered
to as "Sensors" and record ingress information realting to the IP address hosting the honeypot. I installed and deployed the Dionaea, Shockpot
and Snort, using a script that became available after selecting the desired honeypot. Moments after deploying, I noticed attacks coming in from Lithuania,
China, Ukraine and other countries. The map on my admin dashboard lit up, noting the location and source IP of each attack to my honeypots.

Things I noticed: 
                   The top five attacker's IP addresses originated from Lithuainia, Hong Kong, USA, Taiwan, and China.
                   The top attack signatures were Dshield Block Listed Source group, Suspicious inbound to MSSQL port 1433, and Active Threat Intelligence Poor Reputation IP TCP group 92, 97 and 24.
                   At the time of writing this, the honeypots were attacked 4,205 times in 24 hours.
                   The Dionaea honeypot was attacked 2,346 times, Snort 1,115 times, and Shockpot 744 times in 24 hours.
                   The most attacked ports were 80 (http), 445 (AD, SMB file sharing), 1433 (MSSQL server), 3306 (MySQL database system) and 23 (Telnet).
                   Understanding what attracts attackers and becoming aware of popular attack trends will be an on going study process throughout my career. I understand the importance of real world practice, using the tools we're learning about.
                   This project strengthened my security awareness, relating to vulnerable open ports, database exfiltration, and application security management from a networking perspective.
                  
                  
** UPDATE: Out of curiosity, I left the honeypots running for approximately 7 hours after submitting this write up and noticed there were a total of >34,00 attacks accumulated, close to 30,000 more than prior. The attack signatures don't seem to differ too much from what I saw before. I do see that different source IPs are trying consecutive port scans for longer periods of time. I will export the collected data a second time and upload the JSON file for those who wish to analyze the data further.
