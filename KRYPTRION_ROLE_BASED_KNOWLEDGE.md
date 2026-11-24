# KRYPTRION

## Role-Based Knowledge

**Phase II — Role-Based Retrieval-Augmented Generation (RAG)**

**Document:** KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf  
**Version:** 1.0  
**Preparation date:** 23 November 2026  
**Role sections:** SOC Analyst, Security Engineer, IT Operations, Super Admin

*Source status: the two source PDFs named in the preparation brief were not received. See Section 1.5 and the separate source report.*



<div class="pb">

# Section 1 — Document Overview

## 1.1 Document Information

| Attribute | Value |
|---|---|
| Document title | KRYPTRION Role-Based Knowledge |
| Project | KRYPTRION |
| Phase | II — Role-Based Retrieval-Augmented Generation (RAG) |
| Version | 1.0 |
| Preparation date | 23 November 2026 |
| Output file name | KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf |
| Intended consumer | A future Python-based, FAISS-backed, role-based RAG ingestion pipeline |

## 1.2 Purpose

This document is a combined knowledge source for KRYPTRION Phase II. It contains four role-specific knowledge sections (SOC Analyst, Security Engineer, IT Operations, Super Admin). Each section is wrapped in exact start and end markers so that an ingestion pipeline can attach the correct access metadata to every chunk it produces from that section.

## 1.3 Scope

The document covers (a) general cybersecurity and operations knowledge relevant to each role, and (b) the KRYPTRION application functionality that is documented in the evidence available when this document was prepared. It does not describe any capability that has not been established by that evidence. Where a capability is not established, the text says it is **unspecified**.

## 1.4 Evidence Labels Used in This Document

| Label | Meaning |
|---|---|
| [GENERAL] | General cybersecurity or IT operations knowledge. It describes industry practice and does not state that KRYPTRION implements the practice. |
| [KRYPTRION-DOCUMENTED] | Behavior of the KRYPTRION Phase I application established by the Phase I source code and SQL migration files that were inspected (see 1.5). It is a statement about the application design, not proof about any live database unless the text says so. |
| [KRYPTRION-UNSPECIFIED] | A feature, permission, workflow or technical detail that the available evidence does not establish. No answer is given. |
| [PHASE II PROPOSED] | An intended Phase II design element. It does not exist in the current application. |

## 1.5 Source Status and Limitations (read before use)

The preparation brief named two source documents: Cybersecurity_Knowledge_Base_RAG_V2.pdf and KRYPTRION_COMPLETE_PROJECT_DOCUMENTATION.pdf. **Neither file was received when this document was prepared.** Consequently:

- All [GENERAL] content was written from general professional knowledge of widely published frameworks and practices. It is not extracted from Cybersecurity_Knowledge_Base_RAG_V2.pdf and must not be cited as if it were.
- All [KRYPTRION-DOCUMENTED] content comes from the KRYPTRION Phase I application source code and SQL migration files and from the database inspection findings supplied in the brief. It was not taken from KRYPTRION_COMPLETE_PROJECT_DOCUMENTATION.pdf.
- Where the missing project PDF might contain additional detail, the text marks the matter as unspecified rather than guessing.

The separate source report (KRYPTRION_ROLE_BASED_KNOWLEDGE_SOURCE_REPORT.md) lists, per role, which evidence supports which content.

## 1.6 Table of Contents

| Entry | PDF page |
|---|---|
| Section 1 — Document Overview | 2 |
| &nbsp;&nbsp;&nbsp;1.1 Document Information | 2 |
| &nbsp;&nbsp;&nbsp;1.2 Purpose | 2 |
| &nbsp;&nbsp;&nbsp;1.3 Scope | 2 |
| &nbsp;&nbsp;&nbsp;1.4 Evidence Labels Used in This Document | 2 |
| &nbsp;&nbsp;&nbsp;1.5 Source Status and Limitations (read before use) | 2 |
| &nbsp;&nbsp;&nbsp;1.7 Role-Specific Knowledge Separation | 6 |
| &nbsp;&nbsp;&nbsp;1.8 Shared Versus Role-Specific Knowledge | 6 |
| &nbsp;&nbsp;&nbsp;1.9 Access-Boundary Table | 6 |
| &nbsp;&nbsp;&nbsp;1.10 Existing Database Findings Used as Constraints | 6 |
| &nbsp;&nbsp;&nbsp;1.11 Proposed Phase II Retrieval Metadata | 7 |
| &nbsp;&nbsp;&nbsp;1.12 Terminology | 7 |
| Section 2 — SOC Analyst Knowledge | 8 |
| &nbsp;&nbsp;&nbsp;2.1 SOC Responsibilities | 8 |
| &nbsp;&nbsp;&nbsp;2.2 Security Monitoring | 8 |
| &nbsp;&nbsp;&nbsp;2.3 Security Alert Analysis | 9 |
| &nbsp;&nbsp;&nbsp;2.4 Alert Triage and Prioritization | 9 |
| &nbsp;&nbsp;&nbsp;2.5 Incident Identification | 9 |
| &nbsp;&nbsp;&nbsp;2.6 Incident Investigation | 10 |
| &nbsp;&nbsp;&nbsp;2.7 Log Analysis | 10 |
| &nbsp;&nbsp;&nbsp;2.8 Indicators of Compromise (IOCs) | 11 |
| &nbsp;&nbsp;&nbsp;2.9 Threat Intelligence | 11 |
| &nbsp;&nbsp;&nbsp;2.10 MITRE ATT&CK | 11 |
| &nbsp;&nbsp;&nbsp;2.11 Threat Detection | 12 |
| &nbsp;&nbsp;&nbsp;2.12 Incident Response | 12 |
| &nbsp;&nbsp;&nbsp;2.13 Incident Escalation | 12 |
| &nbsp;&nbsp;&nbsp;2.14 Detection Improvement | 13 |
| &nbsp;&nbsp;&nbsp;2.15 Incident Documentation | 13 |
| &nbsp;&nbsp;&nbsp;2.16 Security Reporting | 13 |
| &nbsp;&nbsp;&nbsp;2.17 Relevant Documented KRYPTRION Features and Workflows | 13 |
| Section 3 — Security Engineer Knowledge | 15 |
| &nbsp;&nbsp;&nbsp;3.1 Security Engineering Responsibilities | 15 |
| &nbsp;&nbsp;&nbsp;3.2 Security Architecture | 15 |
| &nbsp;&nbsp;&nbsp;3.3 Vulnerability Management | 16 |
| &nbsp;&nbsp;&nbsp;3.4 Security Hardening | 16 |
| &nbsp;&nbsp;&nbsp;3.5 Threat Modelling | 16 |
| &nbsp;&nbsp;&nbsp;3.6 Network Security | 16 |
| &nbsp;&nbsp;&nbsp;3.7 Application Security | 17 |
| &nbsp;&nbsp;&nbsp;3.8 Infrastructure Security | 17 |
| &nbsp;&nbsp;&nbsp;3.9 Detection Engineering | 17 |
| &nbsp;&nbsp;&nbsp;3.10 MITRE ATT&CK | 18 |
| &nbsp;&nbsp;&nbsp;3.11 Defensive Mitigations | 18 |
| &nbsp;&nbsp;&nbsp;3.12 Security Controls | 18 |
| &nbsp;&nbsp;&nbsp;3.13 Security Assessments | 19 |
| &nbsp;&nbsp;&nbsp;3.14 Secure Configuration | 19 |
| &nbsp;&nbsp;&nbsp;3.15 Security Testing | 19 |
| &nbsp;&nbsp;&nbsp;3.16 Risk Analysis | 19 |
| &nbsp;&nbsp;&nbsp;3.17 Relevant Documented KRYPTRION Features and Workflows | 20 |
| Section 4 — IT Operations Knowledge | 21 |
| &nbsp;&nbsp;&nbsp;4.1 IT Operations Responsibilities | 21 |
| &nbsp;&nbsp;&nbsp;4.2 Infrastructure Administration | 21 |
| &nbsp;&nbsp;&nbsp;4.3 System Administration | 21 |
| &nbsp;&nbsp;&nbsp;4.4 Network Operations | 22 |
| &nbsp;&nbsp;&nbsp;4.5 Service Availability | 22 |
| &nbsp;&nbsp;&nbsp;4.6 Infrastructure Monitoring | 22 |
| &nbsp;&nbsp;&nbsp;4.7 System Maintenance | 22 |
| &nbsp;&nbsp;&nbsp;4.8 Troubleshooting | 22 |
| &nbsp;&nbsp;&nbsp;4.9 Backup and Recovery | 23 |
| &nbsp;&nbsp;&nbsp;4.10 Operational Incident Management | 23 |
| &nbsp;&nbsp;&nbsp;4.11 Configuration Management | 24 |
| &nbsp;&nbsp;&nbsp;4.12 Change Management | 24 |
| &nbsp;&nbsp;&nbsp;4.13 Infrastructure Security | 24 |
| &nbsp;&nbsp;&nbsp;4.14 Operational Documentation | 24 |
| &nbsp;&nbsp;&nbsp;4.15 Relevant Documented KRYPTRION Features and Workflows | 25 |
| Section 5 — Super Admin Knowledge | 26 |
| &nbsp;&nbsp;&nbsp;5.1 Platform Administration | 26 |
| &nbsp;&nbsp;&nbsp;5.2 User Management | 26 |
| &nbsp;&nbsp;&nbsp;5.3 Account Approval and Status Management | 27 |
| &nbsp;&nbsp;&nbsp;5.4 Role Governance | 27 |
| &nbsp;&nbsp;&nbsp;5.5 Access-Control Administration | 27 |
| &nbsp;&nbsp;&nbsp;5.6 Audit Logs | 28 |
| &nbsp;&nbsp;&nbsp;5.7 Accountability | 28 |
| &nbsp;&nbsp;&nbsp;5.8 Security Policy Governance | 28 |
| &nbsp;&nbsp;&nbsp;5.9 Platform Configuration | 29 |
| &nbsp;&nbsp;&nbsp;5.10 Administrative Oversight | 29 |
| &nbsp;&nbsp;&nbsp;5.11 Administrative Incident Escalation | 29 |
| &nbsp;&nbsp;&nbsp;5.12 Platform Monitoring and Governance | 30 |
| &nbsp;&nbsp;&nbsp;5.13 Relevant Documented KRYPTRION Administrative Features and Workflows | 30 |

Page numbers refer to the physical pages of KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf (title page = page 1).

End of table of contents.



## 1.7 Role-Specific Knowledge Separation

The document contains four role-specific sections, each delimited by markers of this exact form:

- `[ROLE_SECTION_START: <role>]` immediately before the section content;
- `[ROLE_SECTION_END: <role>]` immediately after the section content;

where `<role>` is one of `soc_analyst`, `security_engineer`, `it_operations`, `super_admin`.

Rules for the ingestion pipeline:

1. Text between a start marker and its matching end marker belongs to that role only.
2. No role's content appears inside another role's markers.
3. Text outside all markers (this overview) is document overview material. It is not role knowledge and must not be used to grant a role access to another role's section.
4. The whole PDF must not be tagged as accessible to every role.

## 1.8 Shared Versus Role-Specific Knowledge

Shared knowledge consists of general cybersecurity knowledge and applicable KRYPTRION project documentation. It will be handled by the ingestion pipeline as separate shared documents (a pipeline decision outside this file). Role-specific knowledge is the content inside the four marked sections of this file.

Within each role section, general cybersecurity material is included only where it is framed for that role's work. Some general topics (for example MITRE ATT&CK) appear in more than one role section, written from that role's viewpoint. This is intentional so that each role's retrieval boundary is self-sufficient.

## 1.9 Access-Boundary Table

| Role | Shared knowledge | Role-specific knowledge |
|---|---|---|
| SOC Analyst | Yes | SOC Analyst only |
| Security Engineer | Yes | Security Engineer only |
| IT Operations | Yes | IT Operations only |
| Super Admin | Yes | Super Admin governance only |

These are the **intended Phase II retrieval boundaries** [PHASE II PROPOSED]. The table is not evidence that the existing application's permissions have been modified for Phase II.

## 1.10 Existing Database Findings Used as Constraints

The following findings come from a read-only inspection of selected Supabase database objects, as supplied in the preparation brief. They are not a complete security audit.

| Object | Finding |
|---|---|
| `soc_analyst_knowledge`, `security_engineer_knowledge`, `it_operations_knowledge` | Exist in the public schema. Row-Level Security is enabled on all three. |
| SELECT policy (each table) | Requires an authenticated user, account status `approved`, and the table's own role (`soc_analyst`, `security_engineer`, `it_operations` respectively), evaluated through `public.get_user_role()` and `public.get_user_status()`. |
| `user_profiles` | Row-Level Security is enabled. Users can insert and read their own profile and update it subject to the existing policy condition. Approved Super Admins have additional profile SELECT and UPDATE access subject to the existing policy condition. |
| `public.get_user_role()` and `public.get_user_status()` | Return text; read from `public.user_profiles` using `auth.uid()`; owned by `postgres`; SECURITY DEFINER; STABLE; `search_path = public, pg_temp`; EXECUTE granted to `authenticated`. |
| Super Admin and the three knowledge tables | The inspected policies do not give Super Admin automatic SELECT access. |
| Super Admin knowledge table | No `super_admin_knowledge` table was found in the inspected objects, and none is claimed to exist. |

Constraints that follow:

- Super Admin knowledge in this document is limited to platform governance and administration.
- No role is assumed to have access to another role's operational knowledge.
- The existing finding that Super Admin has extra access to `user_profiles` must not be read as unrestricted role assignment or account-status modification.
- The findings do not show that the whole application, all tables, all API endpoints or frontend/backend authorization have been audited, and this document does not claim that the application is secure or that a complete RAG implementation already exists.

## 1.11 Proposed Phase II Retrieval Metadata

The following metadata is a **proposal for the future ingestion pipeline** [PHASE II PROPOSED]. It is not an instruction to change the existing Supabase schema.

```
{ "access_scope": "role", "allowed_roles": ["soc_analyst"],        "section": "SOC Analyst",        "source": "KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf" }
{ "access_scope": "role", "allowed_roles": ["security_engineer"],  "section": "Security Engineer",  "source": "KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf" }
{ "access_scope": "role", "allowed_roles": ["it_operations"],      "section": "IT Operations",      "source": "KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf" }
{ "access_scope": "role", "allowed_roles": ["super_admin"],        "section": "Super Admin",        "source": "KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf" }
```

Chunking guidance for the pipeline [PHASE II PROPOSED]: split each marked section independently; never merge text across a marker boundary; carry the metadata of the enclosing section onto every chunk; fail ingestion if a start marker has no matching end marker or if markers are nested.

## 1.12 Terminology

| Term | Meaning in this document |
|---|---|
| Alert | A record of a possible security event in KRYPTRION or in general SOC practice (context decides). |
| Incident | A confirmed or suspected security event that requires a coordinated response. |
| IOC | Indicator of Compromise. |
| MITRE ATT&CK | A public knowledge base of adversary tactics and techniques. |
| Simulated action | A KRYPTRION action recorded as a simulation; the supplied evidence states that live containment on real endpoints is not performed. |
| RLS | Row-Level Security in PostgreSQL. |

---

[ROLE_SECTION_START: soc_analyst]

# Section 2 — SOC Analyst Knowledge

Section identifier: `soc_analyst`. Intended audience: users whose KRYPTRION role is SOC Analyst. Content in this section is for that role only.

Evidence labels: [GENERAL] general practice; [KRYPTRION-DOCUMENTED] Phase I application behavior established by inspected source code and SQL; [KRYPTRION-UNSPECIFIED] not established; [PHASE II PROPOSED] future design.

Sources for this section: general cybersecurity knowledge authored for this document (the cybersecurity knowledge PDF named in the brief was not received); KRYPTRION Phase I files `src/types/auth.ts`, `src/services/authorizationService.ts`, `src/services/deterministicTriageService.ts`, `src/services/simulatedDetectionEngine.ts`, `src/components/analyst/*`, `supabase/migrations/20261015000000_initial_cyberops_soc_schema.sql`, `20261104000000_detection_improvement_recommendations.sql`, `20261117000000_restrict_incident_tasks_update_policy.sql`.

## 2.1 SOC Responsibilities

[GENERAL] A Security Operations Center (SOC) is the function that continuously watches an organization's systems for signs of attack, decides which signals matter, investigates them, and coordinates the response. Typical responsibilities are: monitoring security telemetry; triaging alerts; investigating suspicious activity; declaring and escalating incidents; supporting containment and recovery; documenting what was found and done; and feeding lessons back into detection. A SOC analyst is the person who performs the first three of these every day. Analysts are commonly organised in tiers: tier 1 performs initial triage and basic enrichment, tier 2 performs deeper investigation and correlation, and tier 3 or threat-hunting staff handle complex cases and proactive search. Smaller teams combine these duties.

[KRYPTRION-DOCUMENTED] KRYPTRION defines the role `soc_analyst` as the role that investigates alerts, correlates them with MITRE ATT&CK, records findings and recommends escalation. The application-level permissions assigned to this role are: read alerts, triage alerts, escalate alerts, add notes, read private analyst notes, read MITRE data, read and update incident tasks, propose actions, read the audit log, and read, review and validate detection improvement recommendations. Whether KRYPTRION models analyst tiers (tier 1, tier 2) is [KRYPTRION-UNSPECIFIED].

## 2.2 Security Monitoring

[GENERAL] Monitoring means collecting telemetry (endpoint events, authentication logs, network flow records, DNS and proxy logs, cloud audit trails, email security events), normalising it, and applying detections that raise alerts. Good monitoring starts from questions the organization must be able to answer, such as "Did any account sign in from an unusual country?" or "Did any server start a command shell it never normally starts?" Coverage gaps matter as much as alerts: a technique with no log source behind it is invisible. Analysts should know which log sources feed their tools and how long data is retained.

[KRYPTRION-DOCUMENTED] KRYPTRION presents alerts to the SOC Analyst in an alert triage dashboard and an alert detail drawer. The alert data in the Phase I application is synthetic or demonstration data: alert records carry an `is_synthetic` flag (default true) and a `provenance` field. Ingestion of live SIEM or agent telemetry is documented as not implemented in Phase I. Real-time feeds from production systems are therefore [KRYPTRION-UNSPECIFIED] beyond that statement.

## 2.3 Security Alert Analysis

[GENERAL] Alert analysis asks four questions in order: What fired and why (the detection logic)? What does the evidence show (raw events, hosts, users, addresses)? Is the activity expected for this environment (asset role, user role, change schedule)? What is the likely adversary objective if the activity is malicious? An alert is a hypothesis, not a verdict. Analysts compare against baselines, enrich indicators with internal context (asset criticality, owner, patch state) and external context (reputation, known infrastructure), and write down the reasoning so another analyst can follow it.

[KRYPTRION-DOCUMENTED] A KRYPTRION alert record contains: an identifier, title, description, severity (critical, high, medium, low, informational), status (new, in_triage, escalated, resolved, false_positive), detection time, source IP, destination IP (optional), host name, user name (optional), a MITRE technique identifier and tactic identifier (optional), a network flow reference (optional), a confidence score from 0 to 100, a structured evidence object, an assigned analyst (optional), and the synthetic/provenance fields. The SOC Analyst role can read all alerts and can create and update alert records according to the database policy definitions.

**Example.** An alert titled "Suspicious PowerShell encoded command" on host `WS-0142` with severity high, technique T1059.001 and confidence 78. The analyst opens the evidence, sees the parent process was an Office application, checks whether the user normally runs scripts, and concludes the behaviour matches malicious macro execution. The note recorded explains this reasoning and the alert moves to escalation.

## 2.4 Alert Triage and Prioritization

[GENERAL] Triage assigns each alert a disposition and priority quickly and consistently. Common dispositions are true positive, benign true positive (real activity that is authorised), false positive (detection fired wrongly) and needs more information. Priority is a function of severity of the behaviour, confidence in the detection, criticality of the affected asset or identity, potential blast radius, and whether activity is ongoing. A simple rubric: critical assets with high-confidence malicious behaviour first; internet-facing systems next; low-confidence alerts on low-value systems last. Time-boxing triage (for example a target of a few minutes per alert) prevents queue starvation. Alert fatigue results when low-fidelity rules produce more alerts than analysts can read; tuning belongs to the detection improvement loop (section 2.14).

[KRYPTRION-DOCUMENTED] KRYPTRION includes deterministic rule-based triage (`deterministicTriageService.ts`). Rule identifiers in the Phase I code follow the pattern `DET-RULE-*`. The application separates these deterministic rule outputs from simulation draft detections, whose identifiers follow the pattern `SIG-DRAFT-*`. The SOC Analyst role holds the permissions to triage and escalate alerts. The exact scoring formula of the deterministic rules is [KRYPTRION-UNSPECIFIED] in this document.

**Example.** Three alerts are open: a critical-severity alert on a domain controller with confidence 90, a medium alert on a test server with confidence 40, and an informational alert about a policy change. The analyst works the domain controller alert first, schedules the test-server alert, and closes the informational alert with a short note.

## 2.5 Incident Identification

[GENERAL] An alert becomes an incident when evidence shows (or strongly suggests) a violation of security policy or an adversary action that needs coordinated handling. Typical triggers: confirmed malicious execution, credential misuse, data exfiltration indicators, ransomware precursors, or the same adversary behaviour across several hosts. Identification also requires a working classification: the incident type (malware, unauthorized access, data loss, denial of service, misuse), a preliminary severity, and the affected assets and users. Related alerts should be grouped so the team tracks one incident, not ten tickets.

[KRYPTRION-DOCUMENTED] KRYPTRION tracks response work as incident tasks linked optionally to an alert. A task has a title, description, target asset, assigned role, status (pending, in_progress, completed, blocked), priority (critical, high, medium, low) and an optional suggested action type. Whether KRYPTRION has a separate "incident" entity distinct from alerts and tasks is [KRYPTRION-UNSPECIFIED].

## 2.6 Incident Investigation

[GENERAL] Investigation reconstructs what happened. A reliable method is to build a timeline from the earliest suspicious event; identify the initial access point; trace execution, persistence and privilege changes; map lateral movement; and determine what data or systems were touched. Preserve evidence before changing systems: capture volatile data and logs where policy allows, record hashes of collected artifacts, and keep a chain-of-custody record if legal action is possible. Distinguish facts (observed in logs) from inferences (reasoned conclusions) and label each in the notes. Pivoting means using one artifact (an IP, a file hash, an account) to find related events.

[KRYPTRION-DOCUMENTED] KRYPTRION provides an investigation workspace and a playbook console for the SOC Analyst role (components `InvestigationWorkspace.tsx` and `PlaybookConsole.tsx`). Analyst notes are a distinct record type: only the SOC Analyst role can create and read them, each note must have non-empty text and records the author, and notes cannot be edited or deleted after they are written. The playbook contents are [KRYPTRION-UNSPECIFIED] in this document.

**Example.** An analyst investigating a suspected credential theft pivots from the alert's user name to authentication events for that account over 24 hours, finds a sign-in from an unfamiliar address immediately after a password reset, and records both observations as separate notes, one stating the fact and one stating the inference.

## 2.7 Log Analysis

[GENERAL] Log analysis turns raw records into answers. Key sources and examples: Windows Security log (event ID 4624 successful logon, 4625 failed logon, 4672 special privileges assigned, 4688 process creation, 4720 account created); Windows System log (7045 service installed); Linux authentication logs (SSH accepted/failed password lines); web server logs (status codes, user agents, unusual paths); DNS logs (rare domains, high query volume); proxy and firewall logs (destinations, bytes transferred); cloud audit logs (console sign-ins, policy changes). Techniques: filter by time window, group by user or host, count by outcome, look for rare values (stacking), compare to a baseline, and correlate across sources by shared fields such as user, host, session and time. Always normalise time zones; a one-hour skew can break a timeline.

**Example.** Many 4625 events for one account from a single address (for example 203.0.113.50) followed by a 4624 success suggests password guessing that succeeded (ATT&CK T1110). The analyst then checks what the account did next.

[KRYPTRION-DOCUMENTED] The SOC Analyst workspace includes explorers for log sources and data components that are backed by the role's knowledge table (`soc_analyst_knowledge`), whose columns referenced by the application include technique, detection strategy, analytic, log source and data component fields. The row content and counts of that table are [KRYPTRION-UNSPECIFIED].

## 2.8 Indicators of Compromise (IOCs)

[GENERAL] An IOC is an observable artifact that suggests compromise: file hashes, IP addresses, domain names, URLs, email sender addresses, registry keys, mutex names, and certificate fingerprints. IOCs are easy to share and match but short-lived: adversaries change infrastructure quickly. The "pyramid of pain" idea ranks indicator types by how costly they are for an adversary to change: hashes and IPs are trivial to change; tools and tactics, techniques and procedures (TTPs) are hard to change. Analysts therefore use IOCs for fast scoping ("which other hosts contacted this domain?") and rely on behavioural detections for durable coverage. Record the source, first seen, last seen and confidence of each IOC, and expire stale ones.

**Example.** A phishing report yields a sender domain, a URL and an attachment hash. The analyst searches mail and proxy logs for all three, finds two other recipients who clicked, and adds those users to the incident scope.

[KRYPTRION-UNSPECIFIED] Whether KRYPTRION has a dedicated IOC store or IOC-matching feature is not established. IP addresses, host names and user names are stored as alert fields, and the alert evidence field can hold structured data.

## 2.9 Threat Intelligence

[GENERAL] Threat intelligence is analysed information about adversaries, their capabilities and their targets. Levels: strategic (trends for leadership), operational (campaigns and adversary behaviour), tactical (TTPs) and technical (IOCs). Useful intelligence is relevant to the organization, timely, accurate and actionable. Common practices: assess source reliability and information credibility separately; use the Traffic Light Protocol (TLP) markings to respect sharing limits; map intelligence to ATT&CK so that detections can be checked for coverage; and avoid blocking on low-confidence indicators without review.

[KRYPTRION-UNSPECIFIED] Integration of external threat intelligence feeds in KRYPTRION is not established by the evidence available.

## 2.10 MITRE ATT&CK

[GENERAL] MITRE ATT&CK is a public knowledge base of adversary behaviour organised as tactics (the adversary's goal) and techniques (how the goal is achieved), with sub-techniques for finer detail. The Enterprise matrix tactics are: Reconnaissance, Resource Development, Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Command and Control, Exfiltration and Impact. Technique identifiers look like T1059 (Command and Scripting Interpreter) and T1059.001 (PowerShell). For an analyst, ATT&CK provides a shared vocabulary: it explains what an observed behaviour is, what an adversary is likely to do next, and which data sources can reveal it.

**Examples.** T1566 Phishing (Initial Access); T1059.001 PowerShell (Execution); T1078 Valid Accounts (Defense Evasion, Persistence, Privilege Escalation, Initial Access); T1110 Brute Force (Credential Access); T1003 OS Credential Dumping (Credential Access); T1021 Remote Services (Lateral Movement); T1486 Data Encrypted for Impact (Impact).

[KRYPTRION-DOCUMENTED] KRYPTRION alerts can carry a MITRE technique and tactic identifier, and the SOC Analyst role has permission to read MITRE data. The SOC knowledge table's referenced columns (technique identifier, name, description, tactics, platforms, detection strategy, analytic, log source, data component) indicate ATT&CK-style reference content. The MITRE explorer view is one of the views authorized for this role.

## 2.11 Threat Detection

[GENERAL] Detections are logic that turns telemetry into alerts. Types: signature or rule-based (known bad), behavioural or analytic (unusual sequences), anomaly-based (statistical deviation) and correlation rules (several weak signals together). Qualities of a good detection: it maps to a technique, names its required log sources, has a documented false-positive profile, and has a test case. Analysts judge detections by precision (how many alerts are real) and recall (how many real events are caught). The Sigma format is a vendor-neutral way to describe log-based detection rules.

[KRYPTRION-DOCUMENTED] KRYPTRION contains a simulated detection engine (`simulatedDetectionEngine.ts`) that produces simulation drafts with `SIG-DRAFT-*` identifiers, kept distinct from deterministic triage rules. The application's own description treats these as simulation, not as production detection content. Deployment of drafts to a real SIEM is [KRYPTRION-UNSPECIFIED].

## 2.12 Incident Response

[GENERAL] A widely used lifecycle (from NIST SP 800-61) is: preparation; detection and analysis; containment, eradication and recovery; and post-incident activity. Containment limits spread (for example isolating a host, disabling an account, blocking an address) and should balance stopping the adversary against losing evidence or alerting them too early. Eradication removes the adversary's presence (malware, persistence, abused accounts). Recovery restores systems and monitors for recurrence. The post-incident review captures what worked and what to improve.

[KRYPTRION-DOCUMENTED] In KRYPTRION the SOC Analyst role can propose actions (`action:propose`) and create incident tasks for other roles. IT Operations role users execute and mark tasks. The application states that containment is simulated and that no live containment is performed on real endpoints. Audit entries for such actions are recorded with simulated statuses (for example SIMULATED_SUCCESS).

**Example.** After confirming a malicious macro on `WS-0142`, the analyst creates a task assigned to IT Operations titled "Isolate WS-0142 from the network" with priority high and a suggested action type, links it to the alert, and records the justification in a note.

## 2.13 Incident Escalation

[GENERAL] Escalation moves an incident to people with more authority or skill. Functional escalation hands the case to a specialist (malware analysis, forensics); hierarchical escalation informs management (for severe business impact). A good escalation message states: what happened, when, what is affected, what has been done, what is needed and by when. Define escalation triggers beforehand (for example confirmed compromise of a privileged account, evidence of data loss, impact on a critical service) so analysts do not hesitate.

[KRYPTRION-DOCUMENTED] The SOC Analyst role has the permission to escalate alerts, and `escalated` is a defined alert status. The organisational escalation path beyond the alert status change (for example who is notified) is [KRYPTRION-UNSPECIFIED].

## 2.14 Detection Improvement

[GENERAL] Every incident and every false positive is an input to detection improvement: tune thresholds, add allow-lists for verified benign behaviour, add missing detections for observed techniques, and retire rules that never produce value. Feedback should be specific enough that an engineer can act on it: which rule, which event, what was wrong, what was expected.

[KRYPTRION-DOCUMENTED] KRYPTRION implements a recommendation exchange between Security Engineers and SOC Analysts. Security Engineers create detection improvement recommendations (status starts as `proposed`). The SOC Analyst role may: accept a proposed or clarification-requested recommendation; reject it (feedback of at least ten characters is required); request clarification (feedback of at least ten characters is required); and later validate a recommendation that the Security Engineer has marked completed. Recommendations cannot be deleted. The SOC Analyst cannot create recommendations. The status values are proposed, accepted, rejected, clarification_requested, in_progress, completed and validated.

**Example.** An analyst sees repeated false positives from a rule that flags administrative PowerShell during patch windows. A Security Engineer proposes a recommendation to add a maintenance-window exclusion. The analyst reviews it, requests clarification about how the window is verified, receives an updated proposal and accepts it. After implementation the analyst validates it against the next patch cycle.

## 2.15 Incident Documentation

[GENERAL] Good documentation lets another person pick up the case and lets the organization learn. Record: timeline with time zone; evidence sources and queries used; decisions and who made them; actions taken and by whom; affected assets and users; indicators; root cause; and open questions. Write observed facts and conclusions separately. Avoid pasting secrets or full credential material into notes.

[KRYPTRION-DOCUMENTED] Analyst notes in KRYPTRION are append-only: they cannot be changed or deleted, and only the SOC Analyst role can read them. Other roles who view an alert do not receive the private analyst notes. The audit log records operational actions and is append-only; the SOC Analyst role can read operational audit entries.

## 2.16 Security Reporting

[GENERAL] Reports differ by audience. Technical incident reports detail timelines and indicators. Management summaries state impact, status and decisions needed. Periodic metrics typically include volume of alerts, mean time to detect, mean time to respond, false-positive rate, and detection coverage by ATT&CK technique. Metrics should drive decisions, not just describe activity.

[KRYPTRION-UNSPECIFIED] Whether KRYPTRION generates formal reports for the SOC Analyst role is not established. The SOC Analyst workspace includes an analytics view among its authorized views; its contents are not specified here.

## 2.17 Relevant Documented KRYPTRION Features and Workflows

| Area | [KRYPTRION-DOCUMENTED] detail for the SOC Analyst role |
|---|---|
| Authorized views | overview, strategies, analytics, log sources, data components, MITRE explorer, alerts, investigations, playbooks, audit, profile |
| Alerts | Read all; triage; escalate; create and update per the defined database policy |
| Notes | Create and read private analyst notes; immutable once written |
| Tasks | Read all incident tasks; create tasks; update tasks |
| Recommendations | Read; accept, reject, request clarification; validate completed items |
| Audit | Read operational audit entries; create operational entries for own actions |
| Knowledge | Read the SOC Analyst knowledge table only |
| Copilot | An advisory AI assistant exists in Phase I. For this role it can use alert evidence including analyst notes and the SOC knowledge table. Its output is advisory and needs human verification. |
| Simulation | Containment actions are simulated; no live containment is performed |

**Workflow summary.** (1) Review the alert queue. (2) Open the alert, read evidence. (3) Check ATT&CK mapping and knowledge records. (4) Record notes. (5) Set status (in triage, escalated, resolved or false positive). (6) If action is needed, create a task for the appropriate role and record justification. (7) Feed detection problems back through the recommendation exchange.

**Unspecified for this role:** live telemetry ingestion, IOC store, threat-intelligence feeds, report generation, analyst tier model, ticketing integration, and the content of playbooks.

[ROLE_SECTION_END: soc_analyst]

---

[ROLE_SECTION_START: security_engineer]

# Section 3 — Security Engineer Knowledge

Section identifier: `security_engineer`. Intended audience: users whose KRYPTRION role is Security Engineer. Content in this section is for that role only.

Evidence labels: [GENERAL] general practice; [KRYPTRION-DOCUMENTED] Phase I application behavior established by inspected source code and SQL; [KRYPTRION-UNSPECIFIED] not established; [PHASE II PROPOSED] future design.

Sources for this section: general cybersecurity knowledge authored for this document (the cybersecurity knowledge PDF named in the brief was not received); KRYPTRION Phase I files `src/types/auth.ts`, `src/services/authorizationService.ts`, `src/components/security-engineer/*`, `supabase/migrations/20261015000000_initial_cyberops_soc_schema.sql`, `20261104000000_detection_improvement_recommendations.sql`, `20261116000000_knowledge_tables_rls_and_grants.sql`, `20261117000000_restrict_incident_tasks_update_policy.sql`.

## 3.1 Security Engineering Responsibilities

[GENERAL] Security engineers design, build and maintain the technical controls that prevent, detect and limit attacks. Typical work: defining security architecture patterns; reviewing designs; managing vulnerabilities; hardening systems; writing and tuning detections; running security assessments; selecting and integrating security tools; and advising developers and operations on risk. The role is preventive and design-oriented, whereas the SOC is reactive and operational; the two meet in detection engineering, where incident findings become better detections.

[KRYPTRION-DOCUMENTED] KRYPTRION defines the role `security_engineer` as the role that analyses tactics, evaluates defensive coverage, and works on detection strategies and mitigations. Application-level permissions: read alerts; read MITRE data; analyse MITRE coverage; read incident tasks; read the audit log; create, read and update detection improvement recommendations. The role has read-only access to alerts and cannot read private SOC analyst notes.

## 3.2 Security Architecture

[GENERAL] Security architecture arranges controls so that the failure of one does not mean compromise. Core principles: least privilege; defense in depth; separation of duties; secure by default; fail closed; minimise attack surface; and zero trust (verify explicitly, assume breach, no implicit trust from network location). Reference frameworks include NIST Cybersecurity Framework 2.0 (functions: Govern, Identify, Protect, Detect, Respond, Recover), NIST SP 800-53 control catalogue, ISO/IEC 27001 and the CIS Critical Security Controls. Architecture reviews check trust boundaries, data flows, authentication and authorization points, secrets handling, logging and recovery.

**Example.** A review of a web application with a database finds that the browser can reach the database API directly. The engineer notes that database authorization (for example row-level policies) becomes the main control and therefore must be tested directly, not assumed from application-side checks.

[KRYPTRION-DOCUMENTED] The KRYPTRION Phase I design applies several of these principles: four separated roles; database policies keyed to role and approval status; a server-side AI component that does not receive credentials from the browser; and no automatic access for administrators to operational data. Deeper architectural detail of the Phase II RAG system is [PHASE II PROPOSED] and not part of the current application.

## 3.3 Vulnerability Management

[GENERAL] Vulnerability management is a cycle: discover assets; scan or assess; prioritise; remediate or mitigate; verify; report. Prioritisation should combine technical severity (CVSS base score), exploit likelihood (for example the EPSS probability and whether the flaw is listed as exploited in the wild in public catalogues), asset criticality and exposure (internet-facing or not), and compensating controls. Patch timelines are commonly tiered: shortest for actively exploited flaws on exposed systems. Exceptions need an owner, a reason, an expiry date and a compensating control.

**Example.** Two flaws have CVSS 9.8 and 7.5. The 9.8 flaw affects an isolated lab host with no sensitive data; the 7.5 flaw is actively exploited and affects an internet-facing gateway. Risk-based ranking puts the 7.5 flaw first.

[KRYPTRION-UNSPECIFIED] Whether KRYPTRION includes a vulnerability scanner or vulnerability tracking module is not established.

## 3.4 Security Hardening

[GENERAL] Hardening reduces attack surface by removing unnecessary software, services and accounts, enforcing secure settings, and restricting privileges. Baselines: CIS Benchmarks and vendor hardening guides. Typical items: disable unused services and ports; enforce multi-factor authentication for administrators; restrict remote administration paths; enable and forward audit logs; apply full-disk encryption on endpoints; set secure defaults in cloud storage and identity configuration; and remove default credentials. Hardened configurations should be defined as code so drift can be detected.

[KRYPTRION-UNSPECIFIED] Hardening status of KRYPTRION's own deployment is not established by this document beyond the database findings in section 1.10, which are not an audit.

## 3.5 Threat Modelling

[GENERAL] Threat modelling identifies what can go wrong before it does. A common approach: draw a data-flow diagram; mark trust boundaries; enumerate threats per element using STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege); rate risk; choose mitigations; and record residual risk. Attack trees and the PASTA method are alternatives. Models should be revisited when architecture changes.

**Example STRIDE row.** Element: an API endpoint that returns role-specific documents. Threat (Information disclosure): a user asks for another role's document by guessing an identifier. Mitigation: authorise every retrieval against the caller's role on the server side and at the data layer, and never trust a role value supplied by the client.

## 3.6 Network Security

[GENERAL] Network security controls include segmentation (separating zones so compromise does not spread freely), firewalls and security groups with default-deny rules, secure remote access, DNS filtering, intrusion detection and prevention, TLS for data in transit, and monitoring of east-west traffic. Key questions: Which systems can talk to which? Which flows cross trust boundaries? What leaves the network and to where?

**Example.** A flat network lets any workstation reach database servers. Segmentation rules limit database access to the application tier, so a compromised workstation cannot query the database directly.

[KRYPTRION-DOCUMENTED] The Phase I application includes a network flow reference on alerts and sample network flow data used for demonstration. The Security Engineer workspace includes analytics and a detection workbench. Network-level controls of the hosting environment are [KRYPTRION-UNSPECIFIED].

## 3.7 Application Security

[GENERAL] Application security addresses flaws in software. Reference: OWASP Top 10 (broken access control, cryptographic failures, injection, insecure design, security misconfiguration, vulnerable components, authentication failures, integrity failures, logging failures, server-side request forgery). Practices: threat model early; validate input on the server; use parameterised queries; apply authorization on every request; manage secrets outside code; keep dependencies updated; perform code review; and use static and dynamic testing. For AI-assisted applications, additional risks include prompt injection, sensitive data disclosure and over-permissive tool access.

**Example.** A search feature builds a query string from user text. Parameterisation or strict allow-list validation prevents injection characters from changing the query.

[KRYPTRION-DOCUMENTED] The Phase I Copilot validates request size and format, restricts which records each role can retrieve, wraps untrusted text in boundary tags, escapes angle-bracket and ampersand characters in untrusted text, redacts secret-like strings in output, and has no tools that can change application state. Its answers are labelled advisory. These controls have not been verified by executed tests in the documentation task that produced this document.

## 3.8 Infrastructure Security

[GENERAL] Infrastructure security covers servers, containers, cloud accounts and supporting services. Priorities: identity and access management with least privilege; secrets management; patching; logging and monitoring; backup protection; network boundaries; image scanning and minimal base images for containers; infrastructure-as-code review; and protection of management planes (cloud console, CI/CD pipelines).

[KRYPTRION-UNSPECIFIED] The hosting platform and its configuration are not established for this document. The Phase I application reads secrets from environment variables and its repository ignores environment files (other than example files); this is a design statement, not an infrastructure review.

## 3.9 Detection Engineering

[GENERAL] Detection engineering treats detections as engineered, tested, versioned assets. Lifecycle: identify a technique or threat; confirm required telemetry exists; write the detection logic; test against benign and malicious samples; document expected false positives; deploy; monitor performance; tune; retire when no longer useful. Detection-as-code stores rules in version control with review and automated tests. The Sigma format expresses rules in a portable way that can be converted to different query languages.

**Example.** To detect suspicious PowerShell (T1059.001), the engineer requires process-creation logging with command lines, writes a rule for encoded-command flags launched from Office parent processes, tests it in a lab, excludes a known management tool by signed path, and measures the false-positive rate for two weeks.

[KRYPTRION-DOCUMENTED] The Security Engineer workspace includes a detection workbench, a security analytics view and an improvement recommendations view. Recommendation records contain: title, detection gap, technical explanation, proposed improvement, MITRE technique and tactic identifiers and names, priority, supporting evidence, optional rule draft reference, optional Sigma draft reference, SOC feedback, implementation notes and status. Whether rules created in the workbench can be deployed to a production detection platform is [KRYPTRION-UNSPECIFIED].

## 3.10 MITRE ATT&CK

[GENERAL] For security engineers ATT&CK is a coverage-planning tool. Map each detection and each preventive control to techniques, find techniques with no coverage, rank gaps by relevance to the organization's threat model, and track improvements. Each technique page lists data sources, mitigations and detection ideas. Be aware that ATT&CK describes behaviour, not guaranteed coverage: having a rule tagged to a technique does not mean every variant is detected. The Enterprise tactics are Reconnaissance, Resource Development, Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Command and Control, Exfiltration and Impact.

**Example.** For T1003 OS Credential Dumping, mitigations include protecting the credential-storing process, restricting privileged accounts, and enabling credential-protection features; detection relies on process-access and process-creation telemetry.

[KRYPTRION-DOCUMENTED] The Security Engineer role holds the permissions to read MITRE data and to analyse MITRE coverage, and its dedicated knowledge table (`security_engineer_knowledge`) references technique, tactic, platform and mitigation fields (technique identifier, name, description, tactics, platforms, mitigation identifier, name and description, mapping type). Row content is [KRYPTRION-UNSPECIFIED].

## 3.11 Defensive Mitigations

[GENERAL] A mitigation is a control that prevents or reduces the impact of a technique. Typical categories: privileged account management, application allow-listing, network segmentation, multi-factor authentication, user training, vulnerability and patch management, audit and logging, restricting file and registry permissions, and execution prevention. Choose mitigations by effectiveness against the likely technique, cost, operational impact and the ability to verify them. Combine preventive and detective mitigations.

**Example.** Against brute-force attacks (T1110): enforce multi-factor authentication, apply account lockout or throttling, monitor failed-logon bursts, and disable legacy authentication protocols.

## 3.12 Security Controls

[GENERAL] Controls are classed as preventive, detective, corrective, deterrent and compensating, and as administrative, technical or physical. A control is only useful if it is implemented, operating and tested; evidence of operation (logs, test results) is part of the control. Control frameworks provide catalogues, but selection should follow risk, not checklist completion.

[KRYPTRION-DOCUMENTED] Controls described for Phase I (design level): role-based views and permissions; row-level security policies on operational tables; triggers that make audit entries and analyst notes append-only; a governance function for account approval; and column-level permissions on user profiles. Their operation in any live environment is [KRYPTRION-UNSPECIFIED] unless confirmed by database inspection; the inspected findings in section 1.10 confirm the knowledge-table and user-profile items listed there only.

## 3.13 Security Assessments

[GENERAL] Assessment types: vulnerability assessment (find and list weaknesses), penetration test (attempt exploitation within agreed rules of engagement), red team exercise (goal-based adversary simulation), architecture review, configuration audit and code review. Define scope, authorisation, rules of engagement, timing, data handling and reporting up front. Findings should have evidence, severity, affected assets, recommended remediation and a retest plan.

## 3.14 Secure Configuration

[GENERAL] Secure configuration means settings chosen deliberately and kept consistent. Good practice: start from a baseline; document deviations; store configuration as code; review changes; scan for drift; keep secrets out of configuration files; and separate production and non-production configurations so test settings cannot affect production.

[KRYPTRION-DOCUMENTED] The Phase I application separates a staging configuration from the default configuration by an explicit environment switch, uses different environment-file chains, and rejects server-side secrets in public client variables in staging mode. Environment variable names are documented in the Phase I project; values are never part of this document.

## 3.15 Security Testing

[GENERAL] Testing verifies that controls work. Layers: unit tests for authorization logic; integration tests with real identities per role; negative tests (attempt what must be denied); fuzzing and input validation tests; dependency scans; dynamic scanning; and for AI features, adversarial prompt tests. A passing positive test ("the allowed user succeeds") never proves a control; the denied case must also be tested.

**Example test design for role isolation.** For each role and each knowledge table, run a SELECT with that role's credentials and record the row count. Expected: rows only for the role's own table, none for the others.

[KRYPTRION-DOCUMENTED] The Phase I repository contains many automated test source files, including role isolation and Copilot tests. Their execution results were not available when this document was prepared, so no pass or fail statement is made.

## 3.16 Risk Analysis

[GENERAL] Risk is commonly expressed as likelihood multiplied by impact, informed by threat, vulnerability and asset value. Qualitative scales (low, medium, high) are quick; quantitative approaches estimate loss in money. A risk register lists each risk, owner, current controls, residual risk, treatment (mitigate, transfer, avoid, accept) and review date. Accepting risk should be a named, time-limited decision by an accountable owner.

**Example.** Risk: a role-based document store returns another role's text because filtering depends on a client-provided parameter. Likelihood: medium. Impact: high. Treatment: enforce role filtering on the server from the verified identity and at the data layer; test cross-role retrieval.

## 3.17 Relevant Documented KRYPTRION Features and Workflows

| Area | [KRYPTRION-DOCUMENTED] detail for the Security Engineer role |
|---|---|
| Authorized views | security engineer overview, MITRE, alerts, audit, profile |
| Alerts | Read-only access to all alerts; no alert modification |
| Analyst notes | No access to private SOC analyst notes |
| Tasks | Read tasks assigned to the Security Engineer role; the role cannot update tasks (an earlier policy that allowed updates was replaced in the latest migration file) |
| Recommendations | Create (status starts as proposed); edit proposal fields while proposed or clarification_requested; move accepted to in_progress; move in_progress to completed with implementation notes of at least ten characters; return clarification_requested to proposed; cannot delete |
| Audit | Read and create operational audit entries for own actions |
| Knowledge | Read the Security Engineer knowledge table only |
| Copilot | Advisory assistant; for this role it can use alert evidence with private notes redacted, MITRE reference data and the Security Engineer knowledge table |

**Workflow summary.** (1) Review alerts and SOC feedback to find detection gaps. (2) Check ATT&CK coverage. (3) Draft a recommendation with evidence and a proposed improvement. (4) Respond to SOC clarification requests. (5) After acceptance, mark in progress, implement, then mark completed with notes. (6) SOC validates.

**Unspecified for this role:** vulnerability scanning module, deployment of rules to a production detection platform, hardening baselines applied to KRYPTRION hosting, penetration test results, and the content of the Security Engineer knowledge table.

[ROLE_SECTION_END: security_engineer]

---

[ROLE_SECTION_START: it_operations]

# Section 4 — IT Operations Knowledge

Section identifier: `it_operations`. Intended audience: users whose KRYPTRION role is IT Operations. Content in this section is for that role only.

Evidence labels: [GENERAL] general practice; [KRYPTRION-DOCUMENTED] Phase I application behavior established by inspected source code and SQL; [KRYPTRION-UNSPECIFIED] not established; [PHASE II PROPOSED] future design.

Sources for this section: general IT operations and infrastructure knowledge authored for this document (the cybersecurity knowledge PDF named in the brief was not received); KRYPTRION Phase I files `src/types/auth.ts`, `src/services/authorizationService.ts`, `src/components/it-operations/*`, `supabase/migrations/20261015000000_initial_cyberops_soc_schema.sql`, `20261116000000_knowledge_tables_rls_and_grants.sql`, `20261117000000_restrict_incident_tasks_update_policy.sql`.

## 4.1 IT Operations Responsibilities

[GENERAL] IT Operations keeps technology services running and recoverable. Core duties: provisioning and maintaining servers, endpoints, networks and cloud resources; monitoring availability and performance; applying patches and updates; managing backups and restoration; handling operational incidents; managing configuration and change; and documenting procedures. In security incidents IT Operations typically carries out technical actions that the security team requests, such as isolating a host, disabling an account, rebuilding a system or restoring data, because it holds the administrative access and operational knowledge needed to do so safely.

[KRYPTRION-DOCUMENTED] KRYPTRION defines the role `it_operations` as the role that executes authorized containment tasks and restores assets. Application permissions: read alerts in a scoped way only (`alert:read_scoped_only`), read incident tasks, update incident tasks, authorize simulated actions (`action:authorize_simulated`), and read the audit log. The role has no permission to triage or escalate alerts, to read private analyst notes, or to create tasks.

## 4.2 Infrastructure Administration

[GENERAL] Infrastructure administration covers the lifecycle of compute, storage and network assets: build from approved images; enrol in monitoring and patching; assign an owner; maintain an accurate inventory; and decommission securely. An up-to-date asset inventory is the foundation of every other operational activity because teams cannot patch, monitor or isolate assets they do not know exist. Use least-privilege administrative accounts, separate administrative and everyday accounts, and log administrative sessions.

**Example.** A new server is built from the approved image, registered in the inventory with an owner and criticality, added to patch groups and monitoring, and only then placed into service.

[KRYPTRION-DOCUMENTED] The IT Operations workspace includes an endpoint inventory view (`EndpointInventoryView.tsx`). The source of inventory data, and whether it is connected to real endpoints, is [KRYPTRION-UNSPECIFIED]; Phase I data is demonstration data.

## 4.3 System Administration

[GENERAL] System administration manages operating systems and services: user and group management, service configuration, scheduled jobs, storage, certificates, time synchronisation and log forwarding. Good habits: automate repeatable work, keep changes small and reversible, record changes, test on non-production first, and keep time synchronised (accurate timestamps are essential for troubleshooting and for security investigations).

## 4.4 Network Operations

[GENERAL] Network operations keeps connectivity reliable and controlled: addressing and DNS, routing and switching, firewall and access rules, VPN and remote access, load balancing, and capacity planning. Monitor link status, latency, packet loss, bandwidth and device health. Keep network diagrams and rule documentation current; undocumented firewall rules accumulate risk. For containment, network teams can isolate a segment or block an address quickly, but every block should be recorded with a reason and a review date.

**Example.** During an incident, an infected workstation is moved to an isolated VLAN that allows access only to the remediation tools and the management console, so analysis can continue without exposing other systems.

## 4.5 Service Availability

[GENERAL] Availability is measured against targets such as a service level objective (for example 99.9 percent monthly uptime allows roughly 43 minutes of downtime in a 30-day month). Practices that support availability: redundancy (no single point of failure), health checks, automatic restart, capacity headroom, graceful degradation, tested failover and clear on-call arrangements. Dependencies must be understood: an application is only as available as its database, DNS, identity provider and network.

## 4.6 Infrastructure Monitoring

[GENERAL] Monitoring covers the four signals often called "golden signals": latency, traffic, errors and saturation, plus resource metrics (CPU, memory, disk, network), service health and certificate expiry. Alerts should be actionable: each alert should tell the on-call person what is wrong and what to check first. Avoid noise: thresholds should reflect real impact. Retain metrics long enough to see trends and plan capacity.

**Example.** A disk-usage alert at 85 percent with a growth forecast gives time to expand storage; a flat alert at 99 percent leaves only minutes.

[KRYPTRION-UNSPECIFIED] Infrastructure monitoring features inside KRYPTRION for IT Operations are not established beyond the endpoint inventory view and the task dashboard.

## 4.7 System Maintenance

[GENERAL] Maintenance includes patching, firmware and software updates, certificate renewal, log rotation, storage clean-up, and periodic review of accounts and permissions. Patching routine: assess, test in a representative environment, schedule in a maintenance window, deploy in stages (pilot group first), verify, and keep a rollback plan. Emergency patches for actively exploited flaws follow an accelerated path but keep the same verification and rollback steps.

## 4.8 Troubleshooting

[GENERAL] A dependable approach: define the symptom precisely; determine what changed recently; reproduce or observe; form hypotheses; test one change at a time; confirm the fix; record cause and resolution. Start with the simplest, most common causes (connectivity, name resolution, disk space, credentials, service state) before deeper analysis. Read logs around the first occurrence, not only the latest error.

**Example.** Users cannot reach an internal application. Steps: confirm the service is listening; confirm name resolution; check the load balancer health status; check the certificate expiry date; review the last deployment or firewall change.

## 4.9 Backup and Recovery

[GENERAL] Backups protect against failure, error and ransomware. The 3-2-1 guideline: keep at least three copies of data, on two different media types, with one copy offsite; a stronger variant adds an immutable or offline copy (3-2-1-1-0 adds one immutable or air-gapped copy and zero errors after verification). Define the recovery point objective (RPO: how much data loss is acceptable) and the recovery time objective (RTO: how long recovery may take) for each service. A backup that has never been restored is unproven: schedule restoration tests and record results. Protect backup credentials and backup consoles from the same attackers.

**Example.** A database has an RPO of 15 minutes and an RTO of 2 hours. Transaction-log backups every 5 minutes meet the RPO; a quarterly restoration test confirms the 2-hour RTO.

[KRYPTRION-UNSPECIFIED] Backup and recovery arrangements for KRYPTRION itself are not established by the evidence available for this document.

## 4.10 Operational Incident Management

[GENERAL] Operational incident management restores normal service quickly. Stages: detect; log and categorise; prioritise by impact and urgency; diagnose; resolve or work around; communicate; close; and review. A major-incident process adds an incident commander, a communications lead, regular status updates and a post-incident review. Security incidents follow the same discipline but add evidence preservation and coordination with the security team: avoid actions that destroy evidence (for example wiping a machine) unless the security team agrees.

**Example.** A security task requests isolation of a host. The operator confirms the asset identity, confirms with the requester whether evidence capture is needed first, performs the isolation, verifies the host is isolated, and records the outcome.

[KRYPTRION-DOCUMENTED] KRYPTRION routes response work to IT Operations as incident tasks. IT Operations sees only tasks assigned to the `it_operations` role, and sees alerts only where an assigned task is linked to the alert. A task has title, description, target asset, priority, status (pending, in_progress, completed, blocked), suggested action type, completion notes, completion time and the identity of the user who completed it. IT Operations can change the progress and completion fields of its tasks; the database trigger rejects changes by this role to assignment, linked alert, title, description, priority, target asset and suggested action type. IT Operations cannot create tasks. The application states that containment is simulated: no live containment on real endpoints is performed, and audit entries use simulated statuses.

**Example workflow in the application.** (1) Open the tasks view. (2) Read the task and the linked alert's permitted details. (3) Mark the task in progress. (4) Perform and verify the authorised action (simulated in Phase I) using the remediation verification step. (5) Mark the task completed with completion notes. (6) The action is recorded in the audit log.

## 4.11 Configuration Management

[GENERAL] Configuration management keeps systems in a known, documented and controlled state. Elements: a configuration management database or inventory; baselines; version-controlled configuration as code; automated drift detection; and approval for changes. Benefits: reproducible builds, faster recovery, and the ability to answer "what changed?" quickly. Secrets must be stored in a secrets manager, not in configuration files.

## 4.12 Change Management

[GENERAL] Change management controls risk from modifications. ITIL commonly distinguishes standard changes (pre-approved, low risk), normal changes (assessed and approved) and emergency changes (urgent, with expedited approval and retrospective review). A good change record states the reason, scope, risk, test evidence, implementation steps, rollback plan, communication and approver. Schedule changes away from critical business periods, and verify success criteria after implementation.

**Example.** A firewall rule change is submitted with the business reason, the exact rule text, a test plan, a rollback rule, an approver and a 30-minute verification step.

[KRYPTRION-UNSPECIFIED] A formal change-management workflow inside KRYPTRION is not established.

## 4.13 Infrastructure Security

[GENERAL] From an operations view, infrastructure security means: patch promptly; enforce multi-factor authentication for administrative access; use separate privileged accounts; restrict management interfaces to dedicated networks; harden baselines (CIS Benchmarks); encrypt data at rest and in transit; protect and monitor backups; forward logs to a central location; and remove unused accounts and services. When responding to security requests, confirm the action against the asset inventory to avoid isolating the wrong system.

**Example.** An alert shows a workstation beaconing to an unknown address. IT Operations blocks the address at the firewall, isolates the workstation, re-images it after the security team captures evidence, and rotates credentials that were used on it.

[KRYPTRION-DOCUMENTED] The IT Operations knowledge table (`it_operations_knowledge`) is the role's reference store; columns referenced by the application include technique, tactic, platform and mitigation fields (technique identifier, name, tactics, platforms, mitigation identifier, name and description, mapping type, platform name, tactic identifier and name). The workspace views for techniques and mitigations are authorized for this role. The IT Operations role is not given the MITRE analysis context in the Phase I Copilot.

## 4.14 Operational Documentation

[GENERAL] Operational documentation includes runbooks (step-by-step procedures), architecture and network diagrams, asset inventories, contact and escalation lists, maintenance schedules and post-incident records. Good runbooks state prerequisites, exact steps, expected results, verification and rollback. Keep documentation next to the work, review it regularly and record the date of last verification. Never place passwords or keys in documentation.

## 4.15 Relevant Documented KRYPTRION Features and Workflows

| Area | [KRYPTRION-DOCUMENTED] detail for the IT Operations role |
|---|---|
| Authorized views | IT operations overview, techniques, mitigations, tasks, alerts, audit, profile |
| Alerts | Read only alerts that are linked to tasks assigned to this role |
| Analyst notes | No access |
| Tasks | Read and update tasks assigned to this role; progress and completion fields only; cannot create tasks |
| Simulated actions | Authorize simulated actions; no live containment is performed |
| Audit | Read and create operational audit entries for own actions |
| Knowledge | Read the IT Operations knowledge table only |
| Copilot | Advisory assistant; for this role it can use assigned tasks and their linked alerts (private notes redacted) and the IT Operations knowledge table; it cannot use MITRE analysis or unassigned records |
| Inventory | Endpoint inventory view and remediation verification dialog exist; data origin unspecified |

**Unspecified for this role:** real endpoint management integration, backup system integration, change-management workflow, monitoring integrations, ticketing integrations, and the content of the IT Operations knowledge table.

[ROLE_SECTION_END: it_operations]

---

[ROLE_SECTION_START: super_admin]

# Section 5 — Super Admin Knowledge

Section identifier: `super_admin`. Intended audience: users whose KRYPTRION role is Super Admin. Content in this section is for that role only and is limited to platform governance and administration.

Evidence labels: [GENERAL] general practice; [KRYPTRION-DOCUMENTED] Phase I application behavior established by inspected source code and SQL, or by the database findings supplied for this document; [KRYPTRION-UNSPECIFIED] not established; [PHASE II PROPOSED] future design.

Scope statement: this section does not contain operational investigation, engineering or infrastructure procedures belonging to other roles. It does not state or imply that a Super Admin can read other roles' operational knowledge. The inspected database findings show that Super Admin has no automatic SELECT access to the three role-specific knowledge tables.

Sources for this section: general governance and access-management knowledge authored for this document (the cybersecurity knowledge PDF named in the brief was not received); KRYPTRION Phase I files `src/types/auth.ts`, `src/services/authorizationService.ts`, `src/components/admin/*`, `scripts/bootstrapAdmin.ts`, `supabase/migrations/20261016000000_user_registration_and_governance.sql`, `20261031021500_super_admin_reference_datasets_aggregate_rpc.sql`, `20261114000300_secure_platform_bootstrap_state.sql`, `20261115000000_platform_identity_and_governance_upgrade.sql`; and the database findings in section 1.10.

## 5.1 Platform Administration

[GENERAL] Platform administration is the stewardship of a system's users, access rules, configuration and oversight records, as distinct from the day-to-day operational work done on the data the platform holds. Good administration is accountable (every privileged action is attributable), minimal (administrators hold only the powers their duty needs) and verifiable (actions leave records that others can review). Administrators are high-value targets, so their accounts need the strongest protections available.

[KRYPTRION-DOCUMENTED] The KRYPTRION role `super_admin` is defined for platform administration, health oversight and governance. Application-level permissions: platform administration (`platform:admin`), platform health reading (`platform:health_read`), audit reading and audit export. The views authorized for the role are the administration dashboard, a platform intelligence dashboard, the audit view and the profile page. The role is not given permissions to read or triage alerts, read analyst notes, read or update incident tasks, or work with detection improvement recommendations.

## 5.2 User Management

[GENERAL] User management follows the identity lifecycle: joiner (request, approval, provisioning), mover (role change) and leaver (deactivation and removal of access). Controls: an authoritative request and approval step; unique accounts for each person; prompt removal of access when a person leaves; periodic review of who holds which role; and records of every change.

[KRYPTRION-DOCUMENTED] New registrations in KRYPTRION create a user profile with no role assigned and account status `pending`. The defined account statuses are pending, approved, disabled and rejected. A user whose account is not approved is not given application access by the Copilot service. Each approved role holder receives a platform user identifier with a prefix by role (SA, SOC, IT, SE) when a role is first assigned; the identifier is intended to stay fixed.

**Example.** A new colleague registers. The Super Admin sees a pending profile, confirms through the organisation's own approval process that the person should have access and which role is appropriate, and then approves the account with that role and a recorded justification.

## 5.3 Account Approval and Status Management

[GENERAL] Account approval verifies identity and entitlement before access is granted. Status changes should always carry a reason. Suspension (temporary) and deactivation or rejection (more permanent) should be distinguishable, and reactivation should require a deliberate decision.

[KRYPTRION-DOCUMENTED] Account status changes are performed through a database governance function (`admin_govern_user_profile`) that takes the target user, an action, an optional role and a justification. The defined actions are approve, reject, change role, suspend, deactivate and reactivate. Rules defined in the SQL migration file: the caller must be an approved Super Admin using an authenticated session; an administrator cannot govern their own account; the Super Admin role cannot be assigned through this function; the last active approved Super Admin cannot be demoted, disabled or deleted; and every governance action writes an audit entry. These rules are defined in the migration files; their application in each live environment has not been verified by this document. The existing profile-table policies (own-profile access plus extra Super Admin select and update access subject to policy conditions) must not be read as giving unrestricted role assignment or status modification.

**Example: last-administrator protection.** Only one approved Super Admin remains and a request arrives to suspend that account. The governance rules refuse the change, so the platform cannot be left without an administrator. The organisation must first approve and establish another Super Admin through its established administrative process.

## 5.4 Role Governance

[GENERAL] Role governance defines which roles exist, what each may do, who may hold them and how they change. Principles: least privilege; separation of duties (no single person controls both the doing and the approving of a sensitive action); role definitions kept in writing; and periodic recertification where role owners confirm that each holder still needs the role.

[KRYPTRION-DOCUMENTED] KRYPTRION defines four roles: SOC Analyst (`soc_analyst`), Security Engineer (`security_engineer`), IT Operations (`it_operations`) and Super Admin (`super_admin`). Role changes occur through the governance function described in 5.3. The Phase I database design also restricts the governance function from creating further Super Admins; the first Super Admin is created through a one-time bootstrap procedure run by a platform operator with service-level access, which cannot be repeated once completed. Procedures for creating additional Super Admins beyond that are [KRYPTRION-UNSPECIFIED].

**Example: role change request.** A SOC Analyst transfers to a security engineering team. The Super Admin records the approval reference and changes the role with a justification. Because role knowledge is separated by role, the user's access to role-specific knowledge changes with the role change; the effect on previously held items is governed by the role-specific policies.

## 5.5 Access-Control Administration

[GENERAL] Access-control administration maintains the rules that decide who can see and do what: role-to-permission mappings, data-level restrictions, and administrative boundaries. Typical safeguards are default deny, explicit grants, regular review of grants, protection of the administrative interface, and testing that denied requests are in fact denied.

[KRYPTRION-DOCUMENTED] The administration area contains an access control matrix view, a data source inventory view, and a platform intelligence dashboard. Facts established for the database: row-level security is enabled on the user profiles table and on the three role-specific knowledge tables; the knowledge-table policies require an authenticated, approved user holding the table's own role; role and status are determined by two helper functions that read the caller's own profile; and Super Admin has no automatic read access to the knowledge tables. The platform intelligence view uses an aggregate-only database function that returns counts and distributions of reference datasets and does not return raw knowledge rows; the function checks that the caller is an approved Super Admin. The detailed contents of these views are [KRYPTRION-UNSPECIFIED]. The matrix of intended Phase II retrieval boundaries in section 1.9 is [PHASE II PROPOSED] and does not describe existing application behavior.

## 5.6 Audit Logs

[GENERAL] Audit logs record who did what, to what, when and with what result. To be trustworthy they must be complete for privileged actions, protected from alteration, time-synchronised, and reviewed. Separate platform-level (governance) records from operational records so that administrators can review governance events without needing operational detail.

[KRYPTRION-DOCUMENTED] KRYPTRION keeps audit entries in two categories: platform and operational. The Super Admin role can read platform-category entries only; operational-category entries are visible to the three operational roles. Audit entries are append-only: database triggers reject updates and deletions. Each entry records the actor, actor role, action type, target, status, justification and metadata fields. A separate account activity history records events such as registration, approval, role change, profile change, sign-in, sign-out, password change and session revocation. Each user can read their own account activity, and a scoped database function can return a limited summary of a target user's governance-related activity to a Super Admin. Account activity rows are retained for a defined period after account deletion in anonymised form according to the migration files. The role has the permission to export audit data; the export format and process are [KRYPTRION-UNSPECIFIED].

## 5.7 Accountability

[GENERAL] Accountability means every privileged action can be tied to a named individual and a justification. Requirements: unique, non-shared administrator accounts; mandatory justification for sensitive changes; immutable records; and review by someone other than the actor. Shared accounts and undocumented changes destroy accountability.

[KRYPTRION-DOCUMENTED] Governance actions require a justification and record the acting administrator, and administrators cannot govern their own accounts. Platform audit entries cannot be altered or removed by application roles. Whether a second-person approval step exists for administrative actions is [KRYPTRION-UNSPECIFIED].

## 5.8 Security Policy Governance

[GENERAL] Security governance organises policies in a hierarchy: policy (what and why), standard (mandatory requirements), procedure (step-by-step) and guideline (advice). Governance frameworks include the NIST Cybersecurity Framework 2.0 "Govern" function and ISO/IEC 27001 management-system requirements. Each policy needs an owner, an approval record, a review date and an exception process in which exceptions are time-limited and recorded. Policy should be tied to risk decisions made by accountable leadership.

**Example policy items for a platform like KRYPTRION:** account approval requires a documented request; administrators use dedicated accounts; role recertification is performed at a set interval; audit records are retained for a defined period; and access exceptions expire.

[KRYPTRION-UNSPECIFIED] Formal KRYPTRION security policies, their owners and review intervals are not established by the evidence available. The Phase I project describes technical enforcement of roles and audit records, not organisational policy documents.

## 5.9 Platform Configuration

[GENERAL] Platform configuration governance covers environments (production, staging, development), secrets handling, feature settings and release control. Principles: separate environments so test activity cannot affect production; keep secrets out of source and documents; restrict who can change production configuration; record each change; and review configuration regularly.

[KRYPTRION-DOCUMENTED] The Phase I application separates a staging configuration from the default configuration through an explicit environment switch and a separate env-file chain, and the repository excludes environment files from version control except example files. The service-level key is used by server components for a limited set of operations and by the one-time bootstrap script; it is not exposed to the browser. Environment values are never included in this document. Hosting configuration and release procedures are [KRYPTRION-UNSPECIFIED].

## 5.10 Administrative Oversight

[GENERAL] Oversight is the regular review of governance health. Typical reviews: pending and stale accounts; accounts with no recent sign-in; role holders versus the approved list; recent administrative changes; failed or unusual administrative sign-ins; and exceptions nearing expiry. Findings go to accountable owners with deadlines.

[KRYPTRION-DOCUMENTED] User profiles carry creation, approval and last-sign-in information, and the platform audit log and account activity history provide governance records. The administration dashboard presents platform information to the Super Admin; its exact metrics are [KRYPTRION-UNSPECIFIED].

**Example: dormant account review.** A Super Admin reviews approved accounts with an old last-sign-in time, asks the account's line owner whether access is still needed, and suspends accounts without a justified need, recording the reason.

## 5.11 Administrative Incident Escalation

[GENERAL] Administrative (governance) escalation concerns decisions and communication around a significant incident, not the technical handling. It involves: informing designated executives and risk owners; engaging legal, privacy and compliance functions when personal data or regulated data may be involved; deciding whether external notification is required (obligations differ by jurisdiction and contract and must be confirmed with legal counsel); authorising emergency measures such as temporarily restricting access; and ensuring decisions are recorded. A pre-agreed escalation contact list and criteria shorten delay.

**Example.** A governance review finds that an account holds a role that its owner says is no longer required. The Super Admin escalates to the account's management chain and the platform owner, records the decision, and suspends the account pending confirmation.

[KRYPTRION-UNSPECIFIED] An administrative escalation workflow, notification mechanism or on-call process within KRYPTRION is not established.

## 5.12 Platform Monitoring and Governance

[GENERAL] Governance monitoring tracks platform health and compliance with rules: service availability, authentication events, changes to privileged roles, and audit-log continuity. Metrics should be few and meaningful: number of pending approvals and their age; number of role holders per role; number of administrative changes per period; and audit-log availability.

[KRYPTRION-DOCUMENTED] The Super Admin role holds the `platform:health_read` permission. In the Phase I Copilot the Super Admin can ask about platform health and general platform topics; answers use governance audit records only, and requests that concern alert triage, remediation tasks or alert and task identifiers are refused for this role. A database function gives the role aggregate counts for reference datasets without exposing raw rows. The platform health data sources are [KRYPTRION-UNSPECIFIED].

## 5.13 Relevant Documented KRYPTRION Administrative Features and Workflows

| Area | [KRYPTRION-DOCUMENTED] detail for the Super Admin role |
|---|---|
| Authorized views | administration, platform intelligence, audit, profile |
| Permissions | platform administration, platform health reading, audit read, audit export |
| User profiles | Read all profiles; extra update access subject to the profile policy condition; status and role changes through the governance function |
| Governance actions | approve, reject, change role, suspend, deactivate, reactivate, each with justification and an audit entry |
| Safeguards | no self-governance; Super Admin role not assignable through governance; last active Super Admin protected |
| Bootstrap | one-time creation of the first Super Admin by a service-level operator procedure; not repeatable |
| Audit | Read platform-category audit entries; append-only |
| Account activity | Own activity; scoped governance summary for a target user |
| Knowledge | No automatic read access to the SOC Analyst, Security Engineer or IT Operations knowledge tables; no `super_admin_knowledge` table is claimed to exist |
| Operational data | No read access to alerts, analyst notes, incident tasks or recommendations under the Phase I policies defined in the migration files |
| Copilot | Advisory; governance audit records only |

**Workflow summary.** (1) Review pending registrations. (2) Verify entitlement outside the platform. (3) Approve, reject or hold with a justification. (4) Periodically review role holders and dormant accounts. (5) Review platform audit records. (6) Record exceptions and escalate governance concerns to accountable owners.

**Unspecified for this role:** second-person approval for admin actions, audit export format, administrative escalation workflow, procedure for creating additional Super Admins, formal security policy documents, platform health data sources, and the exact content of administration dashboards.

[ROLE_SECTION_END: super_admin]

