# Instructions for AI agents

## Mission

Use this repository to design AWS cloud governance and EvidenceMark capabilities that are secure, traceable, evidence-centered, and explicit about uncertainty.

## Required reading order

1. `README.md`
2. `catalog/sources.yaml`
3. `docs/01-principles.md`
4. The task-specific documents under `docs/`
5. The current upstream source before making claims that may have changed

## Source hierarchy

1. Current AWS service documentation, APIs, and formal AWS guidance
2. AWS-owned reference architectures and implementation repositories
3. Maintainer documentation for an open-source project
4. Community-curated resources
5. This repository's interpretations and recommendations

Higher-ranked sources override lower-ranked sources for factual product behavior. This repository remains authoritative for EvidenceMark's internal vocabulary and integration contract.

## Mandatory behavior

- Cite the source URL and, when possible, commit SHA, release, tag, or retrieval date.
- Label statements as `fact`, `inference`, `recommendation`, or `decision`.
- Never claim that a mapping proves compliance or certification.
- Never silently turn an example into a production standard.
- Identify the AWS partition, Regions, organization scope, OU scope, accounts, and lifecycle phase.
- Separate preventive, proactive, detective, responsive, and evidentiary mechanisms.
- State prerequisites, operational owner, expected evidence, failure behavior, and rollback path.
- Prefer least privilege and customer-controlled storage.
- Require human approval for exceptions, risk acceptance, destructive actions, and material architecture decisions.
- If sources conflict or are stale, say so and request verification.

## Expected design output

Every material recommendation should contain:

- objective and scope;
- source-backed rationale;
- assumptions and constraints;
- proposed control type and enforcement point;
- implementation mechanism;
- evidence to collect;
- ownership and approval;
- exception and expiration behavior;
- validation and rollback;
- unresolved questions.

## EvidenceMark boundary

Do not position EvidenceMark as a replacement for AWS Security Hub, AWS Config, Control Tower, Audit Manager, Prowler, Checkov, or a CNAPP. Treat those products as enforcement, assessment, detection, or evidence sources. EvidenceMark connects requirements, controls, executions, artifacts, approvals, findings, and exceptions.

## Retrieval safety

Do not recursively ingest entire repositories by default. Retrieve the smallest relevant path, capture provenance, respect licenses, and refresh volatile material before using it for a decision.
