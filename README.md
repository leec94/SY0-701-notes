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
- Data masking: a method to de-identify some or all characters in a sequence, but not changing the total number of characters that a field should contain. The masked version will be structurally the same, but the data will be hidden. Data that is masked will have the same number of characters as the original data, not a smaller set. _Example:_ Changing the letters or numbers entered into a password field with dots is an example of data masking. 
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

Certificates
- Certificate stapling: attaches an OCSP validation to the digital certificate, saving the client and server the time of repeatedly querying the OCSP server for certificate validity
- Certificate pinning: a technique used to prevent changes in the valid certificate for a domain
- Certificate chaining: used to delegate authority to subordinate certificate authorities

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

DDoS Attacks
- Amplified DDoS: attackers can send a small request to a server, prompting it to reply with a much larger response. The attacker uses a forged source IP (the victim's IP), causing the server's amplified response to flood the victim
- Reflected DDoS: the attacker sends requests to third-party servers with a forged source IP address (the victim's IP), causing those servers to send responses to the victim

Network Attacks
- ARP poisoning: an attack that involves sending false MAC address information to a network switch, causing the switch to associate the incorrect MAC address with a particular IP address
- DNS poisoning: an attack that involves manipulating the DNS server to redirect traffic to malicious sites
- on-path attack: involves intercepting and potentially altering communication between two parties
- Disassociation attacks: intentionally disconnect a wireless user from their access point to force a reauthentication that the attacker may collect with a wireless eavesdropping tool

Wireless Attacks
- evil twin: the correct term used to refer to a seemingly identical, legitimate access point that an attacker has set up to cause unsuspecting users to attempt a wireless connection

Web Attacks
- SQL injection: used to input database commands into an application
- Cross-site scripting (XSS): attempts to inject client-side code into a server so it will be sent to, and executed on, other clients
- XML injection: used to input XML code into an application to manipulate how the application works
- LDAP injection: an attack that can send malicious data to a web form that in turn makes calls or queries to a directory database, such as an X.500-compliant database like Active Directory, or to any other LDAP database.
- Directory traversal attack: enables a malicious user to inject commands inside the HTTP message in order to travel through the directory structure of the web server

Backup types
- Image backup: duplicates an OS installation, either from a physical hard disk or a VM's virtual hard disk. It offers a quick means to redeploy the system without reinstalling software and settings
- File-level backup: copies individual files and directories
- Incremental backup: saves only the changes made since the last backup
- Differential backup: saves all changes made since the last full backup

Attributes of threat actors
- Capability: a threat actor's proficiency in devising new exploit techniques and tools. It can range from using commonly found attack tools to creating zero-day exploits in various systems. Those with the highest capabilities can even deploy non-cyber tools, such as political or military assets
- Sophistication: the level of intricacy and advancement of a threat actor's methods and tools

CVE
- CVSS Scoring: CVSS scores are calculated using a formula that provides a numerical result but also include the categories of Low, Medium, High, and Critical. Low is anything that results in a score of less than 4.0. Medium is a score of 4-6.9. High is 7.0-8.9. Critical is a score higher than 9.

Pen test tools 
- FakeAP: FakeAP is a Linux-based program that broadcasts false SSIDs to effect a denial of service attack on wireless networks

### Security architecture
- Proxy server: stands between the user's computer and the internet, intercepting requests and potentially reducing the public-facing attack surface by masking the internal server
- Jump server: used as a bridge to connect to other servers or networks in separate security zones
- Real-time Operating System (RTOS): an operating system where the processes running are deterministic and prioritize performance, used on devices like industrial equipment and automobiles. \[[Ref](https://www.professormesser.com/security-plus/sy0-501/embedded-systems/)\]

Security systems
- Web application firewall (WAF): Focuses on inspecting HTTP traffic, prevents common web application attacks like cross-site scripting and SQL injections
  - can be placed "In-line" or "Out of Band"
  - WAF vs NGFW article \[[Ref](https://www.f5.com/c/landing/waf-vs-ngfw-which-technology-do-you-need)\] 
- Data loss prevention (DLP) system: software or hardware system that aims to monitor data in use, in transit, or at rest to detect and prevent data theft
  - Types: Endpoint, Network, Storage, Cloud based 
- Intrusion detection system (IDS): logs or alerts if found something suspicious or malicious. Signature-based (from defined signatures) or anomaly based (from baseline)
- Intrusion prevention system (IPS): logs, alerts and takes actions when finds something suspicious or malicious.  

Networking 
- Physical isolation: network design that involves using air-gapping, disconnecting cables, or locking devices to prevent unauthorized access or interference. It can offer benefits such as security, privacy, and reliability.
- Logical segmentation: network design that involves dividing a network into smaller segments to improve performance and security
- Security zones: used to segregate networks to protect private networks from public ones such as the Internet, examples include extranets and DMZs  
- Virtual LANs (VLANs): used to segment hosts into logical networks and to create secure communication boundaries between them. VLANs are implemented on switches
- Software-defined networking (SDN): a network technology that involves dynamically configuring and managing network devices and services through software
- Decentralization: network design that involves distributing the control and authority among multiple nodes or entities
- Port security: feature of managed network switches that allows an organization to limit which devices can connect to a network based on their physical addresses (MAC addresses)
- Secure Access Service Edge (SASE): a cloud-based solution that integrates network security and WAN capabilities
- Software-defined wide area network (SD-WAN): provides centralized network management, flexible routing, and traffic management capabilities. It can be hosted both on-premises and in the cloud, giving it an edge for comprehensive WAN optimization 

Redundant Array of Independent Disks (RAID)
- Striping: spreads the data  for a single volume across 2 or more drives 
- Parity: Calculation of data across two drives, and stored on a third. If a drive fails, the RAID controller can rebuilt from other 2 drives
	- Dedicated parity: parity information is stored all on a single drive
	- Distributed parity: spreads data across all drives in the array
- Mirrored (or redundancy): 2 or more drives each with a copy of the drive, so the volume is protected from a drive failure, only one drive needed to work to function normally

|         | Stripe | Mirrored | Parity             | Minimum Drives |
|---------|--------|----------|--------------------|----------------|
| RAID 0  | yes    | no       | no                 | 2              |
| RAID 1  | no     | yes      | no                 | 2              |
| RAID 5  | yes    | no       | yes, distributed   | 3              |
| RAID 6  | yes    | no       | yes, 2 distributed | 4              |
| RAID 10 | yes    | yes      | no                 | 4              |

Authentication
- Extensible Authentication Protocol (EAP): framework for various authentication methods
- Protected Extensible Authentication Protocol (PEAP): used to encapsulate EAP messages over a secure tunnel that uses Transport Layer Security (TLS), mutual authentication using server certificates, and uses Active Directory databases to authenticate a password from the client
- EAP-TTLS: Requires a digital certificate on the server, but not on the client. Client uses a password for authentication
- EAP-TLS: uses public key infrastructure with a digital certificate installed on both the client and server, uses mutual authentication
- EAP-MD5: uses simple passwords and challenge handshake authentication process to provide remote access authentication
- EAP-FAST: Uses a protected access credential instead of a certificate to establish mutual authentication
- EAP-LEAP: Cisco proprietary and limited to Cisco devices 


### Security operations
Types of web filters
- Agent-based web filters: installed directly on the end-user's device, ensuring that the filtering policy is enforced consistently, whether the user is on the corporate network or working remotely \[[Ref](https://www.professormesser.com/security-plus/sy0-701/sy0-701-video/web-filtering-sy0-701/)\]
- Web security gateway filters: or Unified Threat Management (UTM) device, is a device that filters unsafe content from web traffic, and block risky or unauthorized user behavior. Contains URL filtering, anti-malware detection and blocking, and application control. Also has featues such as firewall, intrusion prevention, and antivirus. Runs on proxy servers or on-prem or in the cloud. \[[Ref](https://www.cloudflare.com/learning/access-management/what-is-a-secure-web-gateway/)\]

Network Access Control (NAC): enforces policies that determine which devices are allowed to access the network, and what resources they can access once they're connected \[[Ref](https://www.professormesser.com/security-plus/sy0-501/network-access-control-4/)\]
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
- TKIP: considered weak and has known vulnerabilities. Due to its security limitations, using TKIP is not advisable, especially when more secure alternatives like AES are available. Used by WPA to rapidly cycle encryption keys and overcome the weaknesses of WEP
- WPA: has some known vulnerabilities, particularly when using its pre-shared key (PSK) mode. Depending solely on WPA might not provide the level of security required to safeguard modern wireless networks. Uses TKIP to rapidly cycle encryption keys and overcome the weaknesses of WEP
- WPA2: Uses Counter Mode Cipher Block Chaining Message Authentication Code Protocol (CCMP) to provide enhanced security using AES
- Transport Layer Security (TLS): a protocol that encrypts communications over a network
- **WPA3** features
  - latest and most secure wireless security protocol
  - utilizes a Diffie-Hellman key agreement
  - provides individualized data encryption even in open networks
  - it prevents eavesdropping, forging, and tampering with management frames
  - uses Simultaneous Authentication of Equals (SAE)

Encryption protocols

Mobile
- Mobile Device Management (MDM): provide organizations with an easy way to manage the security settings on many mobile devices simultaneously. \[[Ref](https://www.professormesser.com/security-plus/sy0-601/sy0-601-video/mobile-device-management-2/)\]

ICS Components
- Data historian: captures and archives all information from the control loop
- Distributed Control System (DCS): manages process automation within a single site
- Human-Machine Interface (HMI): allows operators to interact directly with the system. Its security is paramount to prevent unauthorized access and potential manipulation of the system
- Programmable Logic Controllers (PLC): embedded devices within ICSs connecting to actuators and sensors

Management of data assets
- Enumeration: in hardware, software, and data asset management involves assigning unique identifiers, access controls, and attributes to each asset. This process allows for granular control over access permissions, ensuring only authorized users can interact with assets. Enumeration supports data confidentiality, integrity, and availability by preventing unauthorized access and ensuring proper resource management

Passwords
- HMAC-based one-time password (HOTP): Tokens that generate passcodes based upon a counter that increments when the user pushes a button
- Time-based one-time password (TOTP): Tokens that increment automatically based upon the current time 



### Security program management and oversight
- Recovery Time Objective (RTO): the maximum acceptable time allowed for the recovery of a system or process after a disruption. It defines the time frame within which critical systems and operations must be restored to normal functionality
- Recovery Point Objective (RPO): the maximum amount of data that an organization can afford to lose during a disruption. It represents the point in time to which data must be recovered after recovery efforts are initiated
- Mean Time to Repair (MTTR): the average time it takes to restore a failed system or component to a working state after a disruption. It measures the efficiency of the repair process
- Mean Time Between Failures (MTBF): the average time elapsed between two consecutive failures of a system or component. It provides an indication of the system's reliability

- Risk appetite: the amount of risk an organization is willing to accept in pursuit of its objectives. It's essentially a strategic, high-level view that aligns with the organization's goals and priorities. Think of it as the maximum amount of risk an organization is ready to take on overall, considering its strategic objectives and mission. Risk appetite is about the broader, overarching risk the organization is willing to accept to achieve its strategic goals.
- Risk tolerance: more specific and operational. It represents the acceptable level of risk exposure for various activities or projects within the organization. Risk tolerance is about the specific, measurable levels of risk acceptable in various situations. Risk tolerance refers more broadly to an organization's or individual's willingness to take on risk, not the specific predefined level for taking action. 
- Risk threshold: the limit of acceptable risk that an organization establishes, which once exceeded, triggers a response to reduce the risk to an acceptable level
- Risk level: the severity or high/low ranking of risk
- Risk rating: incorporates both likelihood and impact to give an overall score to a risk
- Likelihood: used in qualitative risk analysis to subjectively describe how probable a risk event is, often expressed in terms such as "low," "medium," or "high."


Data Governance
- Data processor: processes personal data for controllers and ensures implementation of security measures. They are tasked with handling personal data in accordance with the controller's directions and must secure the data as per the established standards.
- Data controller: responsible for determining the purpose and means of data processing, including establishing data ownership and access control 
- Data owner: directly responsible for classifying data and defining access permissions. May also contribute to setting the strategic direction and policies for organizational data management too.
- Governance board: sets the strategic direction and policies for organizational data management.
- Security and compliance committees: assessing and managing risks related to data security and compliance

Regulations 
- Payment Card Industry Data Security Standard (PCI DSS): an industry-mandated standard for the safe handling and storage of credit card information
- Federal Information Security Management Act (FISMA): governs the security of data processed by federal government agencies
- California Consumer Privacy Act (CCPA): a state legislation that provides comprehensive data protection rights to consumers across sectors, horizontally
- Gramm–Leach–Bliley Act (GLBA): financial industry regulation
- Family Educational Rights and Privacy Act (FERPA): regulates educational institutions
- Sarbanes Oxley Act (SOX): regulates the financial accounting practices of publicly traded companies 

Agreement Types
- Service Level Agreement (SLA): a document that defines the expectations between an organization and a third-party provider, outlines security controls, performance metrics, availability requirements, and confidentiality clauses.
- Memorandum of Understanding (MOU): less formal and binding, expresses mutual intent without detailed specifics
- Memorandum of Agreement (MOA): formal, outlines specific responsibilities and roles
- Master Service Agreement (MSA): Covers general terms of engagement across multiple transactions, and used for recurring client relationships, supplemented by Statements of Work
- Statement of Work (SOW): Specifies project details, deliverables, timelines, and milestones. Also provides in-depth project-related information
- Non-Disclosure Agreement (NDA): Ensures confidentiality of sensitive information shared during negotiations. Also has commitments to privacy, protecting proprietary data. 
- Data Use Agreement (DUA): focuses on specific data usage conditions. 
- Business Partnership Agreement (BPA): Governs business partnerships, goes beyond basic contracts when two entities collaborate. Outlines partnership nature, profit-sharing, decision making, and exit strategies, and defines ownership of intellectual property and revenue distribution 

SOC Types
- System and Organization Control (SOC) reports: provide the results of an independent audit of a service provider
- SOC 1 reports: done to verify controls that could impact a client’s financial reporting
- SOC 2 reports: done to verify controls that could impact security and privacy of data
- Type 1 reports: simply verify that controls are in place
- Type 2 reports: verify that the controls are operating efficiently and effectively
