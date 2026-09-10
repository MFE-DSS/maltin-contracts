# Churn scoring pipeline

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-ml-pipeline` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:03845b838078da6f44c7c0a6d578ca4b3e5fd59dfef57df356816b1deb3dd565` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles:
  - `agent_runtime` `1.0.0` — `sha256:2128b67064d02e8e4b5d551bf0e9ecc4223b314064bd63c579ec2b0a6c34131e`
  - `data_ml` `1.0.0` — `sha256:b0116f2f325419e8f8336717f4619035d553808d06cb5cd28d943725c6d11de4`
- Resolved environment: `sha256:21ac42ad3ea617487577ab7abda633daa4cf624c0bea8596e0e3a875fa86bda8`

## Intent

Score accounts weekly so retention effort is directed at the accounts most likely to leave.

FIXTURE DATA - not product evidence. Representative contract only.

## Declaration coverage

Of the obligations this contract activates, how many it **addresses**.
This is not completeness, and it is never readiness.

**Band 2 of 3** — most obligations declared.

| Domain | Band | Addressed | Activated |
|---|---|---|---|
| models | 3 | 0 | 0 |
| api_protocol | 3 | 0 | 0 |
| data_context | 3 | 3 | 3 |
| agent_runtime | 3 | 0 | 0 |
| identity_access | 3 | 0 | 0 |
| governance_safety | 2 | 2 | 4 |
| deployment_network | 3 | 1 | 1 |
| observability_economics | 3 | 3 | 3 |

### What remains open

Reported separately from coverage, and deliberately so: full coverage with open gaps is
an ordinary, correct state (`CORE-018`).

- `obligation_not_addressed` *(governance_safety)* — "Re-evaluation after material change" (REQ-CHANGE-REEVAL) is not addressed by the specification.
- `obligation_not_addressed` *(governance_safety)* — "Critical scenarios enumerated" (REQ-EVAL-CRITICAL-SCENARIOS) is not addressed by the specification.

## Activated obligations

11 obligations follow from the
decisions recorded above. `declaration` says whether the **specification** addresses each
one — never whether an implementation satisfies it.

| Id | Severity | Level | Declaration | From rule |
|---|---|---|---|---|
| `REQ-CHANGE-REEVAL` | critical | MUST | not_addressed | `AC-CHANGE-001` |
| `REQ-DATA-ACCESS-POLICY` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-CLASSIFICATION` | critical | MUST | addressed | `AC-DATA-001` |
| `REQ-DATA-RETENTION` | warning | SHOULD | addressed | `AC-DATA-001` |
| `REQ-EVAL-CRITICAL-SCENARIOS` | critical | MUST | not_addressed | `AC-EVAL-001` |
| `REQ-EVAL-DATASET` | critical | MUST | addressed | `AC-EVAL-001` |
| `REQ-EVAL-THRESHOLD` | critical | MUST | addressed | `AC-EVAL-001` |
| `REQ-OBS-ERROR-SIGNAL` | critical | MUST | addressed | `AC-OBS-001` |
| `REQ-OBS-INCIDENT-OWNER` | critical | MUST | addressed | `AC-OBS-001` |
| `REQ-OBS-ROLLBACK` | critical | MUST | addressed | `AC-OBS-001` |
| `REQ-OBS-TRACING` | critical | MUST | addressed | `AC-OBS-001` |

## Gate definitions

Which obligations guard each gate. **Whether a gate is open or blocked is not stated
here** — that is a judgement about a built system, and it belongs to an assessment.

- **Production readiness** (`production`) — *critical*
  - `REQ-CHANGE-REEVAL`
  - `REQ-DATA-ACCESS-POLICY`
  - `REQ-DATA-CLASSIFICATION`
  - `REQ-DATA-RETENTION`
  - `REQ-EVAL-CRITICAL-SCENARIOS`
  - `REQ-EVAL-DATASET`
  - `REQ-EVAL-THRESHOLD`
  - `REQ-OBS-ERROR-SIGNAL`
  - `REQ-OBS-INCIDENT-OWNER`
  - `REQ-OBS-ROLLBACK`
  - `REQ-OBS-TRACING`

## Open questions

- **blocking** · `Q-REQ-CHANGE-REEVAL` *(governance_safety)* — How will the specification address "Re-evaluation after material change"?
- **blocking** · `Q-REQ-EVAL-CRITICAL-SCENARIOS` *(governance_safety)* — How will the specification address "Critical scenarios enumerated"?

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:13bc1bce61380cbc915f23d4e14b8e7438529b83ad23cc33561cd0bb5c94ebf5`.
