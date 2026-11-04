# Proposed Defensive Roadmap

**Status: Recommendations only.** Nothing here should be interpreted as a deployed or tested control in a real environment.

The source threat-model report proposed three complementary types of security response: **monitoring data sources, deception/honeypots, and preventive mitigations**.

## 1. Improve security visibility

**Web and application telemetry**
- Forward relevant application and web server events into centralized monitoring.
- Develop rules for anomalous authentication, suspicious requests, and signs of exploitation.
- Review completeness of ingested telemetry regularly.

**Firewall and remote-access telemetry**
- Monitor VPN authentication and cross-segment traffic, particularly traffic involving development, production, and payment networks.
- Look for scans, unauthorized access patterns, and surprising east–west connections.

**Secrets and file-access monitoring**
- Audit access to sensitive configuration files, credential stores, and repositories.
- Investigate access by unusual accounts or processes and unexpected changes to security logging.

## 2. Consider isolated decoys

The source report recommended these concepts as potential high-signal tripwires:

| Proposed decoy | Intended purpose | Status |
| --- | --- | --- |
| Decoy source-code repository | Alert on unauthorized interaction with a fake code repository | Proposed only |
| Fake payment service with dummy records | Identify probing or access attempts against a simulated sensitive service | Proposed only |
| Nonfunctional admin dashboard | Generate alerts on suspicious authentication attempts | Proposed only |

**Operational safeguards:** Any future implementation would require isolated infrastructure, fake data only, documented owner approval, and security monitoring that distinguishes authorized testing from genuine attacks. No decoy code or deployable configuration is included here.

## 3. Reduce exposure with preventive controls

- **Harden public-facing applications:** Patch vulnerable components, address exposed development directories and unnecessarily public administration surfaces, and consider application firewall rules.
- **Strengthen network separation:** Limit connectivity among development, production, and payment environments and restrict VPN permissions to business need.
- **Secure credentials:** Centralize sensitive secrets, rotate shared credentials, reduce unnecessary privilege, and review access regularly.
- **Protect security telemetry:** Audit changes to SIEM feeds, logging configurations, and security tools to make tampering easier to detect.

## 4. Suggested verification if implemented later

These are **future test ideas**, not procedures already performed as part of this training project:

- Document baseline log coverage and review SIEM ingestion health.
- Exercise alerts with harmless, authorized test events.
- Test approved and disallowed access paths between segments in an isolated environment.
- Sample access logs for secrets repositories and administrative changes.
- Review evidence with system owners and correct false-positive/false-negative assumptions.

## Source limitations

The original training report includes proposed milestones and goals, but **no evidence that the controls were deployed or that target metrics were achieved**. This portfolio intentionally describes them as recommendations rather than results.
