# Threat Modeling with MITRE ATT&CK

**Training case study | Attack surfaces, risk scoring, and defensive planning**

## About this project

For this project, I built a threat model for **Xibalba Interactive**, a fictional company running online gaming services. Its environment included public game servers, an API, a statistics website, development systems, VPN access, and a payment service.

My task was to work out which assets mattered most, how someone might attack them, and where the company should focus its security efforts.

This was a hypothetical risk assessment, not an investigation of a breach that actually happened.

## What I looked at

I started with the systems and data that would be most damaging to lose or expose: game source code, player accounts, payment information, development credentials, chat-related data, and security logs.

I then considered possible attackers, including financially motivated cybercriminals, nation-state actors, and more persistent threat groups. From there, I mapped out potential attack paths involving public applications, stolen credentials, VPN access, and movement between network segments.

## Risk assessment

The training worksheet rated likelihood and impact from **1 to 5** and added the two numbers together. These are estimates used for the exercise, not measured probabilities.

| Risk scenario | Likelihood | Impact | Score |
| --- | ---: | ---: | ---: |
| Development server compromise | 5 | 5 | **10/10** |
| Exposed administration interface | 5 | 5 | **10/10** |
| Shared development and production database credentials | 5 | 5 | **10/10** |
| Payment server compromise | 4 | 5 | **9/10** |
| VPN gateway exploitation | 4 | 5 | **9/10** |

[Read more about the risk assessment](docs/risk-assessment-highlights.md).

## MITRE ATT&CK mapping

I used ATT&CK to describe how the modeled scenarios might unfold, including:

- **T1190:** Exploit Public-Facing Application
- **T1078:** Valid Accounts
- **T1133:** External Remote Services
- **T1552:** Unsecured Credentials
- **T1021:** Remote Services
- **T1041:** Exfiltration Over C2 Channel
- **T1562:** Impair Defenses

These techniques describe possible attacker behavior in the scenario, not observed attacks.

## What I recommended

I organized the recommendations around three areas:

1. **Better visibility:** Collect web, application, firewall, and file-access logs so suspicious activity is easier to spot.
2. **Early warning:** Consider isolated decoys, such as a fake source-code repository or administration page, to help identify unauthorized probing.
3. **Fewer opportunities to attack:** Patch exposed applications, limit access between sensitive environments, improve secrets management, and monitor changes to security tools.

[Read the proposed defensive roadmap](docs/defensive-roadmap.md).

## What I learned

I got practice connecting technical weaknesses to possible business consequences and deciding which risks deserved attention first. The biggest lesson was that a useful threat model should lead to specific recommendations, not just a list of things that could go wrong.

This is my own write-up of a TripleTen training exercise. I haven't reproduced the original worksheet or course templates, and I haven't claimed the recommended defenses were deployed.
