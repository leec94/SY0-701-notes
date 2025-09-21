# Overview

Notes I want to add to my cheatsheet on exam day. 

## Cheatsheet Notes

Ports and protocols 

Insecure vs Secure protocols
| Insecure             | Secure                               |
|----------------------|--------------------------------------|
| HTTP (port 80)       | HTTPS (port 443)                     |
| FTP (port 20,21)     | SFTP / FTPS (port 465)               |
| Telnet (port 23)     | SSH/SCP/SFTP (port 22)               |
| SMTP (port 25)       | SMTPS (port 465)                     |
| POP3 (port 110)      | POP3S (port 995)                     |
| NNTP (port 119)      | NNTPS (port 563)                     |
| IMAP (port 143)      | IMAPS (port 993)                     |
| SNMP (port 161,162)  | SNMPv3 (port 161, 162, 10161, 10162) |


RAID levels 

|         | Stripe | Mirrored | Parity             | Minimum Drives |
|---------|--------|----------|--------------------|----------------|
| RAID 0  | yes    | no       | no                 | 2              |
| RAID 1  | no     | yes      | no                 | 2              |
| RAID 5  | yes    | no       | yes, distributed   | 3              |
| RAID 6  | yes    | no       | yes, 2 distributed | 4              |
| RAID 10 | yes    | yes      | no                 | 4              |

Risk calculations 
```
SLE = AV * EF
ALE = SLE * ARO 
```

Secure encryption protocols

Incident response phases
Preparation, Identification, Containment, Eradication, Recovery, and Lessons Learned
