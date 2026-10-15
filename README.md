# Incident Response Investigations | CNIT 470

**Two simulated cybersecurity incident investigations** | Purdue University | Team-based coursework, Group 27 | April 2026

> **Portfolio context:** These are educational attack simulations, **not confirmed real-world breaches**. This portfolio describes the investigation documented by the project team. Screenshots are excerpts of the team's existing evidence; detections and conclusions should not be interpreted as independently verified by a third party.

**[Read the 5-page executive report (PDF)](report/ExecutivePortfolioReport.pdf)**  ·  **[View the evidence index](evidence/EVIDENCE_INDEX.md)**  ·  **[Publishing instructions](PUBLISHING_GUIDE.md)**

## At a glance

As part of a collaborative incident response project, our team investigated two different intrusion scenarios across Linux, Windows, and Active Directory environments. We correlated security telemetry, reconstructed attack timelines, identified affected systems, mapped attacker behavior to **MITRE ATT&CK**, and developed containment and hardening recommendations.

| Case study | Investigated activity | Systems and impact | Main evidence sources |
|---|---|---|---|
| [01 · Web defacement and lateral movement](CASE_STUDY_01_Web_Defacement.md) | Valid-credential SSH/RDP access, elevated privileges, SSH persistence, Apache/IIS modification | UBUNTU20, WIN16, WIN12; two web properties defaced | **Suricata, Wazuh, Velociraptor** |
| [02 · AD CS and NTLM relay](CASE_STUDY_02_ADCS_NTLM_Relay.md) | Network discovery, coerced authentication and certificate abuse as reconstructed in the investigation | Active Directory/domain authentication and certificate enrollment environment | **Suricata, Wazuh, Velociraptor, Windows events** |

## Selected findings

### Case 01: Website defacement and lateral movement

The April 12 investigation connected suspicious network scanning with an SSH logon to **UBUNTU20**, sudo/root access, SSH configuration changes, and Apache website modification. Separate RDP activity involved **WIN16**, where a new account and altered security policy were documented, followed by movement to **WIN12** and IIS website modification. SFTP activity was observed, but **successful data exfiltration and its contents were not confirmed**.

![Evidence of SSH persistence in the web-defacement case](evidence/web-defacement/03-ssh-persistence.png)

*SSH server changes and authorized-key activity, extracted from the group's Lab 7 checkoff presentation.*

[View full investigation →](CASE_STUDY_01_Web_Defacement.md)

### Case 02: AD CS / NTLM relay

The April 30 investigation documented suspicious HTTP and SMB/NTLM activity and an attack narrative involving **PetitPotam**, **NTLM relay**, and **Active Directory Certificate Services (AD CS)** web enrollment. The team reconstructed certificate-based authentication abuse, credential exposure, and subsequent discovery activity. Some steps in this chain are **reported in the written timeline rather than demonstrated by an included standalone screenshot**.

![Wazuh NTLM authentication evidence](evidence/adcs-ntlm-relay/02-ntlm-authentication.png)

*Wazuh NTLM-related authentication fields from the original team's final incident report.*

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

## Browse the portfolio

```text
CNIT-470-Incident-Response-Investigations/
├── README.md
├── CASE_STUDY_01_Web_Defacement.md
├── CASE_STUDY_02_ADCS_NTLM_Relay.md
├── evidence/
│   ├── EVIDENCE_INDEX.md
│   ├── web-defacement/            # 8 selected screenshots
│   └── adcs-ntlm-relay/           # 5 selected screenshots
├── timelines/
│   ├── web_defacement_2026-04-12.csv
│   └── adcs_ntlm_2026-04-30.csv
└── report/
    ├── EXECUTIVE_OVERVIEW.md
    ├── ExecutivePortfolioReport.pdf
    └── SOURCE_AND_SCOPE_NOTES.md
```

## Key takeaways

The common theme across both investigations was **identity and access risk**: valid credentials, excessive access, and trust relationships can help an attacker move deeper into an environment. Our analysis prioritized stronger authentication, privilege restrictions, detection of unusual access and administrative changes, protection of AD CS, and more complete logging.

## Project contribution and attribution

This work was completed **collaboratively by CNIT 470 Group 27**. The provided files do not attribute each investigative task to an individual; this repository therefore describes team results rather than claiming personal authorship of specific screenshots, detections, or remediation actions. Students may add a short, accurate **My Contributions** section to describe their individual work before publishing. The screenshots are reproduced for portfolio documentation from the provided team files. No original course assignment handout is included.

## Important boundaries

- Educational / controlled lab setting; not a production security incident.
- **Possible exfiltration** in Case 01 is not treated as proven data theft.
- **Response recommendations** are not presented as implemented controls without validation.
- Case 02's report states recovery outcomes, but no independent recovery verification artifacts were supplied.
- A separate **Fall 2026 Lab 4 instruction sheet** was supplied as context and was **not** used to claim completed work, deploy Timesketch, or perform UAC/KAPE triage.

**Suggested GitHub topics:** `incident-response` · `cybersecurity` · `digital-forensics` · `threat-hunting` · `wazuh` · `suricata` · `velociraptor` · `active-directory` · `mitre-attack`
