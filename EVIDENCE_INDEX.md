# Evidence Index

The assets below are **direct image extractions** from the supplied PowerPoint and DOCX files, not reconstructed or AI-generated event screenshots. Captions describe what the team used them to illustrate; a screenshot may support less than the complete written attack narrative.

## Case Study 01 — Web Defacement

### Network scanning (Suricata)
**Original location:** Lab 7 checkoff slides, p. 5; presenter labels initial network scan.
**Relevance:** Activity used to identify systems; the original screenshot shows network telemetry.
![Network scanning (Suricata)](web-defacement/01-network-scanning.png)

### SSH logon to UBUNTU20
**Original location:** Lab 7 checkoff slides, p. 5; initial access.
**Relevance:** SSH authentication success followed by login session opening for eve.
![SSH logon to UBUNTU20](web-defacement/02-ssh-access-ubuntu20.png)

### SSH persistence changes
**Original location:** Lab 7 checkoff slides, pp. 5-6; persistence.
**Relevance:** Commands changed the SSH server configuration and worked with the authorized_keys file.
![SSH persistence changes](web-defacement/03-ssh-persistence.png)

### Apache website modification
**Original location:** Lab 7 checkoff slides, p. 6; website impact.
**Relevance:** Bash/Shellshock-pattern command execution modified Apache web content and restarted the service.
![Apache website modification](web-defacement/04-apache-web-defacement.png)

### SFTP activity
**Original location:** Lab 7 checkoff slides, p. 6; possible exfiltration.
**Relevance:** SFTP-related process evidence. This does NOT establish what data, if any, was removed.
![SFTP activity](web-defacement/05-sftp-activity.png)

### RDP session to WIN16
**Original location:** Lab 7 checkoff slides, p. 7; Windows initial access.
**Relevance:** Windows authentication activity relating to RDP access as QUBE\Administrator.
![RDP session to WIN16](web-defacement/06-win16-rdp-logons.png)

### Lateral movement to WIN12
**Original location:** Lab 7 checkoff slides, p. 7; lateral movement.
**Relevance:** WIN12 logon and logoff records align with the reported RDP pivot.
![Lateral movement to WIN12](web-defacement/07-win12-lateral-movement.png)

### WIN12 IIS service activity
**Original location:** Lab 7 checkoff slides, p. 8; web-server impact.
**Relevance:** Process execution records include IIS-related activity around the reported web defacement.
![WIN12 IIS service activity](web-defacement/08-win12-iis-activity.png)

## Case Study 02 — AD CS / NTLM Relay

### Suricata HTTP alerts
**Original location:** Final incident response, appendix p. 13, Figure 2.
**Relevance:** Alerts show repeated network activity associated with suspicious HTTP requests; not proof of certificate abuse alone.
![Suricata HTTP alerts](adcs-ntlm-relay/01-suricata-http-alerts.png)

### NTLM authentication telemetry
**Original location:** Final incident response, appendix p. 15, Figure 6.
**Relevance:** Wazuh events contain NTLM V2 authentication fields and a source IP associated with the investigation.
![NTLM authentication telemetry](adcs-ntlm-relay/02-ntlm-authentication.png)

### Privileged logon events
**Original location:** Final incident response, appendix p. 15, Figure 7.
**Relevance:** Windows security events include privileged logon activity relevant to the investigation.
![Privileged logon events](adcs-ntlm-relay/03-privileged-logon.png)

### PowerShell execution telemetry
**Original location:** Final incident response, appendix p. 14, Figure 4.
**Relevance:** Process event records show PowerShell execution; the provided screenshot does not itself establish command intent.
![PowerShell execution telemetry](adcs-ntlm-relay/04-powershell-events.png)

### Security activity timeline
**Original location:** Final incident response, appendix p. 15, Figure 8.
**Relevance:** Timeline view of security-related events near the end of the documented activity.
![Security activity timeline](adcs-ntlm-relay/05-investigation-timeline.png)
