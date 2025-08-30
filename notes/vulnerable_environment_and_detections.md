## Vulnerable Environment
Attackers will leverage insecure and default configurations to their advantage. Their are many vulnerabilites that a attacker will use. From insecure software, legacy systems and default configurations. 

In ProjectX, we have purposely left the default configurations, we left the ssh port 22 open and create an insecure password for it. We gained access to a workstation by using MailHog to our advantage and sent an phishing email to a client, to get there information. Various ways to keep it vulnerable for the purpose of testing.

For detection, we created three alerts in Wazuh, one for file integrity, one for failed SSH attempts and one for winRM logons, so we know if anyone has tried breaching the enterprise.
### Vulnerable Architecture 
<img width="1176" height="798" alt="image" src="https://github.com/user-attachments/assets/9016d677-0a8e-46c6-92c3-c50f45923c82" />

