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

### Threats, vulnerability, and mitigations
### Security architecture
- Proxy server: stands between the user's computer and the internet, intercepting requests and potentially reducing the public-facing attack surface by masking the internal server
- Jump server: used as a bridge to connect to other servers or networks in separate security zones
  
### Security operations
Types of web filters:
- Agent-based web filters: installed directly on the end-user's device, ensuring that the filtering policy is enforced consistently, whether the user is on the corporate network or working remotely \[[Ref](https://www.professormesser.com/security-plus/sy0-701/sy0-701-video/web-filtering-sy0-701/)\]
- Web security gateway filters: or Unified Threat Management (UTM) device, is a device that filters unsafe content from web traffic, and block risky or unauthorized user behavior. Contains URL filtering, anti-malware detection and blocking, and application control. Also has featues such as firewall, intrusion prevention, and antivirus. Runs on proxy servers or on-prem or in the cloud. \[[Ref](https://www.cloudflare.com/learning/access-management/what-is-a-secure-web-gateway/)\]

Network Access Control: enforces policies that determine which devices are allowed to access the network, and what resources they can access once they're connected \[[Ref](https://www.professormesser.com/security-plus/sy0-501/network-access-control-4/)\]
- Agent-based NAC: requires an agent to be installed on every device. Is able to get more detailed information about the device requesting access to the network, and provides continuous monitoring \[[Ref](https://s3msecurity.com/agent-based-or-agentless-which-should-be-preferred/)\]
- Agentless NAC: does not require installation of agents on devices, typically relies on network level authentication protocols such as 802.1X to authenticate devices and enforce access policies. May be less effective at enforcing security policies 

Features of Next Generation Firewall (NGFW): 
- application awareness that can distinguish between different types of traffic
- can conduct deep packet inspection and use signature-based intrusion detection
- has the ability to be integrated with various other security products

Features of stateful firewall:
- tracking of connections and requests
- allowing return traffic for outbound requests
- improving awareness of connection states on layer 4

  
### Security program management and oversight
