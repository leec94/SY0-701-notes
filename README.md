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

Security Controls \[[Ref](https://purplesec.us/learn/security-controls/)\]
- Technical: use technology to reduce vulnerabilities in hardware and software
- Administrative: policies, procedures, or guidelines that define personnel or business practices in accordance with the organization’s security goals
- Physical: implementation of security measures in a defined structure used to deter or prevent unauthorized access to sensitive material
- Preventative: attempt to prevent an incident from occurring
- Detective: attempt to detect incidents after they have occurred
- Corrective: attempt to reverse the impact of an incident
- Deterrent: attempt to discourage individuals from causing an incident
- Compensating: alternative controls used when a primary control is not feasible
- Directive: ensure consistent behavior within an organization

Access Controls
- Role-Based Access Control (RBAC): an authorization model that assigns permissions to roles, rather than individual users
- Attribute Based Access Control (ABAC): determines access through a combination of contexts and system wide attributes
- Discretionary Access Control (DAC): an authorization model where the owner of the resource decides who is allowed to access it
- Mandatory Access Control (MAC): an authorization model where access to resources is determined by a set of rules defined by a central authority

Zero trust concepts
- Policy administrator: responsible for defining and managing security policies that dictate access controls
- Authentication server: primarily tasked with validating a user's credentials and ensuring that a user is who they claim to be
- Policy enforcement point: responsible for enforcing the access control decisions made by the policy engine



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

Attributes of threat actors
- Capability: a threat actor's proficiency in devising new exploit techniques and tools. It can range from using commonly found attack tools to creating zero-day exploits in various systems. Those with the highest capabilities can even deploy non-cyber tools, such as political or military assets
- Sophistication: the level of intricacy and advancement of a threat actor's methods and tools


### Security architecture
- Proxy server: stands between the user's computer and the internet, intercepting requests and potentially reducing the public-facing attack surface by masking the internal server
- Jump server: used as a bridge to connect to other servers or networks in separate security zones
- Real-time Operating System (RTOS): an operating system where the processes running are deterministic and prioritize performance, used on devices like industrial equipment and automobiles. \[[Ref](https://www.professormesser.com/security-plus/sy0-501/embedded-systems/)\] 

Networking 
- Physical isolation: network design that involves using air-gapping, disconnecting cables, or locking devices to prevent unauthorized access or interference. It can offer benefits such as security, privacy, and reliability.
- Logical segmentation: network design that involves dividing a network into smaller segments to improve performance and security
- Software-defined networking (SDN): a network technology that involves dynamically configuring and managing network devices and services through software
- Decentralization: network design that involves distributing the control and authority among multiple nodes or entities

RAID
- Striping: spreads the data  for a single volume across 2 or more drives 
- Parity: calculation of data in two drive, and stored on a third. if a drive fails, the raid controller can rebuild from other 2 drives 
	- Dedicated parity: parity information is stored all on a single drive
	- Distributed parity: spreads data across all drives in the array
- Mirrored (or redundancy): 2 or more drives each with a copy of the drive, so the volume protected from a drive failure, only one drive needed to work to function normally. 

|         | Stripe | Mirrored | Parity             | Minimum Drives |
|---------|--------|----------|--------------------|----------------|
| RAID 0  | yes    | no       | no                 | 2              |
| RAID 1  | no     | yes      | no                 | 2              |
| RAID 5  | yes    | no       | yes, distributed   | 3              |
| RAID 6  | yes    | no       | yes, 2 distributed | 4              |
| RAID 10 | yes    | yes      | no                 | 4              |

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

NetFlow features
- allows for the visualization of flow patterns
- can help with capacity planning and understanding network performance issues
- can identify the source and destination of traffic, making it easier to spot potential threats
- helps provide an understanding of network traffic flow, enhancing security by identifying unusual patterns

Wireless Protocols 
- **AES**: the most secure and widely adopted encryption protocol for wireless networks. Its strong encryption algorithms and extensive testing demonstrate its effectiveness against various attacks. AES is the recommended choice for ensuring robust security in wireless communication
- WEP: outdated encryption protocol that has been widely exploited and rendered highly insecure. Its weak key management and static keys make it vulnerable to various attacks, and it can be cracked relatively easily. It should be avoided in modern network environments due to its lack of security
- TKIP: considered weak and has known vulnerabilities. Due to its security limitations, using TKIP is not advisable, especially when more secure alternatives like AES are available.
- WPA: has some known vulnerabilities, particularly when using its pre-shared key (PSK) mode. Depending solely on WPA might not provide the level of security required to safeguard modern wireless networks
- **WPA3** features
  - latest and most secure wireless security protocol
  - utilizes a Diffie-Hellman key agreement
  - provides individualized data encryption even in open networks
  - it prevents eavesdropping, forging, and tampering with management frames

Encryption protocols


Mobile
- Mobile Device Management (MDM): provide organizations with an easy way to manage the security settings on many mobile devices simultaneously. \[[Ref](https://www.professormesser.com/security-plus/sy0-601/sy0-601-video/mobile-device-management-2/)\]
  
### Security program management and oversight
- Recovery Time Objective (RTO): the maximum acceptable time allowed for the recovery of a system or process after a disruption. It defines the time frame within which critical systems and operations must be restored to normal functionality
- Recovery Point Objective (RPO): the maximum amount of data that an organization can afford to lose during a disruption. It represents the point in time to which data must be recovered after recovery efforts are initiated
- Mean Time to Repair (MTTR): the average time it takes to restore a failed system or component to a working state after a disruption. It measures the efficiency of the repair process
- Mean Time Between Failures (MTBF): the average time elapsed between two consecutive failures of a system or component. It provides an indication of the system's reliability

- Risk Appetite: the amount of risk an organization is willing to accept in pursuit of its objectives. It's essentially a strategic, high-level view that aligns with the organization's goals and priorities. Think of it as the maximum amount of risk an organization is ready to take on overall, considering its strategic objectives and mission. Risk appetite is about the broader, overarching risk the organization is willing to accept to achieve its strategic goals.
- Risk Tolerance: more specific and operational. It represents the acceptable level of risk exposure for various activities or projects within the organization. This is more about the granular, day-to-day level of risk an organization can handle while still operating effectively. Risk tolerance is about the specific, measurable levels of risk acceptable in various situations.

Data Governance
- Data processor: processes personal data for controllers and ensures implementation of security measures. They are tasked with handling personal data in accordance with the controller's directions and must secure the data as per the established standards.
- Data owner: directly responsible for classifying data and defining access permissions. May also contribute to setting the strategic direction and policies for organizational data management too.
- Governance board: sets the strategic direction and policies for organizational data management.
- Security and compliance committees: assessing and managing risks related to data security and compliance

Agreement Types
- Service Level Agreement (SLA): a document that defines the expectations between an organization and a third-party provider, outlines security controls, performance metrics, availability requirements, and confidentiality clauses.
- Memorandum of Understanding (MOU): less formal and binding, expresses mutual intent without detailed specifics
- Memorandum of Agreement (MOA): formal, outlines specific responsibilities and roles
- Master Service Agreement (MSA): Covers general terms of engagement across multiple transactions, and used for recurring client relationships, supplemented by Statements of Work
- Statement of Work (SOW): Specifies project details, deliverables, timelines, and milestones. Also provides in-depth project-related information
- Non-Disclosure Agreement (NDA): Ensures confidentiality of sensitive information shared during negotiations. Also has commitments to privacy, protecting proprietary data. 
- Data Use Agreement (DUA): focuses on specific data usage conditions. 
- Business Partnership Agreement (BPA): Governs business partnerships, goes beyond basic contracts when two entities collaborate. Outlines partnership nature, profit-sharing, decision making, and exit strategies, and defines ownership of intellectual property and revenue distribution 
