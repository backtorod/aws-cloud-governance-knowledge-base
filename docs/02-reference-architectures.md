# Reference architectures and source guide

## AWS Security Reference Architecture examples

**Repository:** https://github.com/aws-samples/aws-security-reference-architecture-examples  
**Use for:** multi-account security-service delegation, organization-wide enablement, security tooling accounts, log archive patterns, StackSets, and Terraform examples.  
**Authority:** AWS-owned reference implementation; validate against current service documentation.  
**EvidenceMark use:** derive candidate controls and expected deployment evidence, but preserve upstream revision and local customization.

## AWS Security Services Best Practices

**Repository:** https://github.com/aws/aws-security-services-best-practices  
**Use for:** prescriptive service architecture, inspection patterns, centralized detection, network boundaries, and operational considerations.  
**Authority:** AWS-owned guidance repository.  
**EvidenceMark use:** design rationale and control implementation options.

## AWS Control Tower controls with Terraform

**Repository:** https://github.com/aws-samples/aws-control-tower-controls-terraform  
**Use for:** programmatic Control Tower control enablement and Terraform-oriented governance workflows.  
**Authority:** AWS sample.  
**EvidenceMark use:** capture plan, approval, apply result, enabled-control state, OU/account scope, and subsequent drift assessment.

## Landing Zone Accelerator on AWS

**Repository:** https://github.com/awslabs/landing-zone-accelerator-on-aws  
**Use for:** regulated multi-account foundations, declarative configuration, centralized logging, networking, encryption, security services, and GitOps delivery.  
**Authority:** AWS Labs implementation; confirm supported versions and deployment prerequisites.  
**EvidenceMark use:** treat configuration revisions and pipeline executions as strong implementation evidence.

## Prowler

**Repository:** https://github.com/prowler-cloud/prowler  
**Use for:** security checks, framework mappings, and assessment output across supported providers.  
**Authority:** community/open-source project; mappings must be verified against the relevant framework.  
**EvidenceMark use:** ingest results as assessment evidence and findings, not as certification.

## Checkov

**Repository:** https://github.com/bridgecrewio/checkov  
**Use for:** infrastructure-as-code policies and pre-deployment checks across Terraform, CloudFormation, Kubernetes, and related formats.  
**Authority:** community/vendor-maintained policy engine.  
**EvidenceMark use:** link policy version, repository commit, workflow run, evaluated artifact, result, and waiver.

## Terraform foundational policies library

**Repository:** https://github.com/hashicorp/terraform-foundational-policies-library  
**Use for:** Sentinel and policy patterns for Terraform workflows.  
**Authority:** vendor-maintained examples; validate compatibility and license.  
**EvidenceMark use:** policy-as-code source with execution evidence from the delivery platform.

## Awesome AWS

**Repository:** https://github.com/donnemartin/awesome-aws  
**Use for:** discovery only.  
**Authority:** community curation.  
**EvidenceMark use:** candidate-source discovery; never use a list entry alone as the basis of a control.

## Awesome Architecture Governance

**Repository:** https://github.com/archguard/awesome-architecture-governance  
**Use for:** discovery of fitness functions, architecture governance, and continuous verification approaches.  
**Authority:** community curation.  
**EvidenceMark use:** pattern discovery and vocabulary enrichment.

## Selection rule

Use AWS-owned sources to establish AWS behavior, open-source engines to implement or assess controls, and community collections to discover candidates. Always validate the exact upstream path and revision used.
