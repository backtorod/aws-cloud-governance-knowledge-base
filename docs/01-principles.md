# Design principles

## 1. Govern early

Prefer controls in this order when practical:

1. organization and account provisioning;
2. infrastructure authoring and pull request;
3. deployment admission;
4. continuous configuration assessment;
5. runtime detection and response;
6. retrospective audit.

Earlier controls reduce invalid states; later controls remain necessary for drift and threats.

## 2. Separate control intent from implementation

A control objective should survive implementation changes. “Central security telemetry must be retained” is an objective. An Organizations policy, Control Tower control, Config rule, Security Hub control, GitHub workflow, or manual review is an implementation.

## 3. Defense in depth without duplicate noise

Multiple mechanisms are justified when they address different failure modes. Record which layer is authoritative and deduplicate equivalent findings before creating work.

## 4. Evidence is not a screenshot

Evidence should be attributable, time-bound, reproducible where possible, and connected to the exact control implementation and execution. Prefer API responses, signed workflow attestations, immutable logs, configuration snapshots, and content hashes.

## 5. Exceptions are governed objects

Each exception requires scope, rationale, risk owner, approver, compensating controls, start time, expiration, review cadence, and closure evidence.

## 6. Framework mappings are many-to-many

One technical control may support multiple obligations, and an obligation may require multiple technical and procedural controls. Store mapping rationale and confidence; never reduce this to an unsupported one-to-one checkbox.

## 7. Customer control and portability

EvidenceMark must support SaaS and customer-managed operation. Customers should be able to retain evidence in their own account or repository, export it, verify hashes independently, and replace integrations without losing the governance record.

## 8. Source freshness

Cloud services and frameworks change. Store retrieval timestamps and immutable revisions. Flag sources for review rather than silently assuming old guidance remains current.
