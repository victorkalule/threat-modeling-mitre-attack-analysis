# Risk Assessment Highlights — Training Scenario

## Method

The source worksheet scores **likelihood from 1 to 5** and **impact from 1 to 5**. It calculates a **total rating by adding those two values**, so scores range from 2 to 10. The scale and the sample assessments below are taken from the training worksheet; they are not calibrated probabilities.

## Selected assessed risks

| Attack surface | Source worksheet risk description (paraphrased) | Likelihood | Impact | Score |
| --- | --- | ---: | ---: | ---: |
| Development server | Compromise could expose source code and permit a pivot to production | 5 | 5 | 10 |
| Public admin interface | Exploitation could enable broad control over the service | 5 | 5 | 10 |
| Shared database credentials | Credential reuse between development and production could expose production resources | 5 | 5 | 10 |
| Administrative accounts | Privileged account compromise could cause system takeover | 5 | 5 | 10 |
| Payment-processing server | Compromise could expose sensitive financial information | 4 | 5 | 9 |
| Exposed Git repository | Misconfiguration could leak source code | 5 | 4 | 9 |
| VPN gateway | Exploitation could permit unauthorized internal access | 4 | 5 | 9 |
| Secrets/configuration files | Sensitive key exposure could permit misuse of services | 4 | 5 | 9 |

### Interpretation

The highest-rated training risks concentrate around **unnecessary public exposure, secrets and identity security, privileged interfaces, and connectivity between critical environments**.

## Example attack scenarios from the source report

### 1. Development environment to production

An attacker exploits a development service, finds reused or exposed credentials, and attempts to access production systems. This scenario helps motivate secrets isolation, patching, and segmentation. The report associates this with **T1190, T1552, T1570, and T1059**.

### 2. VPN credentials and internal access

An attacker obtains VPN credentials through theft or reuse, establishes remote access, and tries to move to more sensitive environments. The report associates this with **T1078, T1133, and T1021**.

### 3. Payment application abuse

An attacker compromises a public-facing payment application and attempts to access or extract payment data. The report associates this with **T1190, T1059, and T1041**.

### 4. Monitoring and log tampering

An attacker seeks to disrupt collection or integrity of security events while maintaining access. The report references **T1562, T1070, and T1565**.

## Limitations

These are **hypothetical attack paths and qualitative risk judgments**, not observed breaches. Asset names have been generalized in this portfolio summary. The scores are those in the source worksheet, not independently verified measurements.
