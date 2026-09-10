# Add async pagination to the client SDK

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-library-sdk-change` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:9002d238c19b5067a9307a56a55ad5caf4a4fc040728ef3c3694e8d4f5851832` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles: **none** — judged by the kernel alone.
- Resolved environment: `sha256:4ab1a02b74d10501336534b1e256476fce453c83def53e860e96728133c26e99`

## Intent

Let consumers iterate large result sets without holding them in memory.

FIXTURE DATA - not product evidence. Zero AI architecture: no model, no tool, no agent runtime, no datasets.

## Scope

- **SC-ITER** — Add an async iterator to every list endpoint wrapper.

## Explicitly not in scope

- **NG-BREAKING** — Do not remove or change the signature of any existing public method.
- **NG-RUNTIME** — Do not add a runtime dependency.

## Authored requirements

- **AR-SEMVER** *(MUST)* — The public API MUST remain backward compatible; the release MUST be a minor version.
- **AR-TYPES** *(MUST)* — The new iterator MUST be fully typed with no `any` in the published declarations.

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

## Reproducing this

`maltin.contract.json` is the only editable truth in this repository. `maltin.lock.json`
and this file are projections of it: delete them, regenerate, and nothing is lost.

Compiling the contract against the locked environment yields `sha256:604a6c499decbeb69f14e913f12c910f95e7f51ede23f7fcad3f4a3b40c9d414`.
