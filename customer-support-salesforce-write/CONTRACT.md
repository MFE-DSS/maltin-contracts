# Customer support assistant (Salesforce case update enabled)

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-customer-support-salesforce-write` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:982fa449b61e7b587062ff5f9cdf220a871e70b461518ccbbf208269ab166e2e` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles:
  - `agent_runtime` `1.0.0` — `sha256:2128b67064d02e8e4b5d551bf0e9ecc4223b314064bd63c579ec2b0a6c34131e`
- Resolved environment: `sha256:bcf622b05aa7af228f3251ac5128ba73ba6f1075569a7f5a3871de4fce8d8200`

## Intent

Reduce handling time by letting the assistant update case status and resolution notes directly.

FIXTURE DATA - not product evidence. Representative contract only.

## Declaration coverage

Of the obligations this contract activates, how many it **addresses**.
This is not completeness, and it is never readiness.

**Band 1 of 3** — some obligations declared.

| Domain | Band | Addressed | Activated |
|---|---|---|---|
| models | 3 | 0 | 0 |
| api_protocol | 3 | 0 | 0 |
| data_context | 3 | 3 | 3 |
| agent_runtime | 1 | 0 | 2 |
| identity_access | 1 | 0 | 1 |
| governance_safety | 1 | 0 | 3 |
| deployment_network | 3 | 0 | 0 |
| observability_economics | 3 | 0 | 0 |

### What remains open

Reported separately from coverage, and deliberately so: full coverage with open gaps is
an ordinary, correct state (`CORE-018`).

- `unknown_applicability` — Rule "AC-CHANGE-001" could not be decided: the contract did not declare the facts it reads.
- `obligation_not_addressed` *(agent_runtime)* — "Idempotency key or compensating action" (REQ-SIDEFX-IDEMPOTENCY) is not addressed by the specification.
- `obligation_not_addressed` *(governance_safety)* — "Approval policy or explicit autonomous-action justification" (REQ-TOOL-APPROVAL) is not addressed by the specification.
- `obligation_not_addressed` *(governance_safety)* — "Tool-call audit logging" (REQ-TOOL-AUDIT) is not addressed by the specification.
- `obligation_not_addressed` *(governance_safety)* — "Critical-action evaluation scenarios" (REQ-TOOL-CRITICAL-EVAL) is not addressed by the specification.
- `obligation_not_addressed` *(agent_runtime)* — "Declared failure semantics for side-effecting calls" (REQ-TOOL-FAILURE-SEMANTICS) is not addressed by the specification.
- `obligation_not_addressed` *(identity_access)* — "Explicit write scope on the external credential" (REQ-TOOL-WRITE-SCOPE) is not addressed by the specification.

## Activated obligations

9 obligations follow from the
decisions recorded above. `declaration` says whether the **specification** addresses each
one — never whether an implementation satisfies it.

| Id | Severity | Level | Declaration | From rule |
|---|---|---|---|---|
| `REQ-DATA-ACCESS-POLICY` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-CLASSIFICATION` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-RETENTION` | warning | SHOULD | addressed | `AC-DATA-001` |
| `REQ-SIDEFX-IDEMPOTENCY` | critical | MUST | not_addressed | `AC-SIDEFX-001` |
| `REQ-TOOL-APPROVAL` | critical | MUST | not_addressed | `AC-TOOL-001` |
| `REQ-TOOL-AUDIT` | critical | MUST | not_addressed | `AC-TOOL-001` |
| `REQ-TOOL-CRITICAL-EVAL` | critical | MUST | not_addressed | `AC-TOOL-001` |
| `REQ-TOOL-FAILURE-SEMANTICS` | critical | MUST | not_addressed | `AC-TOOL-001` |
| `REQ-TOOL-WRITE-SCOPE` | critical | MUST | not_addressed | `AC-TOOL-001` |

## Gate definitions

Which obligations guard each gate. **Whether a gate is open or blocked is not stated
here** — that is a judgement about a built system, and it belongs to an assessment.

- **Production readiness** (`production`) — *critical*
  - `REQ-DATA-ACCESS-POLICY`
  - `REQ-DATA-CLASSIFICATION`
  - `REQ-DATA-RETENTION`
  - `REQ-SIDEFX-IDEMPOTENCY`
  - `REQ-TOOL-APPROVAL`
  - `REQ-TOOL-AUDIT`
  - `REQ-TOOL-CRITICAL-EVAL`
  - `REQ-TOOL-FAILURE-SEMANTICS`
  - `REQ-TOOL-WRITE-SCOPE`

## Open questions

- **blocking** · `Q-APPLIES-AC-CHANGE-001` *(governance_safety)* — Does "Material model, tool or prompt changes invalidate production evidence" apply? The contract has not declared the facts the rule reads, so applicability is unknown.
- **blocking** · `Q-REQ-SIDEFX-IDEMPOTENCY` *(agent_runtime)* — How will the specification address "Idempotency key or compensating action"?
- **blocking** · `Q-REQ-TOOL-APPROVAL` *(governance_safety)* — How will the specification address "Approval policy or explicit autonomous-action justification"?
- **blocking** · `Q-REQ-TOOL-AUDIT` *(governance_safety)* — How will the specification address "Tool-call audit logging"?
- **blocking** · `Q-REQ-TOOL-CRITICAL-EVAL` *(governance_safety)* — How will the specification address "Critical-action evaluation scenarios"?
- **blocking** · `Q-REQ-TOOL-FAILURE-SEMANTICS` *(agent_runtime)* — How will the specification address "Declared failure semantics for side-effecting calls"?
- **blocking** · `Q-REQ-TOOL-WRITE-SCOPE` *(identity_access)* — How will the specification address "Explicit write scope on the external credential"?

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:064e8de4ea32f3d973efe81aa1df37c177b23a69654f0e1a08a6368b8ceb3b35`.
