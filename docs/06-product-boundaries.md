# EvidenceMark product boundaries

## Canonical position

**Security tools find problems. EvidenceMark proves governance happened.**

EvidenceMark is not a replacement for AWS Security Hub, AWS Config, Control Tower, Audit Manager, Prowler, Checkov, or CNAPP products. Those systems provide enforcement, assessment, detection, aggregation, or operational workflows. EvidenceMark connects their outputs to requirements, policies, controls, implementation revisions, executions, evidence, approvals, findings, and exceptions.

## Comparison

| Product category | Primary question | EvidenceMark relationship |
|---|---|---|
| AWS Security Hub / CNAPP | What risks or exposures exist now? | Ingest findings and posture results as evidence and observations |
| AWS Config | Does deployed configuration match a rule? | Record assessment scope, rule revision, execution, and result |
| AWS Control Tower | How are AWS accounts provisioned and governed? | Capture control selection, scope, provisioning execution, drift, and exceptions |
| AWS Audit Manager | How can AWS evidence support an assessment? | Integrate or complement assessment evidence while adding cross-system lineage |
| Prowler | What do automated security checks observe? | Ingest versioned results and mappings without claiming certification |
| Checkov / policy-as-code | Is proposed infrastructure permitted? | Capture policy revision, evaluated artifact, workflow run, decision, and waiver |
| Ticketing/GRC | Who owns work and risk decisions? | Link work items and approvals to technical evidence and control lineage |

## Defensible differentiators

- governance before, during, and after provisioning;
- cross-system evidence lineage;
- customer-defined regulatory and internal-policy mappings;
- Git-based design and approval evidence;
- explicit, expiring exceptions with compensating controls;
- SaaS or customer-managed deployment;
- evidence portability and customer-controlled retention;
- separation of source knowledge from tenant decisions and artifacts.

## Honest non-goals

EvidenceMark should not initially attempt to provide endpoint protection, threat detection, vulnerability scanning, attack-path analysis, a complete GRC suite, or native implementations of every AWS control. Its advantage is trustworthy orchestration and evidence traceability across systems that already perform those functions.
