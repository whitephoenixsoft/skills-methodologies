---
name: project-traceability
description: Establish and maintain a critical path of meaning across project purpose, decisions, requirements, architecture, implementation, and verification. Use for project establishment, traceability reviews, impact analysis, and semantic consistency checks.
metadata:
  version: "0.2.0"
  status: draft
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
7. Identify missing or conflicting relationships.
8. Assess consequences of identified gaps.
9. Recommend the smallest useful correction.

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

## 7. Validation Criteria

Evaluate:

**Identity:** Can semantic commitments be recognized across transformations?

**Justification:** Can important elements be traced to meaningful origins?

**Consistency:** Do related artifacts preserve compatible meaning?

**Coverage:** Is there appropriate evidence for important commitments?

**Change impact:** Can consequential dependencies be identified?

**Authority:** Can accepted knowledge be distinguished from provisional material?

**Uncertainty:** Are unresolved relationships visible?

**Proportionality:** Is the traceability effort justified by its value?

## 8. Project Adaptation

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

## 9. Integration with Knowledge Management

This skill operates under the Knowledge Management and Promotion skill.

Traceability identifies and validates relationships.

Knowledge management governs consolidation, acceptance, promotion, portability, and version-controlled authority.

Do not automatically promote traceability findings into authoritative project knowledge.

## 10. Output Requirements

For traceability reviews, report:

- Scope and authoritative sources
- Relevant critical path of meaning
- Confirmed relationships
- Missing or conflicting relationships
- Uncertainty
- Consequential change impacts
- Recommended corrections

For skill revisions, produce the complete updated Markdown source and a separate change summary.

## 11. Boundaries

This skill does not:

- Require projects to begin with formal requirements.
- Require all exploration to be permanently documented.
- Require every code element to have a semantic identifier.
- Impose a universal document hierarchy.
- Replace project-specific validation rules.
- Invent historical intent.
- Make authoritative decisions on behalf of the user.
- Treat documentation quantity as a measure of quality.

## 12. Success Criteria

Traceability succeeds when:

1. The project's current meaning is recoverable.
2. Important semantic commitments retain their identity.
3. Implementation and verification can be connected to their justification.
4. Changes can be evaluated for semantic impact.
5. Important uncertainty remains visible.
6. Historical evolution is not mistaken for original intent.
7. Documentation remains proportional to project needs.
8. Project knowledge remains portable and reviewable.