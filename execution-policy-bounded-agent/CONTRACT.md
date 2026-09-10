# Migrate the reporting exporter to the new storage client

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-execution-policy-bounded-agent` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:7ef625f7e2a2ffe024c5219bb405c8786c781b7d3776a3ef7d6e5745d87f36a6` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles: **none** — judged by the kernel alone.
- Resolved environment: `sha256:4ab1a02b74d10501336534b1e256476fce453c83def53e860e96728133c26e99`

## Intent

Remove the last dependency on the retired storage SDK before its end of life.

FIXTURE DATA - not product evidence. Carries an execution_policy: the boundary on the DEVELOPMENT AGENT implementing this contract, not the runtime permissions of the built system.

## Scope

- **SC-SWAP** — Replace every call to the retired storage SDK with the new client.

## Explicitly not in scope

- **NG-BEHAVIOUR** — Exported report contents must not change.

## Authored requirements

- **AR-PARITY** *(MUST)* — Every export MUST produce byte-identical output to the pre-migration baseline.

## Declaration coverage

Of the obligations this contract activates, how many it **addresses**.
This is not completeness, and it is never readiness.

**Band 3 of 3** — every activated obligation is addressed.

| Domain | Band | Addressed | Activated |
|---|---|---|---|
| models | null | 0 | 0 |
| api_protocol | null | 0 | 0 |
| data_context | null | 0 | 0 |
| agent_runtime | null | 0 | 0 |
| identity_access | null | 0 | 0 |
| governance_safety | null | 0 | 0 |
| deployment_network | 3 | 0 | 0 |
| observability_economics | null | 0 | 0 |

### What remains open

Reported separately from coverage, and deliberately so: full coverage with open gaps is
an ordinary, correct state (`CORE-018`).

- `unknown_applicability` — Rule "AC-DATA-001" could not be decided: the contract did not declare the facts it reads.
- `unknown_applicability` — Rule "AC-CHANGE-001" could not be decided: the contract did not declare the facts it reads.

## Open questions

- **blocking** · `Q-APPLIES-AC-CHANGE-001` *(governance_safety)* — Does "Material model, tool or prompt changes invalidate production evidence" apply? The contract has not declared the facts the rule reads, so applicability is unknown.
- **blocking** · `Q-APPLIES-AC-DATA-001` *(data_context)* — Does "Sensitive data requires classification, access policy and retention" apply? The contract has not declared the facts the rule reads, so applicability is unknown.

## Execution policy

The boundary on the **development agent** implementing this contract — not the runtime
permissions of the system being built. Nothing here is executed by anything: a command
string in a policy is data (`CORE-086`).

| Family | Rules |
|---|---|
| `approval` | 1 |
| `commands` | 2 |
| `destructive` | 2 |
| `escalation` | 1 |
| `filesystem_protected` | 2 |
| `filesystem_read` | 1 |
| `filesystem_write` | 3 |
| `network` | 2 |
| `tools` | 1 |

A family not listed is **unspecified** — it is not `allow`, and it is not `deny`.

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:e38f3625eb2adff06a6f27e4453c9dd6e198bdfdfda717f0d5af1403acbf39eb`.
