# Verification records

**Status:** 14 existing first-layer records; 0/5 second-layer proof groups passed. Groups with findings have no second-layer pass credential. The manuscript was not repaired as part of this audit.

These materials accompany *Why Hedging Breaks Yuma: Report-Only Rewards for
Decentralized AI Evaluation*. The two layers have different scopes.

- **First layer:** [exact/symbolic records and reproduction commands](first_layer/README.md).
  Fourteen existing computational records are supplied, together with the
  scripts and saved certificates in the complete replication package.
- **Second layer:** independent LLM audits of the existing manuscript proofs,
  completed on 2026-09-30. The original verdicts are reproduced without editing.
  A pass is an LLM proof audit, not Lean/Coq verification or a formal guarantee.

## Second-layer results

An [English findings summary](findings.md) accompanies the unedited reports.

| Manuscript group | Result | Audit inputs and result | Pass credential |
|---|---|---|---|
| Static frontier, binary Yuma, and inheritance of the frontier | No pass: 0 critical error(s), 2 gap(s) | [verdict](second_layer/static/verification.json), [proof](second_layer/static/blueprint.md) | No pass credential issued |
| Continuous-weight hedging and softer weights | No pass: 2 critical error(s), 1 gap(s) | [verdict](second_layer/continuous/verification.json), [proof](second_layer/continuous/blueprint.md) | No pass credential issued |
| Default bond memory: all three equilibrium claims | No pass: 0 critical error(s), 3 gap(s) | [verdict](second_layer/default_memory/verification.json), [proof](second_layer/default_memory/blueprint.md) | No pass credential issued |
| Unequal-stake premium capacity and its stated application | No pass: 3 critical error(s), 2 gap(s) | [verdict](second_layer/capacity/verification.json), [proof](second_layer/capacity/blueprint.md) | No pass credential issued |
| The frontier with persistence | No pass: 0 critical error(s), 4 gap(s) | [verdict](second_layer/persistence/verification.json), [proof](second_layer/persistence/blueprint.md) | No pass credential issued |

The [reviewed manuscript source](second_layer/inputs/paper.tex) fixes the
definitions, assumptions, equations, and proof text covered by these reports.
Each `blueprint.md` contains verbatim theorem and proof environments; no
argument was repaired for the audit. Each `problem.md` records the original
scope and any accepted first-layer algebraic premises. Its `Rethlas/` paths
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
