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

A Contract you find here **proposes; it never accepts.** Adapting one in Maltin Studio starts a
Blueprint of your own in which every imported decision is offered for review — none of them becomes
yours until you say so, and a Blueprint where you accept nothing compiles to exactly what you would
have got by starting from scratch.

## Reproducing them

These are generated, not hand-written. `maltin.lock.json` records the kernel ruleset version, each
profile by version and content hash, and the resolved environment hash — so compiling
`maltin.contract.json` against that environment reproduces the compiled hash the lock states. If your
environment has moved on, a reader will tell you the Contract is `Stale`, which is a fact about the
environment and not a judgement about the Contract.
