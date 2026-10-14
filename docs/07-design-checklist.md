# AWS governance design checklist

## Scope and ownership

- [ ] Business objective, workloads, data classes, accounts, OUs, Regions, and partitions are defined.
- [ ] Platform, security, network, identity, application, risk, and audit owners are named.
- [ ] Shared-responsibility and tenant boundaries are explicit.

## Organization and accounts

- [ ] Management account usage is minimized.
- [ ] Security tooling, log archive, identity, network, shared services, and workload account patterns are decided.
- [ ] Delegated administrators and trusted access are documented.
- [ ] Account vending, enrollment, update, suspension, and closure paths are governed.

## Identity

- [ ] Workforce federation, workload identities, emergency access, and root-user controls are defined.
- [ ] Least privilege, permission boundaries, session duration, and credential lifecycle are addressed.
- [ ] Identity events produce retained evidence.

## Logging, detection, and evidence

- [ ] Organization-wide CloudTrail and configuration recording scope are explicit.
- [ ] Central ownership, immutable retention, encryption, access, and deletion protections are defined.
- [ ] Security services cover intended accounts and Regions.
- [ ] Evidence provenance, hashes, timestamps, retention, and export are specified.

## Network and data protection

- [ ] North-South, East-West, egress, DNS, hybrid, and inspection patterns are defined.
- [ ] Key ownership, delegation, rotation, recovery, and deletion controls are documented.
- [ ] Data classification drives encryption, residency, retention, and access.

## Delivery governance

- [ ] Infrastructure changes use version control and review.
- [ ] Policy checks run before deployment.
- [ ] Artifacts, dependencies, actions, and runners have integrity controls.
- [ ] Deployment identity, approvals, execution, and rollback evidence are retained.

## Operations

- [ ] Drift, findings, incident routing, suppression, remediation, and closure are governed.
- [ ] Exceptions have owners, rationale, compensating controls, expiry, and review.
- [ ] Regional and service failures have tested resilience and recovery paths.
- [ ] Cost and service quotas are considered.

## Assurance

- [ ] Every control has an objective, owner, mode, scope, implementation, evidence specification, and test.
- [ ] Framework mappings include rationale and review status.
- [ ] Unsupported claims and residual risks are visible.
- [ ] Human approval gates exist for material decisions and risk acceptance.
