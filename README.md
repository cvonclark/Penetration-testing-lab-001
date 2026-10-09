# Penetration Testing Lab 001
## vsftpd 2.3.4 Backdoor Exploitation

### Objective
Validate a known vulnerability against an intentionally vulnerable
Metasploitable 2 system in an isolated VMware lab.

### Lab Environment
- Windows 11 host
- VMware Workstation 17 Player
- Kali Linux 2025.3
- Metasploitable 2
- Host-only network

### Methodology
1. Network connectivity verification
2. Port scanning with Nmap
3. Service/version enumeration
4. FTP banner enumeration
5. Anonymous FTP testing
6. Vulnerability research with SearchSploit
7. Exploit identification
8. Vulnerability validation with Metasploit
9. Privilege verification

### Finding
CVE-2011-2523 — vsftpd 2.3.4 Backdoor

### Evidence
<img width="524" height="269" alt="image" src="https://github.com/user-attachments/assets/41e94f46-17d8-4bbb-a56d-02e3bc326cf5" />

<img width="545" height="190" alt="image" src="https://github.com/user-attachments/assets/54becc42-34ed-418e-b7d9-215a39ef8077" />

<img width="575" height="335" alt="image" src="https://github.com/user-attachments/assets/ec80fef3-e984-471e-aea3-058652fe023d" />


<img width="623" height="68" alt="image" src="https://github.com/user-attachments/assets/905d4537-a84d-4ab5-9531-8a2090125d95" />


### Impact
Remote command execution with root privileges.

### Remediation
### Remediation Recommendations

**Finding:** vsftpd 2.3.4 Backdoor — CVE-2011-2523  
**Severity:** Critical  
**Affected Service:** FTP (TCP Port 21)  
**Affected Host:** 192.168.42.128

**Recommended Actions:**

1. **Remove the compromised software:** Immediately remove the backdoored vsftpd 2.3.4 installation and replace it with a current, supported FTP server obtained from a trusted source, if FTP functionality is still required.

2. **Restrict network access:** Block unnecessary inbound connections to TCP port 21 using firewall rules. Limit access to explicitly authorized systems.

3. **Replace insecure file transfer protocols:** Where feasible, migrate from traditional FTP to SFTP over SSH to provide encrypted authentication and data transfer.

4. **Investigate potential compromise:** Because exploitation can provide root-level command execution, review system logs, unauthorized accounts, persistence mechanisms, and other indicators of compromise. If compromise is suspected or confirmed, rebuild the affected host from a trusted image.

5. **Implement vulnerability management:** Establish regular vulnerability scanning, software inventory reviews, and security updates to identify outdated or compromised services.

6. **Validate remediation:** Rescan the host using Nmap, verify that the compromised service is no longer running, and confirm that the previously successful exploit no longer works.

**Expected Outcome:**

Implementing these recommendations will eliminate the known vsftpd backdoor, reduce unnecessary network exposure, and help prevent unauthorized remote command execution with root privileges.

### Tools
- Nmap
- Netcat
- SearchSploit
- Metasploit
- Kali Linux
- VMware Workstation
