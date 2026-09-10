# Supplier delay monitoring

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-supply-chain-monitoring` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:22e62ec1f145c1aa74f4186434ab180fb29509e6c6c9348335344b0b4e78ced8` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles:
  - `agent_runtime` `1.0.0` — `sha256:2128b67064d02e8e4b5d551bf0e9ecc4223b314064bd63c579ec2b0a6c34131e`
- Resolved environment: `sha256:bcf622b05aa7af228f3251ac5128ba73ba6f1075569a7f5a3871de4fce8d8200`

## Intent

Detect supplier delays early enough to re-plan production.

FIXTURE DATA - not product evidence. Representative contract only.

## Declaration coverage

Of the obligations this contract activates, how many it **addresses**.
This is not completeness, and it is never readiness.

**Band 1 of 3** — some obligations declared.

| Domain | Band | Addressed | Activated |
|---|---|---|---|
| models | 3 | 0 | 0 |
| api_protocol | 3 | 0 | 0 |
| data_context | 2 | 1 | 3 |
| agent_runtime | 3 | 0 | 0 |
| identity_access | 3 | 0 | 0 |
| governance_safety | 3 | 0 | 0 |
| deployment_network | 1 | 0 | 1 |
| observability_economics | 2 | 1 | 3 |

### What remains open

Reported separately from coverage, and deliberately so: full coverage with open gaps is
an ordinary, correct state (`CORE-018`).

- `unknown_applicability` — Rule "AC-CHANGE-001" could not be decided: the contract did not declare the facts it reads.
- `obligation_not_addressed` *(data_context)* — "Access policy declared" (REQ-DATA-ACCESS-POLICY) is not addressed by the specification.
- `obligation_not_addressed` *(data_context)* — "Retention policy and access logging" (REQ-DATA-RETENTION) is not addressed by the specification.
- `obligation_not_addressed` *(observability_economics)* — "Error signal" (REQ-OBS-ERROR-SIGNAL) is not addressed by the specification.
- `obligation_not_addressed` *(observability_economics)* — "Named incident owner" (REQ-OBS-INCIDENT-OWNER) is not addressed by the specification.
- `obligation_not_addressed` *(deployment_network)* — "Rollback strategy" (REQ-OBS-ROLLBACK) is not addressed by the specification.

## Activated obligations

7 obligations follow from the
decisions recorded above. `declaration` says whether the **specification** addresses each
one — never whether an implementation satisfies it.

| Id | Severity | Level | Declaration | From rule |
|---|---|---|---|---|
| `REQ-DATA-ACCESS-POLICY` | critical | MUST | not_addressed | `AC-DATA-001` |
| `REQ-DATA-CLASSIFICATION` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-RETENTION` | warning | SHOULD | not_addressed | `AC-DATA-001` |
| `REQ-OBS-ERROR-SIGNAL` | critical | MUST | not_addressed | `AC-OBS-001` |
| `REQ-OBS-INCIDENT-OWNER` | critical | MUST | not_addressed | `AC-OBS-001` |
| `REQ-OBS-ROLLBACK` | critical | MUST | not_addressed | `AC-OBS-001` |
| `REQ-OBS-TRACING` | critical | MUST | addressed | `AC-OBS-001` |

## Gate definitions

Which obligations guard each gate. **Whether a gate is open or blocked is not stated
here** — that is a judgement about a built system, and it belongs to an assessment.

- **Production readiness** (`production`) — *critical*
  - `REQ-DATA-ACCESS-POLICY`
  - `REQ-DATA-CLASSIFICATION`
  - `REQ-DATA-RETENTION`
  - `REQ-OBS-ERROR-SIGNAL`
  - `REQ-OBS-INCIDENT-OWNER`
  - `REQ-OBS-ROLLBACK`
  - `REQ-OBS-TRACING`

## Open questions

- **blocking** · `Q-APPLIES-AC-CHANGE-001` *(governance_safety)* — Does "Material model, tool or prompt changes invalidate production evidence" apply? The contract has not declared the facts the rule reads, so applicability is unknown.
- **blocking** · `Q-REQ-DATA-ACCESS-POLICY` *(data_context)* — How will the specification address "Access policy declared"?
- `Q-REQ-DATA-RETENTION` *(data_context)* — How will the specification address "Retention policy and access logging"?
- **blocking** · `Q-REQ-OBS-ERROR-SIGNAL` *(observability_economics)* — How will the specification address "Error signal"?
- **blocking** · `Q-REQ-OBS-INCIDENT-OWNER` *(observability_economics)* — How will the specification address "Named incident owner"?
- **blocking** · `Q-REQ-OBS-ROLLBACK` *(deployment_network)* — How will the specification address "Rollback strategy"?

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:eeea98659a70822e83f4e1bd7d2f3d56955c673ea46fd395795507fcf2cb37d7`.
