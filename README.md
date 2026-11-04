# Threat Modeling & MITRE ATT&CK Analysis

**Project type:** Simulated cybersecurity training case study  
**Scenario:** Xibalba Interactive, a fictional gaming-services organization  
**Focus:** Threat modeling, attack surface analysis, risk prioritization, MITRE ATT&CK mapping, and defensive strategy

## Project overview

I developed a threat model for a simulated gaming company with public-facing game and API services, a stats website, a development environment, remote-access infrastructure, and a payment-processing environment. My analysis considered how valuable assets could be targeted, where security weaknesses created exposure, and which controls should be prioritized to reduce risk.

The work was a **documented risk assessment and proposed security roadmap**, not an investigation of a confirmed real-world breach or a deployment of production defenses.

## What I analyzed

- **Critical assets:** Proprietary source code, player account data, payment information, developer credentials, chat services, and security logs.
- **Threat actors:** Cybercriminals, nation-state actors, and advanced persistent threat groups, with additional actor categories considered in the worksheet.
- **Attack surface:** Public web applications, API and admin interfaces, exposed development assets, remote access, shared credentials, and network boundaries.
- **Risk assessment:** Likelihood and impact ratings to prioritize exposures across the environment.
- **Attack scenarios:** Web exploitation, credential compromise, lateral movement, theft of proprietary code or payment data, and disabling security logging.

## Risk prioritization highlights

The supporting training worksheet rated likelihood and impact on 1–5 scales and **added** them to produce a total score out of 10. Selected high-priority scenarios were:

| Asset / exposure | Likelihood | Impact | Worksheet score |
| --- | --- | --- | --- |
| Development server compromise | 5 | 5 | **10/10** |
| Public administrative interface compromise | 5 | 5 | **10/10** |
| Shared development/production database credentials | 5 | 5 | **10/10** |
| Payment-processing server compromise | 4 | 5 | **9/10** |
| VPN gateway exploitation | 4 | 5 | **9/10** |

These are **scenario-based estimates**, not measured exploitation probabilities or incident statistics.

## Selected MITRE ATT&CK techniques

The scenarios in my report referenced these techniques, among others:

- [T1190 — Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190/)
- [T1078 — Valid Accounts](https://attack.mitre.org/techniques/T1078/)
- [T1133 — External Remote Services](https://attack.mitre.org/techniques/T1133/)
- [T1552 — Unsecured Credentials](https://attack.mitre.org/techniques/T1552/)
- [T1021 — Remote Services](https://attack.mitre.org/techniques/T1021/)
- [T1041 — Exfiltration Over C2 Channel](https://attack.mitre.org/techniques/T1041/)
- [T1562 — Impair Defenses](https://attack.mitre.org/techniques/T1562/)

**Important:** These are plausible attack techniques used for threat modeling. They are **not evidence that any attack occurred** against a real organization.

## Proposed defensive strategy

I evaluated three complementary sets of recommendations:

1. **Visibility and monitoring:** Centralize web/application, firewall, and sensitive-file access logs; monitor for suspicious authentication, exploitation, lateral movement, and tampering with defenses.
2. **Deception and early warning:** Propose isolated decoys, including a fake source-code repository, a simulated payment service, and an administrative-interface tripwire.
3. **Prevention and hardening:** Patch exposed applications, address misconfigurations, strengthen segmentation, protect credentials in a secrets manager, and audit changes to security tooling.

See [risk assessment highlights](docs/risk-assessment-highlights.md) and [proposed defensive roadmap](docs/defensive-roadmap.md).

## Skills demonstrated

- Asset inventory and threat actor profiling
- Structured likelihood/impact risk assessment
- Attack surface mapping and scenario development
- MITRE ATT&CK technique mapping
- Defensive prioritization with business and technical stakeholders in mind
- Writing an actionable security improvement roadmap

## Source and limitations

This GitHub portfolio is an **original summary** based on my TripleTen cybersecurity training deliverables. It excludes the original course template, live or private credentials, and detailed environment identifiers. The source report contains some unfilled template sections, which are intentionally not presented as completed work.

This repository documents **analysis and recommendations only**. There is no evidence in the source deliverables that the proposed honeypots, SIEM detections, segmentation changes, or preventive controls were deployed or validated in production.

Before public release, confirm that publishing original summaries and any supporting screenshots is permitted by the training provider. See [publication checklist](PUBLICATION_CHECKLIST.md).
