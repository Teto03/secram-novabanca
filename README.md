# Cyber Security Risk Assessment — NovaBanca S.p.A. (SecRAM 2.0)

End-to-end security risk assessment of **NovaBanca S.p.A., a fictional bank**, carried out for the *Cyber Security Risk Assessment* course (MSc Computer Science — Cybersecurity, University of Trento, AY 2025/26).

The assessment follows **SecRAM 2.0**, the security risk assessment methodology developed within the European SESAR programme for air traffic management, adapted here to a banking context.

## Method

1. Primary assets identification and impact assessment (confidentiality, integrity, availability)
2. Supporting assets identification
3. Threat scenarios on supporting assets
4. Likelihood evaluation
5. Risk level evaluation
6. Risk treatment: security controls and residual risk

## Scope

The target of evaluation is the whole ICT estate of NovaBanca, a fictional Italian retail and corporate bank (€18.4 bn total assets, 680,000 retail customers, 47 branches) supervised as a Significant Institution. The analysis covers **9 primary assets** and **25 supporting assets** — from the Temenos T24 core and SWIFT to Active Directory, backups, the network MSP and the ATM fleet — and scores **70 threat scenarios** on the bank's 5×5 likelihood–impact matrix. Two non-malicious resilience scenarios (power outage, data-centre loss) are included to reflect DORA's operational-resilience scope.

**Before treatment:** 6 Critical, 30 High, 34 Medium. **After treatment:** every residual risk is Medium or Low.

## Key results

| # | Threat scenario | Supporting asset | Impact | Likelihood | Risk | Main controls | Residual risk |
|---|---|---|---|---|---|---|---|
| 1 | TS-05 Supply-chain compromise | Network MSP (third party) | 5 | 5 | **Critical** | C-04 third-party risk programme (DORA Art. 28), C-22 zero-trust JIT access, C-26 PAM | Medium |
| 2 | TS-09 Exploit of unpatched CVEs | Temenos T24 core banking | 5 | 4 | **Critical** | C-01 emergency / virtual patching (WAF), C-11 host IDS on AIX | Medium |
| 3 | TS-04 SWIFT fraud via privileged account | Active Directory / IAM | 5 | 4 | **Critical** | C-02 MFA on all privileged accounts, C-25 remove 47 stale accounts, C-26 PAM | Medium |
| 4 | TS-06 Insider data exfiltration | Active Directory / IAM | 5 | 4 | **Critical** | C-05 DLP, C-26 PAM with session recording, C-25 | Medium |
| 5 | TS-01 Ransomware | Backup & DR systems | 5 | 4 | **Critical** | C-03 immutable / offline backups + quarterly DR test | Medium |

Cross-cutting: the four-month CISO vacancy raises the likelihood of almost every scenario, so appointing a permanent CISO (C-06) underpins most treatments.

## Deliverables

- [`report/`](report/) — full risk assessment report (PDF)
- [`risk-register/`](risk-register/) — risk register (Excel, plus a CSV export for quick reading on GitHub)
- [`methodology/`](methodology/) — methodology notes and assumptions

## Notes

- NovaBanca S.p.A. is fictional; no real organization or data is involved.
- SecRAM 2.0 is a SESAR methodology: this repository only applies it and links to the official documentation, it does not redistribute it.
- Individual project.
