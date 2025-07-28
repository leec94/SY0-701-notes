# SY0-701-notes
Notes on CompTIA Security+ SY0-701 exam, covering gaps in my knowledge from various practice exams.

## Overview 

*Domains*
- General security concepts
- Threats, vulnerability, and mitigations
- Security architecture
- Security operations
- Security program management and oversight

### General security concepts
Concealment types
- Tokenization: the process of substituting a sensitive data element with a non-sensitive equivalent, referred to as a token. The token and the data it substitutes are stored in a secure database. If the original data is needed, it can be accessed using the token and querying the database. The token will be a different size and have a different structure than the original data so the token can’t be used to decipher the original data.
- Steganography: the practice of concealing a file, message, image, or video within another file, message, image, or video
- Data masking: a method to de-identify some or all characters in a sequence, but not changing the total number of characters that a field should contain. The masked version will be structurally the same, but the data will be hidden. Changing the letters or numbers entered into a password field with dots is an example of data masking. Data that is masked will have the same number of characters as the original data, not a smaller set
- Encryption: the process of converting information or data into a code to prevent unauthorized access. It often uses an algorithm to replace the original data with other data. If a person figures out or acquires the algorithm, the data can be decrypted

### Threats, vulnerability, and mitigations
Malware types
- Logic bomb: executes a malicious action when a specific condition or trigger is met, such as a date, time, or event
- Ransomware: encrypts the data or files on a system and demands a ransom for their decryption or restoration
- Trojan: disguises itself as a legitimate or benign program, but performs malicious actions when executed.
- Worm: self-replicates and spreads to other systems or networks without user interaction

Password attacks
- Spraying: trying common passwords against multiple accounts, hoping to find a match
- Brute force: involves trying all possible combinations of characters until the correct password is found

Cryptographic attacks
- Birthday attack: type of cryptographic attack that involves finding two different inputs that produce the same output for a hashing algorithm
- Downgrade attack: forcing a communication channel to use a weaker encryption algorithm or protocol, making it easier to decrypt or intercept

Backup types
- Image backup: duplicates an OS installation, either from a physical hard disk or a VM's virtual hard disk. It offers a quick means to redeploy the system without reinstalling software and settings
- File-level backup: copies individual files and directories
- Incremental backup: saves only the changes made since the last backup
- Differential backup: saves all changes made since the last full backup

### Security architecture
- Proxy server: stands between the user's computer and the internet, intercepting requests and potentially reducing the public-facing attack surface by masking the internal server
- Jump server: used as a bridge to connect to other servers or networks in separate security zones
- Real-time Operating System (RTOS): an operating system where the processes running are deterministic and prioritize performance, used on devices like industrial equipment and automobiles. \[[Ref](https://www.professormesser.com/security-plus/sy0-501/embedded-systems/)\] 
  
### Security operations
Types of web filters
- Agent-based web filters: installed directly on the end-user's device, ensuring that the filtering policy is enforced consistently, whether the user is on the corporate network or working remotely \[[Ref](https://www.professormesser.com/security-plus/sy0-701/sy0-701-video/web-filtering-sy0-701/)\]
- Web security gateway filters: or Unified Threat Management (UTM) device, is a device that filters unsafe content from web traffic, and block risky or unauthorized user behavior. Contains URL filtering, anti-malware detection and blocking, and application control. Also has featues such as firewall, intrusion prevention, and antivirus. Runs on proxy servers or on-prem or in the cloud. \[[Ref](https://www.cloudflare.com/learning/access-management/what-is-a-secure-web-gateway/)\]

Network Access Control: enforces policies that determine which devices are allowed to access the network, and what resources they can access once they're connected \[[Ref](https://www.professormesser.com/security-plus/sy0-501/network-access-control-4/)\]
- Agent-based NAC: requires an agent to be installed on every device. Is able to get more detailed information about the device requesting access to the network, and provides continuous monitoring \[[Ref](https://s3msecurity.com/agent-based-or-agentless-which-should-be-preferred/)\]
- Agentless NAC: does not require installation of agents on devices, typically relies on network level authentication protocols such as 802.1X to authenticate devices and enforce access policies. May be less effective at enforcing security policies 

Features of Next Generation Firewall (NGFW) 
- application awareness that can distinguish between different types of traffic
- can conduct deep packet inspection and use signature-based intrusion detection
- has the ability to be integrated with various other security products

Features of stateful firewall
- tracking of connections and requests
- allowing return traffic for outbound requests
- improving awareness of connection states on layer 4

WPA3 features
- latest and most secure wireless security protocol
- utilizes a Diffie-Hellman key agreement
- provides individualized data encryption even in open networks
- it prevents eavesdropping, forging, and tampering with management frames

  
### Security program management and oversight
- Recovery Time Objective (RTO): the maximum acceptable time allowed for the recovery of a system or process after a disruption. It defines the time frame within which critical systems and operations must be restored to normal functionality
- Recovery Point Objective (RPO): the maximum amount of data that an organization can afford to lose during a disruption. It represents the point in time to which data must be recovered after recovery efforts are initiated
- Mean Time to Repair (MTTR): the average time it takes to restore a failed system or component to a working state after a disruption. It measures the efficiency of the repair process
- Mean Time Between Failures (MTBF): the average time elapsed between two consecutive failures of a system or component. It provides an indication of the system's reliability
