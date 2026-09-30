# Verification records

**Status:** 15 first-layer computational records, replayed after repair; 5/5 second-layer proof groups passed. These results concern the repaired manuscript; the original failed audits remain available.

These materials accompany *Why Hedging Breaks Yuma: Report-Only Rewards for
Decentralized AI Evaluation*. The two layers have different scopes.

- **First layer:** [exact/symbolic records and reproduction commands](first_layer/README.md).
  Fifteen computational records and a complete post-repair replay are supplied,
  together with scripts and saved certificates in the replication package.
- **Second layer:** independent LLM audits of the repaired manuscript proofs,
  completed on 2026-09-30. The verifier's verdicts are reproduced without editing.
  A pass is an LLM proof audit, not Lean/Coq verification or a formal guarantee.

## Second-layer results

An [English repair summary](findings.md) accompanies the unedited reports.
The [first submission](second_layer/history/attempt1/inputs/paper.tex) and its
failed reports are preserved under `second_layer/history/attempt1/`.
The [intermediate zero-discount finding](second_layer/history/persistence_attempt2/verification.json)
and its reviewed text are also retained.

| Manuscript group | Result | Audit inputs and result | Pass credential |
|---|---|---|---|
| Static frontier, binary Yuma, and inheritance of the frontier | Pass | [verdict](second_layer/static/verification.json), [proof](second_layer/static/blueprint.md) | [credential](second_layer/static/blueprint_verified.md) |
| Continuous-weight hedging and softer weights | Pass | [verdict](second_layer/continuous/verification.json), [proof](second_layer/continuous/blueprint.md) | [credential](second_layer/continuous/blueprint_verified.md) |
| Default bond memory: all three equilibrium claims | Pass | [verdict](second_layer/default_memory/verification.json), [proof](second_layer/default_memory/blueprint.md) | [credential](second_layer/default_memory/blueprint_verified.md) |
| Unequal-stake premium capacity and its stated application | Pass | [verdict](second_layer/capacity/verification.json), [proof](second_layer/capacity/blueprint.md) | [credential](second_layer/capacity/blueprint_verified.md) |
| The frontier with persistence | Pass | [verdict](second_layer/persistence/verification.json), [proof](second_layer/persistence/blueprint.md) | [credential](second_layer/persistence/blueprint_verified.md) |

The [reviewed manuscript source](second_layer/inputs/paper.tex) fixes the
definitions, assumptions, equations, and proof text covered by these reports.
Each `blueprint.md` contains verbatim theorem and proof environments from the
repaired manuscript; no separate argument was supplied only to the reviewer.
Each `problem.md` records the scope and accepted first-layer algebraic premises. Its `Rethlas/` paths
describe the audit workspace; the reviewed paper is supplied above, and the
referenced computational outputs are in the replication ZIP.

Only a verdict of `correct` with no critical errors and no gaps produces a
`blueprint_verified.md`. A report containing findings is not a partial pass.
The reports concern their stated mathematical scope; they do not certify the
novelty of the work, its empirical model, every software input, or results from
other papers. In particular, no coalition-phase theorem is covered here.

This directory is a publication export of the shared verification records.
It does not replace the source ledger or create a separate verification state.
The computational records retain their original dates and limitations; the
later second-layer results are shown explicitly above.
