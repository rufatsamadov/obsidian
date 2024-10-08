Kerberoasting is a sophisticated post-compromise attack technique that targets service accounts within Microsoft Active Directory environments. This method is particularly effective because it allows attackers to extract password hashes of service accounts, which are often highly privileged and have access to sensitive data.

By leveraging the Kerberos authentication protocol, attackers can request service tickets for accounts with Service Principal Names (SPNs). These tickets are then used to obtain the password hashes, which can be cracked offline. Once the plaintext credentials are obtained, the attacker can impersonate the service account, gaining unauthorized access to critical systems and data.

## How does Kerberoasting Work?

Kerberoasting operates by exploiting the Kerberos authentication protocol, specifically targeting service accounts with Service Principal Names (SPNs). The attacker first compromises a domain user account, which is then used to request a service ticket from the Ticket Granting Service (TGS). This service ticket is encrypted with the hash of the service account's password.

Once the service ticket is obtained, the attacker extracts the ticket's hash and proceeds to crack it offline using tools like Hashcat or John the Ripper. This offline cracking process is crucial as it allows the attacker to avoid detection by security systems that monitor network traffic and user activity. The cracked password hash can then be used to impersonate the service account, granting the attacker unauthorized access to network resources.

## What are Examples of Kerberoasting?

Examples of Kerberoasting attacks highlight the technique's effectiveness in real-world scenarios. One notable instance is the **Operation Wocao**, where threat actors used PowerSploit’s Invoke-Kerberoast module to request encrypted service tickets and brute-force the passwords of Windows Service Accounts offline. This allowed them to authenticate as service accounts on other systems within the network, facilitating further malicious activities.

Another significant example is the **Solorigate Backdoor Incident**, where APT29 threat actors obtained Ticket Granting Service (TGS) tickets for Active Directory Service Principal Names (SPNs) and cracked them offline. This method enabled unauthorized access to sensitive systems and data. Similarly, the **FIN7 Threat Group** utilized Kerberoasting to extract service tickets and crack passwords, allowing them to move laterally within the network and access critical credentials.