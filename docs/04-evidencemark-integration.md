# Wiring this knowledge base into EvidenceMark

## Position

This repository is EvidenceMark's **curated knowledge layer**. It contains source metadata, normalized design guidance, schemas, and agent instructions. It must not become the tenant evidence store or a mirror of every upstream repository.

EvidenceMark remains the **governance system of record** connecting:

```text
Knowledge source -> requirement -> policy -> control
                 -> implementation -> execution -> evidence
                 -> finding / decision / exception
```

## Recommended integration

### 1. Register this repository as a knowledge source

Add a connector configuration using `examples/evidencemark-source-config.yaml`. Pin production ingestion to an immutable commit SHA. A branch such as `main` may be watched for updates, but a design decision must record the resolved commit.

### 2. Add a catalog ingestion job

On a pull-request merge or scheduled refresh:

1. read `catalog/sources.yaml`;
2. validate entries against `schemas/knowledge-item.schema.json`;
3. resolve the current upstream revision and license;
4. calculate a content hash;
5. create or update EvidenceMark source records;
6. open a review item when authority, license, availability, or material content changes.

Do not recursively clone all upstream repositories into EvidenceMark by default.

### 3. Expose retrieval to agents

Provide a narrow tool such as:

```text
search_governance_knowledge(query, domains, authority_minimum, as_of)
get_knowledge_item(id, revision)
get_control_guidance(control_mode, lifecycle_phase, aws_services)
```

Return source metadata and short relevant excerpts or summaries. Agents must cite returned source IDs and revisions in proposals.

### 4. Extend EvidenceMark's domain model

Recommended objects:

- `KnowledgeSource`
- `KnowledgeRevision`
- `Requirement`
- `Policy`
- `ControlObjective`
- `ControlImplementation`
- `AssessmentExecution`
- `EvidenceArtifact`
- `Finding`
- `Decision`
- `Exception`
- `MappingAssertion`

Mappings need author, rationale, confidence, review status, and validity dates.

### 5. Connect operational evidence sources

Use adapters for:

- AWS Organizations and Control Tower;
- AWS Config and Security Hub;
- CloudTrail, Security Lake, and logging stores;
- GitHub repositories, pull requests, Actions, and attestations;
- Prowler and Checkov result formats;
- Terraform plan/apply and policy evaluation;
- human approvals and time-bound exceptions.

The knowledge repository explains what should exist. Connectors prove what actually happened.

### 6. Preserve an evidence envelope

Every ingested artifact should carry the fields defined in `schemas/evidence-record.schema.json`: tenant, source, collection method, timestamps, scope, content hash, control links, execution link, retention classification, and integrity metadata.

### 7. Implement precedence and freshness

Use this precedence for AWS factual behavior:

1. live/current AWS documentation;
2. AWS-owned reference repository pinned to a revision;
3. vendor or project maintainer documentation;
4. community reference;
5. internal interpretation.

A newer low-authority source must not silently override an approved policy. It should create a review event.

## GitHub orchestration

A practical workflow:

1. An EvidenceMark design request opens or updates a GitHub issue.
2. An agent retrieves this repository and applicable upstream sources.
3. The agent proposes architecture, controls, mappings, and evidence requirements in a pull request.
4. CI validates schemas, links, mapping rationale, and required metadata.
5. Human reviewers approve material design and risk decisions.
6. Deployment workflows emit signed execution metadata.
7. EvidenceMark ingests the PR, approvals, workflow runs, artifacts, and deployed-state checks.
8. Drift or source updates create findings or review tasks.

## Deployment modes

### Customer-managed

- EvidenceMark runs in the customer's environment.
- Evidence stays in customer-controlled repositories or object storage.
- This public knowledge base is pulled read-only and pinned by revision.

### SaaS

- EvidenceMark assumes narrowly scoped customer roles or receives pushed evidence.
- Tenant data is logically and cryptographically isolated.
- Customers choose storage and retention options.
- The same public knowledge layer is shared, while policies, mappings, exceptions, and evidence remain tenant-specific.

## First implementation milestone

Build a read-only `KnowledgeSource` importer for this repository, schema validation, commit pinning, source search, and provenance display. Then add GitHub Actions evidence ingestion. AWS connectors can follow without coupling the knowledge model to AWS APIs.
