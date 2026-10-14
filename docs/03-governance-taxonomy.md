# Governance taxonomy

## Core entities

| Entity | Meaning |
|---|---|
| Source | Authoritative or informative upstream material |
| Requirement | External or internal obligation expressed without implementation assumptions |
| Policy | Organization-approved interpretation of one or more requirements |
| Control objective | Desired outcome that reduces a defined risk |
| Control implementation | Concrete mechanism implementing an objective |
| Assessment | Evaluation of a target against a control |
| Execution | A particular run of automation or review |
| Evidence artifact | Retained object supporting a claim |
| Finding | Observed deviation, weakness, or risk |
| Decision | Approved selection, acceptance, rejection, or disposition |
| Exception | Time-bound authorized deviation |
| Mapping | Explained relationship between entities |

## Control modes

- **Preventive:** blocks an action or configuration, such as SCPs and RCPs.
- **Proactive:** evaluates a proposed resource before provisioning, such as CloudFormation hooks or pipeline policy checks.
- **Detective:** evaluates deployed state, such as AWS Config, Security Hub CSPM, or Prowler.
- **Responsive:** changes state or initiates remediation after detection.
- **Evidentiary:** captures and preserves proof of design, execution, approval, or state.
- **Procedural:** relies on an accountable human or organizational process.

A mature control may combine modes. Record each mechanism independently.

## Lifecycle phases

1. strategy and regulatory interpretation;
2. platform and landing-zone design;
3. account or subscription provisioning;
4. workload design;
5. infrastructure authoring;
6. deployment;
7. continuous operation;
8. incident and remediation;
9. audit and assurance;
10. decommissioning.

## Minimal control record

- stable control ID;
- title and objective;
- risks addressed;
- requirement mappings with rationale;
- owner and operator;
- enforcement mode and lifecycle phase;
- target scope;
- implementation references;
- evidence specification;
- assessment frequency;
- failure severity and response;
- exception policy;
- version and effective date.

## Evidence quality dimensions

Evidence should be scored or described for provenance, integrity, freshness, completeness, scope match, reproducibility, and independence. A high quantity of weak evidence must not be represented as strong assurance.
