# Maltin Contracts

A **Git Registry**: a Git repository holding one or more **Contract Packages**.

Each directory is one Contract Package — the authored contract, the lock that pins the exact
normative environment it was compiled against, and a human-readable card.

```
hub.index.json           what this registry contains. Discovery only, never authority
<contract>/              one Contract Package
  maltin.contract.json   the authored document — normative
  maltin.lock.json       kernel ruleset, profiles and resolved environment, by hash
  CONTRACT.md            a deterministic projection for people — never authority
  maltin.lineage.json    optional — where this Contract was adapted from. Non-normative
```

A Git Registry holding exactly one Contract Package at its root is equally valid. Nothing requires
one Git repository per Contract, and nothing requires a Contract to live here.

## The index

`hub.index.json` lets a reader find out what this registry contains in **one request** instead of
two per package. It carries a directory, a name, the author's own description, a use-case family, a
schema version and the profile ids — and nothing else.

It is **not evidence**. An entry says somebody claimed a Contract is in that directory. Whether the
Contract is there, whether it is valid, and whether its environment still resolves are three further
questions, answered only by fetching `maltin.contract.json` and `maltin.lock.json` and validating
them. If the index and a Contract disagree, the Contract is right.

It is generated from packages that validated, never hand-maintained, and byte-identical for
byte-identical registry state.

## What these are

**First-party examples, published by the Maltin project.** They are not community submissions and
carry no endorsement of anything. They exist so the Maltin Hub has real Contracts to read over a real
network, and so anyone can see exactly what a published Contract looks like before publishing one.

## What these are not

Not a package registry. Nothing here is installed, executed or depended on. A Contract is a statement
of intent that a compiler can check — reading one runs nothing.

Every value in `maltin.contract.json` is **data**. Commands, tool names and paths that appear in an
execution policy are declarations of a boundary, not instructions to run: a reader that executed them
would be the bug.

## Using one

A Contract you find here **proposes; it never accepts.**

Adapting one in Maltin Studio starts a Blueprint that is **built locally**, not copied and trimmed.
The rule it holds to is stronger than "nothing dangerous is inherited":

> **No authored specification content from a source Contract becomes part of an adapted Blueprint
> without an explicit review action.**

Not *nothing that activates a rule*. Nothing you wrote down. That distinction is the whole of it:

```
scope:     only EU customers
non_goals: do not support multi-region
```

Neither of those makes a compiler do anything. Both are commitments their author made, and neither
becomes the adapting user's commitment by default. The same goes for the purpose, the architecture,
the profiles, the profile data, the execution boundary, the requirements, the acceptance criteria,
the verification, the boundaries, the recorded decisions and the owners. Some of it is reviewed
decision by decision; the rest is offered as whole sections, one accept at a time. A section-sized
accept is coarse, and it is still a decision somebody made.

The Blueprint starts with the scaffolding a document needs to be a document — an identity, a version,
the schema version, a lifecycle — and **every one of those values is its own**, not this Contract's.

So the guarantee is exact rather than rhetorical:

> A Blueprint in which you accept nothing compiles **byte-identically** to one started by somebody
> who never opened this registry. The compiled content hash is the same string — not "roughly the
> same Blueprint".

## Adapting makes a new Contract, not a copy of this one

The converse holds too, and it is the more interesting half. Accept every proposal and the result
reproduces this Contract's **meaning** exactly — every authored section, and every conclusion the
compiler draws from them: activated requirements, applicability, open questions, gates, completeness
and the resolved normative environment.

Its **identity is still its own**:

```
semantics(yours) == semantics(this one)     when you accept everything
identity(yours)  != identity(this one)      always
```

Different `contract_id`, different `contract_version`, different authored hash, different compiled
hash. A Contract adapted from another is a new Contract — that is what makes this a flywheel rather
than a photocopier. The relationship between the two is real, and it is recorded outside the
Contract's own state rather than inside it, so neither hash moves.

If a Contract ever carried normative content Maltin had no way to offer you a decision about, the
adaptation would name it and refuse to compile — rather than inherit it quietly or drop it quietly.
None of the seven here does.

## Reproducing them

These are generated, not hand-written. `maltin.lock.json` records the kernel ruleset version, each
profile by version and content hash, and the resolved environment hash — so compiling
`maltin.contract.json` against that environment reproduces the compiled hash the lock states. If your
environment has moved on, a reader will tell you the Contract is `Stale`, which is a fact about the
environment and not a judgement about the Contract.
