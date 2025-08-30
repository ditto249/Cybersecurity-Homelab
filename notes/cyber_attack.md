## Cyber Attack: Initial Access - Breached

<img width="1325" height="400" alt="image" src="https://github.com/user-attachments/assets/18ec6d3f-8b2a-41ee-a06a-67b7d59e3ca8" />
## The Attack Architecture
<img width="1077" height="736" alt="image" src="https://github.com/user-attachments/assets/b4d1b284-f98e-407c-8740-1bebe9d4c2d9" />

## The Scenario
In this lab, we are going to “simulate” each step by leveraging techniques and tool at our disposal. 

By leveraging default, insecure and outdated configurations and software, our attacker wants to use their skills for their own personal gain. These configurations, although outdated and disabled by default, can still often be found in business networks to this day.

### Reconnaissance
- Gather information.
- Understand the target’s systems, networks and environments to identify potential vulnerabilities or points of entry.
- Used to collect as much data as possible about the target without actively engaging or alerting the target. 

### Initial Access
- Seek to establish a foothold in the target network or system.
- Gateway for attackers to gain entry, enabling them to progress through subsequent stages of an attack, such as privilege escalation, lateral movement and data exfiltration.

### Lateral Movement
- Discover and navigate through a network.
- Gain access to additional systems, resources or data.
- It helps them maintain persistence, avoid detection and prepare for further actions like data exfiltration or ransomware deployment. 

### Privilege Escalation
- Increase their level of access within the environment.
- By obtaining higher privileges, such as  administrator or root access, adversaries gain greater control over the systems.
- Techniques include exploiting software vulnerabilities, misconfigured user accounts or password weaknesses.

### Data Exfiltration
- Extract valuable or sensitive information from  the compromised network.
- Transfer data such as intellectual property, customer records or financial information to an external location controlled by the adversary.
- Successful data exfiltration can result in significant reputational, operational and financial damage to the target. 

### Persistence
- Maintaining access.
- Ensures the attacker’s operations can continue despite interruptions.
- Often embedded deep in the system, such as registry modifications or startup scripts, to resist detection and removal. 

### Defence Evasion
- Cover tracks to maintain compromise.
- During compromise, stealthy attackers should cover up their tracks to hide their digital footprints.
- Logs, dropped files and packages are deleted.
- Disabled / uninstall security software.
- Obfuscating / encrypting / packing data and scripts.
- Process injection.
