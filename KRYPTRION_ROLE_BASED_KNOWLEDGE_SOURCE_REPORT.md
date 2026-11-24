# KRYPTRION Role-Based Knowledge — Source Report

| Attribute | Value |
|---|---|
| Project / phase | KRYPTRION, Phase II (role-based RAG) |
| Companion deliverables | `KRYPTRION_ROLE_BASED_KNOWLEDGE.pdf`, `KRYPTRION_ROLE_BASED_KNOWLEDGE.md` |
| Version / date | 1.0 / 23 November 2026 |
| Mode | Read-only. No database, policy, function, trigger, credential or Phase I application file was modified. |

## 1. Critical finding: the two named source documents were not received

The brief names two source documents. Neither was available in the uploaded files or anywhere in the working environment:

| Named source | Received? | Consequence |
|---|---|---|
| `Cybersecurity_Knowledge_Base_RAG_V2.pdf` | **No** | No content was extracted from it. All general cybersecurity and IT-operations content was **authored from general professional knowledge** of public frameworks and practices (MITRE ATT&CK, NIST SP 800-61, NIST CSF 2.0, OWASP Top 10, STRIDE, CIS Benchmarks, CVSS/EPSS, ITIL change types, 3-2-1 backup, and similar). It must not be cited as originating from that PDF. |
| `KRYPTRION_COMPLETE_PROJECT_DOCUMENTATION.pdf` | **No** | KRYPTRION-specific content was taken instead from the Phase I application ZIP (`kryptrion---ai-security-operations-platform__1_.zip`) and its SQL migrations, which were inspected in the earlier documentation task, plus the database findings given in the brief. That PDF may contain details, terminology or workflows not reflected here. |

What was actually used:

1. Phase I source code and SQL migration files (verified by reading, not by execution).
2. The "existing database security findings" in section 3 of the brief (taken as supplied; not independently re-inspected, because no database access exists in this task).
3. The author's general knowledge, for all [GENERAL] content.

**Recommendation:** supply the two PDFs so the document can be reconciled against them. Expected effects: more KRYPTRION terminology and workflow detail, and replacement of authored general content with the supplied knowledge base where preferred.

## 2. Content classification

The PDF labels every substantive paragraph with one of four tags.

| Tag | Meaning | Origin in this document |
|---|---|---|
| [GENERAL] | General cybersecurity / operations knowledge | Authored (no supplied general-knowledge PDF) |
| [KRYPTRION-DOCUMENTED] | KRYPTRION behavior established by evidence | Phase I source and SQL files; brief section 3 for database items |
| [KRYPTRION-UNSPECIFIED] | Not established by the evidence | No answer is given |
| [PHASE II PROPOSED] | Future design | Brief sections 5 to 7 (boundaries, markers, metadata) |

"Documented" means defined in source code or SQL migration files. Unless the text cites the brief's findings, it does **not** mean verified in a live database.

## 3. Evidence supporting each role section

### 3.1 SOC Analyst (`soc_analyst`)

| Content | Class | Evidence |
|---|---|---|
| SOC duties, monitoring, triage, investigation, log analysis (event IDs), IOCs, threat intelligence, incident response, escalation, documentation, reporting | [GENERAL] | Authored |
| MITRE ATT&CK tactic list and example techniques (T1566, T1059.001, T1078, T1110, T1003, T1021, T1486) | [GENERAL] | Authored |
| Role definition and permission list | [KRYPTRION-DOCUMENTED] | `src/types/auth.ts` (`ROLE_METADATA`, `ROLE_PERMISSIONS`) |
| Authorized views | [KRYPTRION-DOCUMENTED] | `src/services/authorizationService.ts` |
| Alert fields, severities, statuses | [KRYPTRION-DOCUMENTED] | `20261015000000_initial_cyberops_soc_schema.sql` |
| Immutable SOC-only analyst notes | [KRYPTRION-DOCUMENTED] | Same migration (table, policies, immutability trigger) |
| Tasks and their statuses | [KRYPTRION-DOCUMENTED] | Same migration; `20261117000000` |
| Recommendation review states and 10-character feedback rule | [KRYPTRION-DOCUMENTED] | `20261104000000_detection_improvement_recommendations.sql` |
| `DET-RULE-*` and `SIG-DRAFT-*` identifier patterns; simulated detection | [KRYPTRION-DOCUMENTED] | `deterministicTriageService.ts`, `simulatedDetectionEngine.ts`, Copilot prompt text |
| SOC knowledge table and its policy | [KRYPTRION-DOCUMENTED] | Brief section 3.1; `20261116000000_knowledge_tables_rls_and_grants.sql`; column names from `knowledgeService.ts` |
| Synthetic data, no live SIEM ingestion | [KRYPTRION-DOCUMENTED] | `is_synthetic`/`provenance` columns; README section 25 |

### 3.2 Security Engineer (`security_engineer`)

| Content | Class | Evidence |
|---|---|---|
| Security architecture, vulnerability management, hardening, threat modelling (STRIDE), network/application/infrastructure security, detection engineering, mitigations, controls, assessments, secure configuration, testing, risk analysis | [GENERAL] | Authored |
| Role definition, permissions, views | [KRYPTRION-DOCUMENTED] | `auth.ts`, `authorizationService.ts` |
| Read-only alerts; no private notes | [KRYPTRION-DOCUMENTED] | Initial migration policies |
| Recommendation creation and lifecycle | [KRYPTRION-DOCUMENTED] | `20261104000000` |
| Security Engineer cannot update tasks | [KRYPTRION-DOCUMENTED] (SQL definition) | `20261117000000` (replaced an earlier policy that allowed it) |
| Security Engineer knowledge table | [KRYPTRION-DOCUMENTED] | Brief section 3.1; `20261116000000` |
| Phase I Copilot input controls | [KRYPTRION-DOCUMENTED] | `src/server/ai/*` |
| Staging/default configuration separation | [KRYPTRION-DOCUMENTED] | `src/server/env/environmentLoader.ts`, `.gitignore` |

### 3.3 IT Operations (`it_operations`)

| Content | Class | Evidence |
|---|---|---|
| Infrastructure and system administration, network operations, availability, monitoring, maintenance, troubleshooting, backup and recovery (RPO/RTO, 3-2-1), incident management, configuration and change management, documentation | [GENERAL] | Authored |
| Role definition, permissions, views | [KRYPTRION-DOCUMENTED] | `auth.ts`, `authorizationService.ts` |
| Scoped alert access (only task-linked alerts), task update limits, no task creation | [KRYPTRION-DOCUMENTED] | Initial migration policies and task-mutation trigger; `20261117000000` |
| Simulated containment | [KRYPTRION-DOCUMENTED] | Audit status values and application description in the Phase I source |
| IT Operations knowledge table | [KRYPTRION-DOCUMENTED] | Brief section 3.1; `20261116000000` |
| Endpoint inventory view, remediation verification dialog (existence only) | [KRYPTRION-DOCUMENTED] | `src/components/it-operations/*` (file names) |

### 3.4 Super Admin (`super_admin`)

| Content | Class | Evidence |
|---|---|---|
| Administration, identity lifecycle, role governance, access-control administration, audit-log principles, accountability, policy hierarchy, configuration governance, oversight, administrative escalation (non-technical) | [GENERAL] | Authored |
| Role definition, permissions, views | [KRYPTRION-DOCUMENTED] | `auth.ts`, `authorizationService.ts` |
| Account statuses, pending registration with no role | [KRYPTRION-DOCUMENTED] | `20261016000000_user_registration_and_governance.sql` |
| Governance function, actions, safeguards (no self-governance, last Super Admin protected, Super Admin not assignable) | [KRYPTRION-DOCUMENTED] (SQL definition) | `20261115000000_platform_identity_and_governance_upgrade.sql` |
| One-time bootstrap of first Super Admin | [KRYPTRION-DOCUMENTED] | `scripts/bootstrapAdmin.ts`; `20261016000000`; `20261114000300` |
| Platform vs operational audit separation; append-only audit | [KRYPTRION-DOCUMENTED] | Initial migration policies and triggers |
| Aggregate-only reference datasets function | [KRYPTRION-DOCUMENTED] | `20261031021500_super_admin_reference_datasets_aggregate_rpc.sql` |
| No automatic access to the three knowledge tables; no `super_admin_knowledge` table claimed | [KRYPTRION-DOCUMENTED] | Brief sections 3.1 and 3.4; `20261116000000` |
| Profile-table policies (own-profile access plus extra Super Admin select/update) | [KRYPTRION-DOCUMENTED] | Brief section 3.2. Not read as unrestricted role or status modification. |

## 4. General knowledge versus KRYPTRION-specific content

- **General knowledge** appears in every role section, written from that role's viewpoint. Overlap (for example MITRE ATT&CK in the SOC Analyst and Security Engineer sections) is intentional so each role's retrieval boundary stands alone.
- **KRYPTRION-specific content** is concentrated in the last subsection of each role section (2.17, 3.17, 4.15, 5.13) and in short [KRYPTRION-DOCUMENTED] paragraphs within topics.
- **Super Admin** content is governance only. A text check of the final PDF found none of the operational terms searched for (playbook, IOC, Sigma, hardening, backup, runbook, log analysis, pivot). The word "triage" appears only in statements that the role is not permitted to triage alerts.

## 5. Features, permissions and details left unspecified

| Role | Unspecified (not established by evidence) |
|---|---|
| SOC Analyst | Live telemetry ingestion, IOC store, threat-intelligence feeds, report generation, analyst tier model, ticketing integration, playbook contents, exact deterministic scoring formula, a distinct "incident" entity |
| Security Engineer | Vulnerability scanning module, deployment of rules to a production detection platform, hardening baselines of KRYPTRION hosting, penetration test results, knowledge-table content |
| IT Operations | Real endpoint management and backup integration, change-management workflow, monitoring integrations, ticketing integration, inventory data origin, knowledge-table content |
| Super Admin | Second-person approval for admin actions, audit export format, administrative escalation workflow, procedure for additional Super Admins, formal security policy documents, platform health data sources, dashboard metrics |
| All | Content, size and provenance of the three knowledge tables; Phase II ingestion implementation |

## 6. Conflicts and points to note

| # | Point | Detail |
|---|---|---|
| 1 | **Helper-function `search_path`** | Brief section 3.3 reports `public, pg_temp` for `get_user_role()` and `get_user_status()`. The repository migration `20261115000100_harden_service_role_and_security_definer_functions.sql` sets `search_path = ''` for these functions. The inspected database therefore does not match that migration file (or the migration was not applied there, or the report concerns a different environment). The cause is unknown and was not resolved. The PDF states the brief's finding in section 1.10 and does not repeat the migration's value. |
| 2 | **Environment of the inspected database** | The brief says "existing Supabase database objects" without naming Original production or KRYPTRION-STAGING. The environment is therefore unspecified, and the findings are not attributed to either. |
| 3 | **Super Admin profile access** | Brief section 3.2 says approved Super Admins have additional profile UPDATE access "subject to the existing policy condition". The migrations additionally restrict direct updates to specific columns and send role and status changes through a governance function. The PDF describes this and warns against inferring unrestricted role or status modification. Live column privileges are not verified. |
| 4 | **Overlap of knowledge-table policies with migrations** | The brief's SELECT-policy findings are consistent with `20261116000000`. Consistency of definition does not prove the migration was applied. |
| 5 | **Source of KRYPTRION detail** | KRYPTRION detail comes from the Phase I ZIP, not the named project PDF (section 1 above). |

## 7. Assumptions and limitations

1. Role names and identifiers (`soc_analyst`, `security_engineer`, `it_operations`, `super_admin`) follow the brief and the Phase I source.
2. The brief's database findings are taken as given. They are not a complete audit, and the PDF makes no claim that the application is secure, that all tables or endpoints were inspected, or that a Phase II RAG implementation exists.
3. The access-boundary table and metadata examples are labelled [PHASE II PROPOSED]. They do not show that existing application permissions have changed.
4. General knowledge was written without access to the supplied general-knowledge PDF. Statements such as framework phase names, event IDs and technique identifiers reflect widely published material but were not checked against a retrieved source in this task.
5. Example addresses, host names and scenarios are fictional. No credentials, tokens or secrets appear.

## 8. Notes for the ingestion pipeline

1. **Markers.** All eight markers occur exactly once, in order, each on its own line, and are extractable with standard PDF text extraction. Each role section starts on a new page. The Markdown file contains the same markers.
2. **Overview is not role knowledge.** Section 1 (including the table of contents and the proposed-metadata block) lies outside all markers. Treat it as document overview or shared material, never as a source of role access.
3. **Page footer text.** Every page carries a stamped footer ("KRYPTRION Role-Based Knowledge | v1.0 | Page N of M"). It will appear in extracted text and can fall inside role sections. Strip it before chunking.
4. **Ligatures.** The PDF was generated with ligatures disabled; extraction returns plain letters (the only non-ASCII character is the em dash).
5. **Table of contents.** Page numbers refer to physical PDF pages (title page = 1). They were computed from the rendered PDF and checked against it. In the Markdown file they describe the PDF, not Markdown pagination.
6. **Chunk-level tags.** Paragraph labels ([GENERAL] and so on) can be kept as chunk text or parsed into an `evidence_class` field if desired.
7. **Shared documents.** The brief says shared material is ingested separately. Role sections here contain general knowledge only where framed for that role.

## 9. Validation performed on the final files

| Check | Result |
|---|---|
| Four role sections present | Yes |
| Eight markers, exact text, one occurrence each, correct order | Yes (PDF and Markdown) |
| Other roles' markers inside a role section | None |
| PDF text extractable (`pdftotext`) | Yes; 31 pages |
| TOC page numbers match the PDF | 78 of 78 entries match |
| Secrets, keys, JWTs in PDF or Markdown | None found (pattern scan) |
| Super Admin section free of other roles' operational procedures | Keyword check passed; the section was also written to governance scope |
| Content reviewed by a subject-matter expert | **No** |
| Cross-check against the two named source PDFs | **Not possible** (not received) |
