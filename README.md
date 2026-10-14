# AWS Cloud Governance Knowledge Base

An agent-ready, source-conscious knowledge base for designing secure AWS organizations, landing zones, governance controls, policy-as-code, and evidence-centered compliance systems.

This repository is the canonical external reference layer for [EvidenceMark](https://evidencemark.com). It does **not** copy or replace upstream projects. It indexes authoritative and community sources, explains when to use them, and defines how design agents should translate them into traceable decisions and evidence requirements.

## Start here

| Need | Read |
|---|---|
| Design an AWS landing zone or multi-account model | [Reference architectures](docs/02-reference-architectures.md) |
| Select preventive, detective, proactive, or responsive controls | [Governance taxonomy](docs/03-governance-taxonomy.md) |
| Connect this knowledge base to EvidenceMark | [EvidenceMark integration](docs/04-evidencemark-integration.md) |
| Instruct an AI agent how to use this repository | [Agent usage](docs/05-agent-usage.md) and [AGENTS.md](AGENTS.md) |
| Compare EvidenceMark with AWS security products | [Product boundaries](docs/06-product-boundaries.md) |
| Review an architecture before approval | [Design checklist](docs/07-design-checklist.md) |
| Inspect machine-readable source metadata | [Source catalog](catalog/sources.yaml) |

## Core principles

1. Prefer current AWS documentation and AWS-owned reference implementations for AWS behavior.
2. Treat community repositories as implementation accelerators, not normative authority.
3. Distinguish requirements, controls, implementations, executions, findings, evidence, decisions, and exceptions.
4. Design controls at the earliest practical lifecycle point.
5. Preserve provenance: source URL, revision, retrieval time, applicable scope, and license.
6. Never present framework alignment as certification.
7. Require human approval for material risk acceptance and exceptions.
8. Keep EvidenceMark complementary to enforcement and detection tools.

## Evidence-centered governance

Security tools answer: **What is misconfigured or risky now?**

EvidenceMark answers: **What requirement applies, what control was selected, where was it enforced, what ran, what evidence was retained, and who approved the outcome or exception?**

Typical trace:

```text
Source requirement
  -> normalized obligation
  -> internal policy
  -> control objective
  -> control implementation
  -> execution or assessment
  -> evidence artifact
  -> finding or attestation
  -> approval / exception
```

## Repository structure

```text
.
├── AGENTS.md
├── catalog/sources.yaml
├── docs/
│   ├── 01-principles.md
│   ├── 02-reference-architectures.md
│   ├── 03-governance-taxonomy.md
│   ├── 04-evidencemark-integration.md
│   ├── 05-agent-usage.md
│   ├── 06-product-boundaries.md
│   └── 07-design-checklist.md
├── examples/evidencemark-source-config.yaml
└── schemas/
    ├── evidence-record.schema.json
    └── knowledge-item.schema.json
```

## Scope

Included: AWS Organizations, Control Tower, landing zones, centralized security services, identity, logging, encryption, network inspection, policy-as-code, compliance mapping, and control-to-evidence traceability.

This repository does not provide legal advice, certify compliance, replace customer risk acceptance, or guarantee that upstream examples are production-ready.

## License and upstream content

Original material in this repository is released under the Apache License 2.0. Every upstream project retains its own license and ownership. Follow links to use upstream content and verify its current license before reuse.

Contributions must preserve source provenance and distinguish fact, interpretation, recommendation, and EvidenceMark-specific guidance.
