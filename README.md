# Windows SAM Database Vulnerability Assessment & Password Auditing

An ethical hacking lab report documenting a simulated penetration test against an isolated, deliberately unpatched Windows 2000 VM — focused on the "Gaining Access" phase of the attack lifecycle, specifically weak password hygiene via offline SAM database extraction and rainbow table cracking.

## Scenario

Suzlon Corporation's internal security auditor investigates whether legacy, unsupported Windows systems on the corporate network are vulnerable to privilege escalation and lateral movement due to weak passwords and outdated hashing protocols (LM/NTLM). The assessment is carried out entirely offline, within an isolated lab environment, simulating an intruder who has already gained local access.

## Lab Environment

- Fully isolated, internet-disconnected network testbed — no production systems involved
- **Attacker machine:** Kali Linux
- **Target machine:** Windows 2000 Professional (deliberately unpatched, legacy OS)

## Attack Phases Covered

1. **Footprinting & Reconnaissance** — identifying attacker/target IPs on the isolated network
2. **Scanning** — Nmap-based port, service, and OS enumeration
3. **Vulnerability Identification** — legacy SMB/NetBIOS exposure
4. **Exploitation** — remote shell access via a well-known, publicly documented SMB vulnerability (Metasploit)
5. **Credential Extraction** — dumping LM/NTLM password hashes from the SAM database
6. **Offline Password Cracking** — rainbow table attack using Ophcrack
7. **Clearing Tracks** — log tampering awareness
8. **Impact Analysis** — confidentiality, integrity, and availability assessment of the compromise

## Tools Used

- Kali Linux
- Nmap
- Metasploit Framework
- PwDump
- Ophcrack (rainbow table-based password recovery)

## Countermeasures Discussed

- Patch management and the vulnerability management lifecycle
- Network segmentation / firewall rules restricting SMB ports (135, 139, 445)
- Endpoint detection and disabling unnecessary legacy services (e.g. TFTP)
- Strong password policy
- Salted hashing algorithms in place of legacy LM/NTLM


## Disclaimer

This report documents an authorized, simulated penetration test conducted entirely within an isolated lab environment with no internet access and no production systems. It is intended solely for academic and educational purposes under controlled conditions.
