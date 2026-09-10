# Extract the billing calculator from the monolith

> A **Maltin Contract**: what this system must do, and which obligations follow from that.
> It is a specification. It makes **no claim that anything has been built or verified** —
> that judgement needs observations of a running system and is not in this file.

## Identity

| | |
|---|---|
| Contract | `fixture-brownfield-refactor` |
| Version | `0.1.0` |
| Schema | `4.0.0` |
| Specification lifecycle *(derived)* | `incomplete` |
| Authored contract hash | `sha256:0fe9951a47e1559bd0d47838c81a67a2257598d142ac2fcdf7cd29b8681fbfc0` |

## Normative environment

The exact rules this contract was judged by. Reproduce it from `maltin.lock.json`.

- Kernel ruleset: `3.0.0`
- Profiles: **none** — judged by the kernel alone.
- Resolved environment: `sha256:4ab1a02b74d10501336534b1e256476fce453c83def53e860e96728133c26e99`

## Intent

Make billing logic independently testable and releasable.

FIXTURE DATA - not product evidence. Proves the Contract Kernel works with NO AI architecture: no models, no tools, no agent runtime.

## Scope

- **SC-EXTRACT** — Move billing calculation out of the monolith into its own module.
- **SC-TESTS** — Bring the existing billing test suite with it, unchanged.

## Explicitly not in scope

- **NG-BEHAVIOUR** — Public billing behaviour must not change. This is a structural move, not a redesign.
- **NG-PRICING** — Do not alter pricing rules, rounding or currency handling.
- **NG-SCHEMA** — Do not migrate the billing database schema.

## Authored requirements

- **AR-COMPAT** *(MUST)* — The extracted module MUST produce byte-identical invoice output for every input in the existing regression corpus.
- **AR-NO-CYCLE** *(MUST)* — The monolith MUST NOT depend on internal details of the extracted module.
- **AR-PERF** *(SHOULD)* — Invoice generation SHOULD not regress by more than 5% at p95.

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

Compiling the contract against the locked environment yields `sha256:84de50d02742fef144f044c2142af1dd8c64ebd88e01623367198ea9c148a23f`.
