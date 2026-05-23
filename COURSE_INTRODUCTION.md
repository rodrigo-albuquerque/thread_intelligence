# Threat Intelligence — Reference Overview

Reference material on advanced threat intelligence: research, analysis, attribution, and reporting. This document is the top-level index; topic detail lives in the linked documents.

## Topic Index

```mermaid
flowchart TD
    ROOT[THREAT INTELLIGENCE]
    F[FOUNDATIONS]
    A[ANALYSIS]
    D[DELIVERY]
    T1[Threat actor landscape]
    T1B[Threat modelling frameworks]
    T1C[Legal, ethical &amp; policy<br/>considerations]
    T2[Strategic analysis &amp;<br/>threat modelling]
    T3[Threat research, correlation,<br/>infrastructure mapping]
    T4[Reporting &amp; communication]
    T5[End-to-end campaign analysis]

    ROOT --> F --> T1
    F --> T1B
    F --> T1C
    ROOT --> A --> T2
    A --> T3
    ROOT --> D --> T4
    T4 --> T5
```

| Topic | Reference |
|-------|-----------|
| Threat actor categories, motivations, attribution, confidence levels | [THREAT_ACTOR_LANDSCAPE.md](./THREAT_ACTOR_LANDSCAPE.md) |
| Threat modelling frameworks (MITRE ATT&CK, Diamond, Cyber Kill Chain, STRIDE, PASTA) | [THREAT_MODELLING_FRAMEWORKS.md](./THREAT_MODELLING_FRAMEWORKS.md) |
| Legal, ethical & policy considerations (GDPR, CCPA, OSINT ethics, NIST 800-53/61) | [LEGAL_ETHICAL_AND_POLICY.md](./LEGAL_ETHICAL_AND_POLICY.md) |
| Strategic analysis & threat modelling (NIST 800-30, ACH) | *to be added* |
| Threat research, correlation, infrastructure mapping (OSINT, malware analysis, behavioural fingerprinting) | *to be added* |
| Reporting & communication | See [Ransomware Reporting Reference](#ransomware-reporting-reference) below |
| End-to-end campaign analysis | *to be added* |

---

## The Intelligence Maturity Spectrum

```mermaid
flowchart LR
    A[RAW DATA<br/>spreadsheets, noise]
    B[INDICATOR<br/>COLLECTION<br/>IOCs, feeds, lists]
    C[STRUCTURED<br/>ANALYSIS<br/>ACH, ATT&amp;CK,<br/>hypotheses]
    D[STRATEGIC<br/>INTELLIGENCE<br/>decisions, action,<br/>influence]

    A --> B --> C --> D

    style A fill:#fde8e8,stroke:#c00
    style D fill:#e8f5e9,stroke:#2a7
    classDef stuck fill:#fff3cd,stroke:#b8860b
    class B,C stuck
```

Most analysts operate at indicator collection or structured analysis. Strategic intelligence is the output stage where assessments drive decisions.

---

## Frameworks & Tools Quick Reference

| Purpose | Tool / Framework |
|---------|------------------|
| Malware & behaviour analysis | VirusTotal, AnyRun |
| Infrastructure mapping | Shodan, PassiveDNS |
| Structured analysis | MITRE ATT&CK, ACH (Analysis of Competing Hypotheses) |
| Multidimensional intrusion analysis | Diamond Model |
| Attack lifecycle tracking | Cyber Kill Chain |
| Stakeholder-ready outputs | Reporting templates, modern reporting tools |
| Ethical & legal guardrails | GDPR, CCPA, NIST 800-53, NIST 800-61 |

For framework comparison and the Diamond Model in detail, see [THREAT_MODELLING_FRAMEWORKS.md](./THREAT_MODELLING_FRAMEWORKS.md).

---

# Ransomware Reporting Reference

Reference for analysing a ransomware campaign and reporting findings to different stakeholders. Four core competencies:

1. Understanding the threat
2. Connecting technical findings to business impact
3. Prioritising recommendations
4. Tailoring communication for different audiences

## Symptoms vs Early Indicators

The **symptoms** of a ransomware attack (encrypted files, ransom notes) are not the same as the **earlier technical indicators** that allow detection while the attack is still in progress.

```mermaid
flowchart LR
    IA[Initial Access<br/><i>Phishing, RDP brute-force,<br/>VPN exploit</i>]
    LM[Lateral Movement<br/><i>SMB scans, PsExec,<br/>anomalous logons</i>]
    PE[Privilege Escalation<br/><i>Mimikatz, AD enumeration,<br/>new admin accounts</i>]
    EN[Encryption + Ransom Note<br/><i>Files renamed, services down,<br/>backups deleted</i>]

    IA --> LM --> PE --> EN

    subgraph EARLY [EARLY INDICATORS — Detection Window]
        IA
        LM
        PE
    end
    subgraph LATE [SYMPTOMS — Too Late]
        EN
    end

    style EARLY fill:#e8f5e9,stroke:#2a7
    style LATE fill:#fde8e8,stroke:#c00
```

Detection effort belongs on the left side of the timeline. Once symptoms appear, recovery — not prevention — is the only option.

## Technical Findings → Business Impact

Technical findings need to be translated into language that non-technical stakeholders can act on.

```
  TECHNICAL FINDING                       BUSINESS IMPACT
  ─────────────────                       ───────────────

  Encrypted file servers          ───▶    Operations halted, revenue loss
  Exfiltrated customer DB         ───▶    Regulatory fines, brand damage
  Backup systems compromised      ───▶    Recovery cost / time multiplied
  AD domain controller breach     ───▶    Full enterprise trust failure
```

## Recommendation Prioritisation

Recommendations are structured by urgency and impact, not listed flat.

```mermaid
quadrantChart
    title Recommendation Prioritisation
    x-axis Low Impact --> High Impact
    y-axis Low Urgency --> High Urgency
    quadrant-1 CRITICAL — Do now, any cost
    quadrant-2 QUICK WIN — Do now, low effort
    quadrant-3 DEFER — Skip or revisit later
    quadrant-4 PLAN — Schedule carefully
```

## Audience-Tailored Communication

The same incident is reported differently depending on the audience.

```mermaid
flowchart TD
    F[INCIDENT FACTS<br/>single source of truth]
    E[EXECUTIVES<br/>Business risk<br/>£ impact<br/>Decisions needed<br/>Plain English]
    I[IT / SOC<br/>IOCs, TTPs<br/>Detection rules, logs<br/>Remediation steps]
    L[LEGAL / COMPLIANCE<br/>Data exposed<br/>Notification obligations<br/>Regulators involved]

    F --> E
    F --> I
    F --> L

    style F fill:#e3f2fd,stroke:#1565c0
```

## See Also

- [Threat actor types and attribution](./THREAT_ACTOR_LANDSCAPE.md) — categories of actors and how attribution works.
- [Threat modelling frameworks](./THREAT_MODELLING_FRAMEWORKS.md) — MITRE ATT&CK, Diamond Model, Cyber Kill Chain, STRIDE, PASTA.
