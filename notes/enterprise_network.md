# A business network
Constructing this business network helped me to learn skills while building more on the foundations that I learned from my previous projets.
** Realistic Training Environment:** By building a business network, it allowed for me to practise cybersecurity skills while in a safe environment which closely resembling a professional setting.
** Skill Development:** I got to learn tools likes SIEMs, vulonerability scanners and packet analysers in a network context.
** Incident Response Practise:** I simulated incidents such as unauthorised access helped to provide valuable experience in real-time response.

The fake enterprise that I developed with the guide was called **ProjectX**. Acompany that builds software for consumers and it is windows-native.

The Network details were:
<img width="1175" height="920" alt="image" src="https://github.com/user-attachments/assets/7c077c08-9315-41bc-8707-4dfcad83860f" />

## Microsoft Active Directory
Microsoft's directory service to manage and organise resources in the network.
This was the place that will act as the centralized database to authenticate and authorise users and devices, making it the lifeline and backbine of the enterprise environment.
### Key Components:
- **Authentication:** Verifies user identity using credentials like username and password.
- **Authorisation:** Grants or denies access to the network resources based on permissions.
- **Centralized Management:** Centralizes control over users, computers and other resources.

<img width="1450" height="356" alt="image" src="https://github.com/user-attachments/assets/721c1086-547d-464d-bda2-9beb7845d44f" />

### Security Implications
Active Directory's are the prime target for attackers because it is the central role for managing all the enterprises's netwrok resources.
### Common Security Threats:
- **Credential Theft:** Techniques like pass-the-hash or Kerberoasting can allow attackers to escalate privileges.
- **Privilege Escalation:** Exploiting misconfigured permissions to gain higher access levels.
- **Lateral Movement:** Once inside, attackers can move through the network using AD to identify valuable targets.

## Connecting to Active Directory
<img width="1276" height="451" alt="image" src="https://github.com/user-attachments/assets/f277cd2c-5fe5-42a4-bfb0-a98d225b9b88" />
### End state
<img width="1483" height="568" alt="image" src="https://github.com/user-attachments/assets/e2bd9d08-1f03-4195-9ffd-08dcd48f8823" />

## A Dedicated Server
Business and enterprise environments will have dedicated servers for different purposes, a server empowers the backend processing of user and service requests.
There are many different types of servers, but we used a Jumpbox for this one.
A Jumpbox server is a server that acts as an entry point into an isolated environment. Jumphosts can be used as a security mecahnism to restrict access to the internal environment.

## Jumpbox
We used a jumpbox server, the corp server, where this server you will be able to provision and access other types of services such as FTP, DNS and email (SMTP)
<img width="817" height="600" alt="image" src="https://github.com/user-attachments/assets/24083812-8114-434f-84c6-dc3230cc05a3" />
For this lab, we could have used more VM's for the FTP, DNS or SMTP, but that would have been very resource heavy and would be a lot more work, so instead they would be containers using Docker Engine.
<img width="834" height="492" alt="image" src="https://github.com/user-attachments/assets/4a1a5fc7-9624-4a51-a456-77ed7adf5e46" />
### Common Security Threats:
- **Single point of failure:** If compromised, the jumpbox can provide access to the entire internal network it protects.
- **Lateral Movement:** If lateral movement protections (e.g. firewall rules, endpoint detection) are weak, attackers can move from the jumpbox to other interal systems.
- **Lack of Monitoring:** If session activity, command history, or file transfers are not logged or monitored, malicious actions may go unnoticed.

## Email Server with MailHog
An email server is designed to send, receive, store and manage email communications for users. Even though they are less common as enterprises will use Microsoft Exchange to handle their email needs, running a email server will give good insight into how email works and why it's important to secure email gateways.
### Email Server Architecture
MailHog: A lightweight email testing tool that acts as a fake SMTP server. It captures all outgoing emails applications, without delivering them to real inboxes.
<img width="1025" height="493" alt="image" src="https://github.com/user-attachments/assets/cbc16f23-f9b0-4ec6-b2d5-b9f0d7637d1a" />
### Common Security Threats:
**Open relay Exploitation:** If improperly configures, the server can be used by spammers to send large volumes of emails, damaging IP reputation.
**Brute Force Attacks:** Attackers often attempt to compromise accoutns via brute force or credential stuffing.
**Spam and Phishing:** Attackers may spoof your domain or use your server for phishing campaigns.
**Data Breaches:** Poorly secured servers can expose sensitive email nad user credential.
**Malware Delivery:** The server could inadvertently become a vehicle for spreading malware if attachments are not scanned.

## Security Server with Wazuh
A dedicated security server for ensuring performance, security and scalability to monitor and analyse the stack. 
**Performance Isolation**: Running resource-intensive tools on a dedicated server prevents performance degradation caused by competing workloads on shared resources. Each application demands significant CPU, RAM, and disk I/O to function efficiently
**Enhanced Security**: Security tools process sensitive data, including logs and vulnerability scans. A dedicated server minimizes the attack surface by isolating these critical processes from unrelated systems.
**Centralized Management**: A dedicated server simplifies monitoring and management, providing a single point for handling logs, alerts, and vulnerability data, which improves efficiency and reduces administrative overhead. We will be using a few closed and open-source security tools to monitor, detect, and prevent our simulated “attacks”.

## Wazuh 
Wazuh is an open source platform that gives both extended detection responses (XDR) and System Information Event Management (SIEM) to protectr cloud, container and server workloads.
**XDR**
- XDR is a defensive approach.
- Data is collected and aggregated into a platform from data sources such as workstations, servers, cloud environments, and network devices.
- XDR provides improved detection, investigation, and response to threats by centralizing all data to identify patterns, trends, and analyze malicious activity.
**System Information and Event Management (SIEM)**
- A system that provides log management, threat detection, and incident response capabilities.
- Wazuh acts as a SIEM solution by collecting and analyzing security data from multiple sources, detecting threats in real time, and facilitating efficient incident response.

### Security Server Architecture
<img width="1462" height="477" alt="image" src="https://github.com/user-attachments/assets/97bb08e2-69f9-47c6-9b7e-92cdbfe8e91e" />

### Security Implications
Running an XDR and SIEM services provides significant advantages to monitor, detect, prevent and respond to security-related activity.
### Common Security Threats:
- **Threat Detection:** Detect malicious activities such as brute-force attacks, privilege escalation, and suspicious login attempts.
- **Proactive Defense:** Collects and analyzes endpoint data to detect advanced threats like fileless malware, lateral movement, and ransomware activities.
- **Incident Response and Investigation:** Configured to automatically trigger responses (e.g., blocking an IP address or executing scripts to quarantine infected machines), significantly reducing the time between detection and mitigation.
- **Centralized Security Management:** Aggregates data from multiple sources (network, endpoint, and cloud), providing a centralized security management platform.
- **Threat Hunting:** analysing anomalies in system and network behaviour.
