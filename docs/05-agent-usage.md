# Agent usage guide

## Recommended context attachment

Point an agent first to `AGENTS.md`, then provide only the task-relevant files. For a landing-zone task, attach the source catalog, principles, reference architectures, taxonomy, and design checklist. For EvidenceMark implementation, also attach the integration document and schemas.

## Standard prompt

```text
Use backtorod/aws-cloud-governance-knowledge-base as the governance reference.
Follow AGENTS.md. Verify volatile AWS behavior against current official AWS
documentation. Produce a design with assumptions, control modes, enforcement
points, evidence requirements, exceptions, validation, rollback, and citations.
Do not claim compliance or certification.
```

## Expected citations

Citations should identify:

- knowledge item ID;
- upstream URL;
- immutable revision or version when available;
- retrieval date;
- whether the claim is fact, inference, recommendation, or decision.

## Task patterns

### Architecture design

Ask the agent to identify account/OU topology, trust boundaries, delegated administrators, log ownership, encryption ownership, network inspection points, break-glass access, regional strategy, resilience, evidence, and rollback.

### Control design

Ask for the objective first, then preventive/proactive/detective/responsive implementations, coverage gaps, evidence, exception behavior, and operational ownership.

### Product design

Ask how EvidenceMark connects existing tools rather than reproducing them. Require clear boundaries with Security Hub, Config, Control Tower, Audit Manager, Prowler, Checkov, and CNAPP platforms.

### Review

Ask the agent to list unsupported claims, stale references, missing provenance, control-mode confusion, evidence gaps, dangerous automation, and decisions requiring human approval.

## Anti-patterns

- ingesting an entire upstream repository into every prompt;
- treating an “awesome” list as authoritative;
- citing a default branch without recording the resolved commit;
- assuming a check mapping equals compliance;
- collapsing findings and evidence into one object;
- allowing agents to approve their own risk exceptions;
- proposing remediation without blast-radius and rollback analysis.
