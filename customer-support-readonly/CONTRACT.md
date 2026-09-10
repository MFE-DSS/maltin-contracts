# Customer support assistant (read-only)

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-customer-support-readonly` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:bd64715e2291e2d4389e6ae5993fbf2c81811d84f4d8e1778b9da518d456fb02` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles:
  - `agent_runtime` `1.0.0` — `sha256:2128b67064d02e8e4b5d551bf0e9ecc4223b314064bd63c579ec2b0a6c34131e`
- Resolved environment: `sha256:bcf622b05aa7af228f3251ac5128ba73ba6f1075569a7f5a3871de4fce8d8200`

## Intent

Reduce time-to-first-response by answering from the knowledge base and prior case history.

FIXTURE DATA - not product evidence. Representative contract only.

## Declaration coverage

Of the obligations this contract activates, how many it **addresses**.
This is not completeness, and it is never readiness.

**Band 3 of 3** — every activated obligation is addressed.

| Domain | Band | Addressed | Activated |
|---|---|---|---|
| models | 3 | 0 | 0 |
| api_protocol | 3 | 0 | 0 |
| data_context | 3 | 3 | 3 |
| agent_runtime | 3 | 0 | 0 |
| identity_access | 3 | 0 | 0 |
| governance_safety | 3 | 0 | 0 |
| deployment_network | 3 | 0 | 0 |
| observability_economics | 3 | 0 | 0 |

### What remains open

Reported separately from coverage, and deliberately so: full coverage with open gaps is
an ordinary, correct state (`CORE-018`).

- `unknown_applicability` — Rule "AC-CHANGE-001" could not be decided: the contract did not declare the facts it reads.

## Activated obligations

3 obligations follow from the
decisions recorded above. `declaration` says whether the **specification** addresses each
one — never whether an implementation satisfies it.

| Id | Severity | Level | Declaration | From rule |
|---|---|---|---|---|
| `REQ-DATA-ACCESS-POLICY` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-CLASSIFICATION` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-RETENTION` | warning | SHOULD | addressed | `AC-DATA-001` |

## Gate definitions

Which obligations guard each gate. **Whether a gate is open or blocked is not stated
here** — that is a judgement about a built system, and it belongs to an assessment.

- **Production readiness** (`production`) — *critical*
  - `REQ-DATA-ACCESS-POLICY`
  - `REQ-DATA-CLASSIFICATION`
  - `REQ-DATA-RETENTION`

## Open questions

- **blocking** · `Q-APPLIES-AC-CHANGE-001` *(governance_safety)* — Does "Material model, tool or prompt changes invalidate production evidence" apply? The contract has not declared the facts the rule reads, so applicability is unknown.

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:0cc176e08aa5a33f3497e139563d2a337ed8389a1988e1fcd62ac6da2c635d33`.
