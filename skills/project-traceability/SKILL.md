---
name: project-traceability
description: Establish and maintain a critical path of meaning across project purpose, decisions, requirements, architecture, implementation, and verification. Use for project establishment, traceability reviews, impact analysis, and semantic consistency checks.
metadata:
  version: "0.3.1"
  status: stable
---

# Project Traceability

## 1. Purpose

Preserve semantic identity, intent, justification, and verification as projects emerge, evolve, and undergo transformation.

Traceability is not merely a collection of document references. It is the ability to recover why something exists, what it means, what it fulfills, and how that meaning is preserved or changed.

The central objective is to establish and maintain a **critical path of meaning**.

## 2. Core Principles

### 2.1 Projects May Emerge from Exploration

Projects do not require a predefined purpose before exploration begins.

A project may emerge from:

- A learning exercise
- An observation
- An engineering problem
- A research question
- An experiment
- An architectural concept
- An existing implementation

Do not fabricate an original project purpose retrospectively.

Preserve the distinction between original motivation and subsequently established purpose.

### 2.2 Establish a Critical Path of Meaning

When an activity becomes a recognized project, identify the minimum semantic structure needed to explain its identity and direction.

Determine:

- What is this project?
- Why does it exist now?
- What problem, opportunity, or objective does it address?
- What commitments define its identity?
- What must remain true as it evolves?
- What evidence supports these commitments?

The critical path is a connected chain or network of meaning, not necessarily a chronological sequence or a single linear hierarchy.

It may be reconstructed from existing artifacts, decisions, or implementation.

Do not require every possible relationship to be documented.

### 2.3 Work Bidirectionally

Traceability may proceed:

- Forward from purpose toward implementation and verification.
- Backward from implementation or evidence toward justification.
- Laterally between related decisions, constraints, and artifacts.

Do not assume that upstream knowledge was created before downstream artifacts.

When reconstructing history, distinguish documented origins from present-day interpretations.

### 2.4 Preserve Semantic Identity

Elements representing independent semantic commitments require stable identifiers.

Examples include:

- Objectives
- Requirements
- Decisions
- Invariants
- Architectural constraints
- Accepted behavioral contracts

Identifiers should remain stable when representation changes but meaning is preserved.

When meaning changes substantially, evaluate whether a new semantic identity is required.

Preserve supersession and derivation relationships where relevant.

### 2.5 Reuse Implementation Identity

Code does not automatically require separate semantic identifiers.

Use existing locators where sufficient:

- Repository paths
- File names
- Module names
- Types
- Functions and methods
- Test names
- Commit references

These identify concrete artifacts rather than independently authoritative semantic commitments.

When a locator changes, update the reference without unnecessarily changing the semantic identity.

### 2.6 Trace Meaning, Not Just References

Relationships must communicate their significance.

Useful relationship types include:

- derives-from
- refines
- implements
- verifies
- constrains
- depends-on
- supersedes
- contradicts

Distinguish semantic relationships from simple navigational links.

### 2.7 Preserve Uncertainty

Classify relationships as:

- Confirmed
- Inferred
- Proposed
- Unresolved

Do not manufacture missing relationships.

A missing relationship may indicate incomplete documentation, incomplete understanding, or a genuine design gap.

### 2.8 Maintain Proportionality

Traceability exists to improve understanding and support change.

Avoid duplicating authoritative information.

Do not impose a large documentation structure on a small project without demonstrated value.

Prefer the smallest useful set of relationships.

## 3. Project Establishment Procedure

When exploration becomes a project:

1. Identify the current motivation.
2. Preserve relevant historical origins.
3. Identify existing semantic commitments.
4. Identify the most important constraints and invariants.
5. Examine existing artifacts and evidence.
6. Construct the initial critical path of meaning.
7. Identify important unresolved relationships.
8. Propose an initial authoritative project definition.

Project establishment does not automatically promote exploratory material into accepted knowledge.

Acceptance follows the Knowledge Management and Promotion process.

## 4. Traceability Model

Represent project knowledge as semantic elements connected to other semantic elements and concrete artifacts.

### Semantic Elements

Represent independently meaningful project commitments.

Each should have:

- Stable identifier
- Meaning or statement
- Status
- Authoritative source
- Relevant relationships

Include rationale and evidence when needed to understand or validate the commitment.

### Concrete Artifacts

Represent implementations, documents, tests, benchmarks, and operational evidence.

Use existing artifact identifiers wherever practical.

### Relationships

Represent the meaning of connections between elements.

Relationships should be sufficiently explicit to support forward tracing, backward tracing, and impact analysis.

Avoid treating all links as equivalent.

## 5. Traceability Review Procedure

When reviewing project work:

1. Identify the scope of review.
2. Retrieve current authoritative knowledge.
3. Locate relevant semantic elements.
4. Identify connected implementation and evidence.
5. Trace relationships in both directions.
6. Evaluate semantic consistency.
7. Discover existing execution records for relevant executable verification, including CI runs and check results.
8. Identify missing or conflicting relationships.
9. Assess consequences of identified gaps.
10. Recommend the smallest useful correction.

Do not assume that incomplete traceability means the implementation is incorrect.

## 6. Change Impact Analysis

When a semantic element or concrete artifact changes:

1. Identify what changed.
2. Classify the change as semantic, structural, representational, or evidential.
3. Identify affected relationships.
4. Determine whether established meaning remains valid.
5. Identify verification that may require review.
6. Determine whether existing semantic identities remain appropriate.
7. Preserve relevant historical relationships.
8. Report uncertainty and unresolved consequences.

Avoid automatically invalidating every connected artifact.

## 7. Reproducible Evidence Protocol

### 7.1 Baseline Identity

Before evaluating traceability, record the repository URL, branch or ref, resolved commit SHA, exact methodology version, and the methodology source (path plus commit SHA or content hash where available). A branch name alone is not a reproducible baseline. If the exact skill source is unavailable, mark the review as provisional and do not claim full methodology conformance.

### 7.2 Artifact Inventory

Establish the population of artifacts relevant to the declared scope before making a coverage judgment. Record the exact paths inspected, their role and revision, relevant exclusions, and discovery method. Distinguish a complete scoped inventory from selected or sampled artifacts. Record additions and omissions discovered during the review. A partial inventory supports local findings but not repository-wide coverage claims.

### 7.3 Verification Levels

Use the following cumulative evidence levels, reporting the highest level actually established for each finding:

- **L0 — Reported:** Claim or locator supplied, not independently inspected.
- **L1 — Located:** Source reference or evidence locator found in an inspected artifact.
- **L2 — Resolved:** Referenced target exists at the pinned revision; locator is accurate.
- **L3 — Semantically examined:** Target contents, assertions, and relationship to the claimed contract inspected; scope and limitations recorded.
- **L4 — Executed:** Relevant verification executed against the pinned revision, with command, environment where material, result, and output reference recorded.

These levels describe verification depth, not proof strength. An executed test can still be insufficient to prove an invariant. Non-executable artifacts can be fully assessed at L3; do not require L4 where execution is inapplicable. When a level is not applicable, say why. Do not imply that merely running a test establishes complete coverage.

### 7.3.1 Execution Evidence Discovery

When a finding or coverage claim depends on executable verification, actively search for existing execution evidence **before** concluding that L4 is unavailable. Inspect applicable CI workflow runs, check suites and check runs, job and step conclusions, logs, retained artifacts, and other recorded local or remote verification results. Do not stop at the workflow definition, a pull-request-only run search, or combined commit statuses: these do not exhaust GitHub Actions execution evidence.

Match each execution record to the pinned commit SHA, or document and justify an equivalent revision and its limitations. For each relevant result record the command or check, revision, environment where material, outcome, evidence locator, and the scope of verification actually exercised. Distinguish workflow configuration, a triggered run, a completed job, and successful relevant steps. A successful workflow does not establish that every test or invariant was exercised.

If no execution evidence is obtained, record the discovery surfaces queried and their limitations. Distinguish **not executed (affirmatively established)**, **executed but failed**, **execution evidence inaccessible**, **no matching record found in searched sources**, and **discovery incomplete**. Absence from one search is not proof that execution never occurred. Do not demand new execution when suitable existing evidence is available; do not claim L4 without a verified execution record.

L4 applies only to claims for which execution is relevant. Documentation-only defects and other non-executable semantic findings may be conclusively assessed at L3.

### 7.4 Finding Evidence Record

Each finding must include: finding ID; claim and classification; source path and precise locator (line range, symbol, test name, or equivalent); target locator if applicable; baseline commit SHA; skill version and source identity; inspected artifact subset; verification level; evidence supporting the claim; contrary evidence or limitations; and the smallest justified action. A shared report header may carry common baseline fields if each finding unambiguously inherits them.

Distinguish **primary evidence** that directly supports a claim from **supporting evidence** that corroborates only part of it. Explicitly label inferred relationships. Record exact commands and results for execution claims. If a claim cannot be independently verified, mark it unresolved rather than confirmed.

### 7.5 Coverage Judgment Gate

Before stating coverage completeness, complete applicable execution evidence discovery under Section 7.3.1 and define the denominator: the authoritative set of in-scope semantic obligations, with active/planned/retired lifecycle distinctions. Establish the corresponding in-scope artifact inventory and examine evidence adequacy at the level required by the claim. Reconcile both forward and reverse relationships. State exclusions and unknowns.

If these prerequisites are incomplete, report **coverage not established** or **coverage partially evaluated**, and restrict conclusions to the inspected subset. Never turn absence from a sample into a claim that implementation or verification is missing. Missing traceability, broken locators, and absent implementation or verification remain distinct categories.

## 8. Validation Criteria

Evaluate:

**Identity:** Can semantic commitments be recognized across transformations?

**Justification:** Can important elements be traced to meaningful origins?

**Consistency:** Do related artifacts preserve compatible meaning?

**Coverage:** Is there appropriate evidence for important commitments?

**Change impact:** Can consequential dependencies be identified?

**Authority:** Can accepted knowledge be distinguished from provisional material?

**Uncertainty:** Are unresolved relationships visible?

**Proportionality:** Is the traceability effort justified by its value?

## 9. Project Adaptation

### Small Libraries

Connect project identity, invariants, public contracts, implementations, tests, and benchmarks.

### Compilers and Process Engines

Preserve semantic commitments through parsing, analysis, normalization, lowering, and runtime execution.

Distinguish source-level meaning from implementation representation.

### Legacy Systems

Reconstruct traceability incrementally using existing documentation, code, operational evidence, and stakeholder knowledge.

Avoid fabricating undocumented design intent.

### Decision Systems

Preserve relationships among observations, proposals, decisions, authority, scope, implementation, and review.

Do not confuse an observation with an accepted decision.

## 10. Integration with Knowledge Management

This skill operates under the Knowledge Management and Promotion skill.

Traceability identifies and validates relationships.

Knowledge management governs consolidation, acceptance, promotion, portability, and version-controlled authority.

Do not automatically promote traceability findings into authoritative project knowledge.

## 11. Output Requirements

For traceability reviews, report:

- Reproducible baseline (commit SHA and exact skill source/version)
- Exact scoped artifact inventory and exclusions
- Verification level and provenance for every finding
- Execution evidence discovery sources, matched runs/checks, outcomes, and access limitations where applicable
- Coverage denominator, evidence adequacy, and judgment eligibility

- Scope and authoritative sources
- Relevant critical path of meaning
- Confirmed relationships
- Missing or conflicting relationships
- Uncertainty
- Consequential change impacts
- Recommended corrections

For skill revisions, produce the complete updated Markdown source and a separate change summary.

## 12. Boundaries

This skill does not:

- Require projects to begin with formal requirements.
- Require all exploration to be permanently documented.
- Require every code element to have a semantic identifier.
- Impose a universal document hierarchy.
- Replace project-specific validation rules.
- Invent historical intent.
- Make authoritative decisions on behalf of the user.
- Treat documentation quantity as a measure of quality.

## 13. Success Criteria

Traceability succeeds when:

1. The project's current meaning is recoverable.
2. Important semantic commitments retain their identity.
3. Implementation and verification can be connected to their justification.
4. Changes can be evaluated for semantic impact.
5. Important uncertainty remains visible.
6. Historical evolution is not mistaken for original intent.
7. Documentation remains proportional to project needs.
8. Project knowledge remains portable and reviewable.
9. Every coverage judgment is reproducible from a pinned baseline and recorded evidence.