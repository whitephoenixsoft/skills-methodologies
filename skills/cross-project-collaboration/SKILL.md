---
name: cross-project-collaboration
description: Coordinate bounded work across projects, conversations, humans, and independent AI systems when context, visibility, ownership, or authority differs. Use for collaboration setup, outgoing and return handoffs, clarification, exceptions, verification, and reconciliation.
metadata:
  version: "0.1.1"
  status: draft
---

# Cross-Project Collaboration

## 1. Purpose

Govern the lifecycle of collaboration across independent workstreams, projects, conversations, agents, AI systems, and human participants.

Preserve sufficient context, evidence, scope, ownership, authority, and uncertainty so that work can be transferred, executed, returned, reviewed, and reconciled without assuming shared memory or shared access.

**Collaboration transfers work and information. It does not automatically transfer authority, establish truth, or imply acceptance.**

## 2. Scope and Activation

Use this skill when at least one of the following is material:

- Participants do not share full context or artifact access.
- Work crosses project, conversation, organizational, or AI-system boundaries.
- One participant delegates bounded work to another.
- Results must return to a distinct owner for review or integration.
- Ownership, verification, or decision authority could be confused.

Do not impose formal handoffs on ordinary discussion within a shared context. Apply the smallest contract sufficient for the risk and complexity.

This skill governs collaboration, not the subject-matter correctness of the work itself.

## 3. Normative Language

- **MUST**: required for a conforming collaboration when applicable.
- **SHOULD**: recommended unless a documented reason justifies omission.
- **MAY**: optional.

## 4. Core Principles

1. **Bounded context:** Never assume the recipient can see the sender's conversation, files, repositories, tools, or earlier decisions.
2. **Explicit authority:** Identify who can request work, perform it, approve scope changes, and accept authoritative outcomes.
3. **Evidence integrity:** Distinguish reported claims from independently verified findings; preserve references and limitations.
4. **Status integrity:** Keep observations, hypotheses, proposals, tested findings, accepted decisions, and deferred matters distinct.
5. **Bidirectional responsibility:** The initiating handoff and return handoff are both required for delegated work that needs reconciliation.
6. **No silent expansion:** Material changes in scope or authority require approval by the appropriate owner.
7. **Failure transparency:** Blocked work, failed execution, negative experiments, and inconclusive findings are valid reportable outcomes.
8. **Explicit closure:** Work reported as completed is not automatically accepted or reconciled.
9. **Portability:** Contracts MUST be understandable without a particular AI provider or chat history.
10. **Minimal overhead:** Record only the detail needed to recover the collaboration, verify claims, and decide next steps.

## 5. Participants and Responsibilities

### Originator

Defines the objective, requested deliverable, constraints, completion criteria, and intended recipient. Reviews the returned work or routes it to the appropriate reviewer.

### Executor

Evaluates whether the request is actionable, accepts or returns it, works within approved scope, preserves evidence, and issues a return handoff.

### Authority Owner

Holds authority over a relevant project decision, specification, artifact, or scope boundary. The authority owner may differ from the originator and executor.

### Reviewer (optional)

Examines returned evidence, quality, or conformance. A reviewer does not acquire decision authority merely by reviewing.

One participant MAY hold multiple roles. Roles and authority MUST NOT be inferred solely from who authored a message or has access to a tool.

## 6. Collaboration Lifecycle

The lifecycle is logical, not a mandatory software state machine. A lightweight conversation may combine stages, but it MUST preserve their distinctions when relevant.

1. **Establish:** Identify participants, roles, ownership, authority, visibility limits, objective, and boundaries.
2. **Issue:** Send an outgoing handoff with sufficient context and an actionable request.
3. **Validate:** Recipient accepts, asks for clarification, declines, or reports a blocker. Receipt alone is not acceptance.
4. **Execute:** Perform authorized work and record material evidence, assumptions, and deviations.
5. **Handle exceptions:** Clarify, block, revise, or escalate whenever necessary; this is available at any stage.
6. **Return:** Send a return handoff reporting actual outcomes, verification, deviations, and unresolved issues.
7. **Reconcile:** Originator or designated authority reviews the return, accepts it, requests revision, rejects it with reasons, or defers a decision; update the appropriate records and close or explicitly leave open.

A collaboration MUST NOT be marked reconciled solely because the executor reports completion.

## 7. Outgoing Handoff Contract

A formal outgoing handoff MUST include, to the extent applicable:

- **Handoff ID:** Stable identifier unique within the originating collaboration record.
- **Originator and recipient:** Workstream or participant names and roles.
- **Objective:** What question or outcome the recipient is responsible for.
- **Context:** Minimum self-contained background needed to understand the request.
- **Scope and exclusions:** What may and may not be changed or concluded.
- **Authority:** Who may approve consequential decisions or scope changes.
- **Evidence and references:** Artifacts, links, versions, experiment IDs, or supplied excerpts.
- **Visibility limits:** What access is known, unknown, or unavailable.
- **Requested output:** Expected deliverable and return format.
- **Completion criteria:** How the recipient and originator can judge the work.
- **Open questions or assumptions:** Uncertainty that must not be silently resolved.

The sender SHOULD identify the authoritative version of mutable artifacts, such as branch, commit, document version, or timestamp, when relevant.

If a recipient cannot access a reference, the sender SHOULD supply the necessary excerpt or artifact when authorized and feasible. Do not copy secrets or restricted content into a less-trusted destination.

## 8. Receiving and Acceptance Rules

Before execution, the recipient MUST assess:

1. Whether the objective and deliverable are sufficiently clear.
2. Whether the necessary context and evidence are available.
3. Whether the requested work fits the recipient's capability and authority.
4. Whether constraints and completion criteria are internally consistent.
5. Whether any security, confidentiality, or access restrictions prevent the work.

The recipient MUST respond with one of:

- **Accepted:** Actionable within the stated boundaries.
- **Clarification required:** A material ambiguity or missing dependency prevents responsible execution.
- **Blocked:** A required resource, permission, tool, or prerequisite is unavailable.
- **Declined:** The task is inappropriate, outside capability, or cannot be performed under its constraints.

Acceptance does not certify the sender's claims or guarantee successful execution.

The recipient MAY proceed with explicitly labeled noncritical assumptions if they do not materially affect authority, safety, scope, or conclusions. Material ambiguity MUST be returned for clarification.

## 9. Execution and Change Control

During execution, the executor MUST:

- Stay within accepted scope and authority.
- Preserve meaningful evidence and distinguish direct observation from inference.
- Identify material discrepancies with the handoff.
- Avoid silently converting proposals or experimental findings into accepted requirements.
- Report unexpected findings that affect the requested outcome.

A material scope change MUST be proposed to the appropriate owner before affected work proceeds. Unaffected work MAY continue if doing so does not prejudice the decision.

If a new issue belongs to another workstream, the executor MUST identify the proposed owner and return or request an explicit handoff. Do not silently absorb responsibility or assume the proposed owner has accepted it.

## 10. Exception Handling

| Condition | Required response |
| --- | --- |
| Missing context | Request the specific missing information; do not invent it. |
| Inaccessible evidence | Identify the source and access limitation; mark dependent claims unverified. |
| Material ambiguity | State competing interpretations and request clarification. |
| Conflicting requirements | Pause affected work and return the conflict to the authority owner. |
| Scope expansion | Propose the change and await approval before affected execution. |
| Unexpected evidence | Preserve the finding and report its implications without premature promotion. |
| Execution failure | Return the attempted work, failure point, evidence, and possible recovery paths. |
| Negative experiment | Report the observed negative result; do not classify it as execution failure solely for contradicting a hypothesis. |
| Inconclusive result | Report uncertainty, limitations, and what would resolve them. |
| Partial completion | Return completed portions, remaining work, and blockers. |
| Recipient unable to proceed | Decline or block with reasons and any viable alternative. |
| Contradiction with prior work | Preserve both claims, provenance, and verification status; request reconciliation. |
| No response / lost context | Mark pending or stalled; do not infer acceptance or completion. |

Exceptions MAY occur during any lifecycle stage. The exception response MUST indicate whether work continues, pauses, returns for clarification, or ends.

## 11. Return Handoff Contract

A return handoff MUST include:

- **Original handoff ID** and recipient/executor identity.
- **Outcome:** Completed, partially completed, blocked, failed, declined, or inconclusive.
- **Work performed:** Actions, analyses, experiments, or artifacts actually produced.
- **Findings:** Results separated from interpretations and recommendations.
- **Evidence and verification:** Sources, versions, tests, checks, and what could not be verified.
- **Deviations:** Any approved or unapproved divergence from scope or method.
- **Open items:** Remaining questions, risks, dependencies, and blockers.
- **Requested reconciliation:** What the originator or authority owner needs to decide or do next.

For material external research claims, the return handoff MUST provide resolvable source references when available. Include sufficient identifying details (for example, title, author, publication, and DOI or URL) for the originator to locate and assess the source. If a material source is unavailable, inaccessible, or not independently verified, the executor MUST disclose that limitation. This requirement does not mandate citations for every incidental background statement.

A return MAY contain no recommendation when evidence is insufficient.

A report of success MUST state what succeeded and under what conditions; it MUST NOT imply unperformed validation or broader applicability.

## 12. Reconciliation and Closure

The originator or designated reviewer MUST examine the return against the original objective and completion criteria, including material revisions.

**Deliverable reconciliation and authoritative decisions are distinct.** An originator MAY accept and reconcile delegated work within their assigned responsibility without seeking separate approval from the authority owner merely to acknowledge satisfactory completion. Acceptance of a research report, experiment, or implementation deliverable does not approve its recommendations or authorize changes to governed requirements, architecture, policy, or other authoritative artifacts. Consequential project decisions MUST be referred to the designated authority owner unless the originator already holds that authority. If ownership or decision authority is unclear, record the ambiguity and seek clarification before making the consequential change.

The reconciliation result MUST be one of:

- **Accepted:** Returned work meets the agreed criteria; any promotion or authoritative decision remains a separate action.
- **Revision requested:** Specific gaps are returned to the executor with updated criteria or questions.
- **Rejected:** Returned work does not meet criteria; reasons are recorded.
- **Deferred:** A decision or dependency remains unresolved; owner and next condition are recorded.

The collaboration MAY close after acceptance, rejection, or an explicitly recorded decision not to continue. Deferred work remains open or is closed as deferred with its unresolved status preserved.

The reconciler MUST record the disposition of material findings and follow-up ownership. Acceptance of a handoff does not itself promote a finding to authoritative project knowledge.

## 13. Collaboration Record and Continuity

For material collaborations, maintain a compact portable record containing:

- Collaboration ID and purpose.
- Participants, roles, and authority boundaries.
- Handoff IDs and revisions.
- Current status and responsible owner.
- Relevant evidence and artifact versions.
- Exception and clarification history when material.
- Return handoffs and reconciliation outcomes.
- Unresolved issues, assigned owners, and next actions.

Markdown is sufficient. No central database, agent protocol, orchestration service, or automated state tracker is required.

If a conversation or agent is replaced, a successor MUST use the record and supplied artifacts rather than claiming access to missing prior context.

A handoff revision SHOULD retain the original ID with a revision marker, or explicitly link the replacement to the superseded handoff. Do not silently overwrite materially changed instructions.

## 14. Relationship to Other Methodologies

### Knowledge Management and Promotion

This skill governs the transfer and reconciliation of findings. The Knowledge Management and Promotion skill governs whether and how findings become durable or authoritative knowledge. A completed collaboration MUST NOT be treated as automatic knowledge promotion.

### Project Traceability

This skill preserves the identities and references necessary to transfer work. The Project Traceability skill governs the critical path of meaning among purpose, decisions, requirements, implementation, and verification. A handoff link alone does not establish semantic traceability or verification sufficiency.

When the relevant methodology is available, use it for its own concern. If unavailable, preserve the boundary and note that its checks were not performed.

## 15. Portable Templates

### 15.1 Outgoing Handoff

```markdown
# Outgoing Collaboration Handoff

Handoff ID:
Collaboration ID:
From / role:
To / role:
Authority owner:
Status: Issued

## Objective

## Minimum Context

## Scope and Exclusions

## Evidence and Artifact Versions

## Visibility / Access Limitations

## Assumptions and Open Questions

## Requested Deliverable

## Completion Criteria

## Clarification / Escalation Route
```

### 15.2 Recipient Response

```markdown
# Handoff Response

Handoff ID:
Recipient:
Disposition: Accepted | Clarification required | Blocked | Declined

## Understanding of the Request

## Missing Information or Constraints

## Assumptions (if proceeding)

## Requested Clarification or Next Action
```

### 15.3 Return Handoff

```markdown
# Return Collaboration Handoff

Original handoff ID:
Collaboration ID:
From / executor:
To / originator:
Outcome: Completed | Partially completed | Blocked | Failed | Declined | Inconclusive

## Work Performed

## Findings and Interpretations

## Evidence and Verification Status

## Scope Deviations

## Limitations and Unresolved Questions

## Recommended Next Action (optional)

## Decisions / Reconciliation Requested
```

### 15.4 Reconciliation Record

```markdown
# Collaboration Reconciliation

Handoff ID:
Reviewer / authority owner:
Disposition: Accepted | Revision requested | Rejected | Deferred

## Evaluation Against Completion Criteria

## Evidence Limitations

## Findings Disposition

## Follow-up Owners and Actions

## Closure Status
```

## 16. Evaluation Plan and Evidence (v0.1.1)

Exercise this skill with three bounded scenarios:

1. Missing Relationship Detection returns experimental evidence to Relationship Graph Architecture, including a known false positive.
2. CAS Mathematics returns possible structural implications while retaining CAS ownership of domain-specific mathematics.
3. Relationship Graph Architecture delegates implementation to an independent coding agent with explicit scope and return verification.

Evaluate whether each collaboration:

- Can be understood without shared chat history.
- Preserves evidence and uncertainty.
- Prevents unapproved scope or authority transfer.
- Handles clarification and failure without inventing outcomes.
- Produces an actionable return handoff.
- Ends with an explicit reconciliation decision or unresolved owner.

### Evaluation record — MRD-RESEARCH-002-R1 (2026-11-08)

- **Basis:** Executor and originator reports for a bounded independent research handoff, reviewed against draft v0.1.0 at commit `2d210dfdc4291fa0754b683e499d867a255eeec3`.
- **Observed success:** Self-contained handoff; acceptance, research execution, and return kept distinct; scope and authority boundaries preserved; MRD-001 shared-cause false positive retained as reported evidence; MRD-002 explicitly not executed; reconciliation not presumed from executor completion.
- **Coverage:** Partial coverage of scenario 1 only. Research was returned to its originator, not an experiment run delivered directly to Relationship Graph Architecture. Scenarios 2 and 3 remain untested.
- **Observed improvement:** External research references were not sufficiently resolvable for formal follow-up; clarify source identification requirements.
- **Observed ambiguity:** Clarify that an originator can reconcile delegated deliverables within assigned responsibility without acquiring authority to approve consequential project changes.
- **Disposition:** One successful receive/execute/return case, partial evaluation coverage; skill remains **draft**. Do not infer full lifecycle validation or completed evaluation-plan coverage.

Revise the skill from observed failures and unnecessary overhead rather than speculative orchestration requirements.

## 17. Deferred Capabilities

Not required in version 0.1.1:

- Automated agent routing or delegation.
- Global task or dependency registry.
- Centralized state-machine implementation.
- Mandatory formal records for trivial conversations.
- Cross-provider API integration.
- Automated knowledge promotion or authoritative decision-making.

These MAY be considered if real collaboration evidence demonstrates a need.
