# Maltin Contracts

Published Agent Contracts, in the form a Maltin reader consumes.

Each directory is one **Contract repository**: the authored contract, the lock that pins the exact
normative environment it was compiled against, and a human-readable card.

```
<contract>/
  maltin.contract.json   the authored document — normative
  maltin.lock.json       kernel ruleset, profiles and resolved environment, by hash
  CONTRACT.md            a deterministic projection for people — never authority
```

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

Adapting one in Maltin Studio starts a Blueprint that is **built from an allow-list**, not copied and
trimmed. It begins with descriptive scaffolding only: the contract id and version, the schema
version, the lifecycle marker, and the free-text `scope` and `non_goals`. None of those derives a
fact, activates a rule, raises a requirement, opens a gate, selects a profile or declares an
execution boundary. The Blueprint's purpose and its architecture start empty.

Everything normative reaches your Blueprint **only when you accept it** — what the Contract is for,
its architecture, the profiles it pins, its profile data, its execution boundary, its authored
requirements, acceptance criteria, verification, architecture boundaries, recorded decisions and
owners. Some of that is reviewed decision by decision; the rest is offered as whole sections, one
accept at a time. A section-sized accept is coarse, and it is still a decision you made.

So the guarantee is exact rather than rhetorical:

> A Blueprint in which you accept nothing compiles **byte-identically** to one built from that same
> descriptive scaffolding with no Contract in front of you. The compiled content hash is the same
> string — not "roughly the same Blueprint".

And the converse holds, which is what makes withholding safe rather than lossy: accepting every
section and every decision reproduces this Contract's compiled identity exactly.

If a Contract ever carried normative content Maltin had no way to offer you a decision about, the
adaptation would name it and refuse to compile rather than inherit it quietly or drop it quietly.
None of the seven here does.

## Reproducing them

These are generated, not hand-written. `maltin.lock.json` records the kernel ruleset version, each
profile by version and content hash, and the resolved environment hash — so compiling
`maltin.contract.json` against that environment reproduces the compiled hash the lock states. If your
environment has moved on, a reader will tell you the Contract is `Stale`, which is a fact about the
environment and not a judgement about the Contract.
