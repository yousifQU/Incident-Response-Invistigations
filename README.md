# Incident Response Investigations | CNIT 470

**Two simulated cybersecurity incident investigations** | Purdue University | Team-based coursework, Group 27 | April 2026

> **Portfolio context:** These are educational attack simulations, **not confirmed real-world breaches**. This portfolio describes the investigation documented by the project team. Screenshots are excerpts of the team's existing evidence; detections and conclusions should not be interpreted as independently verified by a third party.

**[Read the 5-page executive report (PDF)](report/ExecutivePortfolioReport.pdf)**  ·

## At a glance

As part of a collaborative incident response project, our team investigated two different intrusion scenarios across Linux, Windows, and Active Directory environments. We correlated security telemetry, reconstructed attack timelines, identified affected systems, mapped attacker behavior to **MITRE ATT&CK**, and developed containment and hardening recommendations.

| Case study | Investigated activity | Systems and impact | Main evidence sources |
|---|---|---|---|
| [01 · Web defacement and lateral movement](CASE_STUDY_01_Web_Defacement.md) | Valid-credential SSH/RDP access, elevated privileges, SSH persistence, Apache/IIS modification | UBUNTU20, WIN16, WIN12; two web properties defaced | **Suricata, Wazuh, Velociraptor** |
| [02 · Active Directory Cetficiation Services (AD CS) and NTLM relay](CASE_STUDY_02_ADCS_NTLM_Relay.md) | Network discovery, coerced authentication and certificate abuse as reconstructed in the investigation | Active Directory/domain authentication and certificate enrollment environment | **Suricata, Wazuh, Velociraptor, Windows events** |

## Selected findings

### Case 01: Website defacement and lateral movement

The April 12 investigation connected suspicious network scanning with an SSH logon to **UBUNTU20** system, sudo/root access, SSH configuration changes, and Apache website modification. Separate RDP activity involved **WIN16** system, where a new account and altered security policy were documented, followed by movement to **WIN12** system and Internet Information System website modification. SFTP activity was observed, but **successful data exfiltration and its contents were not confirmed**.

![Evidence of SSH persistence in the web-defacement case](evidence/web-defacement/03-ssh-persistence.png)


[View full investigation →](CASE_STUDY_01_Web_Defacement.md)

### Case 02: AD CS / NTLM relay

The April 30 investigation documented suspicious HTTP and SMB/NTLM activity and an attack narrative involving **PetitPotam** exploit, **NTLM relay**, and **Active Directory Certificate Services (AD CS)** web enrollment. The team reconstructed certificate-based authentication abuse, credential exposure, and subsequent discovery activity.

![Wazuh NTLM authentication evidence](evidence/adcs-ntlm-relay/02-ntlm-authentication.png)


[View full investigation →](CASE_STUDY_02_ADCS_NTLM_Relay.md)

## Technical skills demonstrated

| Area | Skills / tools used in the provided investigations |
|---|---|
| Incident handling | Scoping, triage, detection and analysis, containment planning, recovery recommendations, lessons learned |
| SIEM and network visibility | **Wazuh** security events; **Suricata** IDS / network data |
| Endpoint investigation | **Velociraptor** hunts, process events, Windows authentication events, Linux sudo and SSH activity |
| Identity and access | SSH, RDP, NTLM, LDAP, **Active Directory Certificate Services (AD CS)** |
| Adversary analysis | Timeline reconstruction, indicators of compromise, account misuse, lateral movement, mapping to **MITRE ATT&CK** |
| Communications | Executive summaries, impact assessment, security recommendations, evidence documentation |


## Key takeaways

These incident response investigations provided valuable hands-on experience in analyzing cybersecurity attacks, identifying security weaknesses, and understanding how attackers compromise different systems. The following lessons were learned from investigating both the web defacement and Active Directory attacks.

1. Importance of Strong Authentication and Access Controls

Both investigations demonstrated how weaknesses in authentication can put an entire network at risk. In the web defacement incident, the attacker used valid credentials to access Linux and Windows systems through SSH and RDP. In the Active Directory incident, weaknesses in NTLM authentication and certificate services created opportunities for credential abuse. These findings highlighted the importance of implementing multi-factor authentication (MFA), enforcing strong password policies, and restricting unnecessary remote access.

2. Privilege Escalation and Lateral Movement

One of the most important lessons was understanding how attackers can move beyond their initial point of entry. During the web defacement investigation, the attacker gained root privileges on an Ubuntu server, modified SSH configurations, and later accessed Windows systems using administrative credentials. The attacker also created an unauthorized account and modified security policies. This demonstrated why organizations should follow the principle of least privilege, limit administrative access, and implement network segmentation to reduce lateral movement.

3. Importance of Security Monitoring and Log Analysis

The investigations demonstrated the value of collecting and analyzing security logs from multiple sources. Tools such as Wazuh, Suricata, and Velociraptor helped identify suspicious network activity, unusual authentication events, privilege escalation, and system modifications. By comparing evidence from these tools, the team reconstructed attack timelines and better understood the sequence of events. This experience reinforced the importance of continuous monitoring, centralized logging, and having enough visibility to detect suspicious behavior.

5. Following a Structured Incident Response Process

Both investigations reinforced the importance of following an organized incident response process rather than investigating suspicious events without a clear plan. The team examined the scope of each incident, analyzed available evidence, identified affected systems, reconstructed attack timelines, and developed containment and recovery recommendations. Mapping attacker behavior to the MITRE ATT&CK framework also helped organize the findings and explain the techniques used. This approach made the investigations easier to document and communicate.

## Project contribution and attribution

This work was completed **collaboratively by CNIT 470 Group 27**. This repository therefore describes team results rather than claiming personal authorship of specific screenshots, detections, or remediation actions
