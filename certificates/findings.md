# Findings summary

This is an editorial English summary of the original independent LLM audit
reports. The linked `verification.json` files are the unedited verdicts and
remain the authoritative audit outputs. No proof was repaired or resubmitted.
Repeated findings are retained in the original reports because they affect
different manuscript claims.

## Static frontier and binary Yuma

[Original report](second_layer/static/verification.json).

The audit found no error in the main derivations of the three static lemmas
and the positive-ownership frontier. The complete group did not pass:

- The manuscript does not define current shares, bonds, and their payment
  contribution when just one miner has zero total clipped weight. Binary
  reports create this case. The all-columns-zero fallback is a different case.
- The inheritance lemma permits zero ownership, but invokes a frontier
  defined only for positive ownership and gives no definition of `Q*(0)`.

These require explicit boundary definitions and corresponding arguments.
Restricting ownership to positive values would strengthen the hypotheses.

## Continuous weights

[Original report](second_layer/continuous/verification.json).

- The manuscript does not exclude one validator. At `n=1`, both thresholds
  are zero, contradicting the claimed strict comparison. The strict claim
  cannot retain its stated full domain; excluding this case adds a hypothesis.
- Several sign claims in the softer-weight proof use an unstated ownership
  range. They are false, for example, at `ell=2/5` and `omega=2`. This is an
  error in the argument, not a counterexample to the final threshold formula.
  The necessary and sufficient branches need explicit domains; simply adding
  `omega <= 1` strengthens the hypotheses.
- The zero-column definition problem also affects endpoint payments here.

## Default bond memory

[Original report](second_layer/default_memory/verification.json).

The audit accepted the stated first-layer algebraic premises and found no
algebraic error in state elimination, the convexity extension, or discounted
summation. Three gaps remain:

- Independent states and within-round conditional independence do not imply
  the fresh, history-conditional signal law used by the proof. An explicit
  condition on signals across rounds is an additional hypothesis.
- The exact endpoint deviation assumes a specified zero-column post-EMA
  normalization. The manuscript has not defined that process or established
  its correspondence with the calculation.
- The pooling argument does not supply a general, implementable reflection
  of arbitrary history-dependent strategies, with the required bond-state
  comparison. The potential identity and 256 finite paths do not fill this
  gap. This needs a complete argument; the audit does not establish whether
  the final claim must change.

## Unequal-stake capacity and its application

[Original report](second_layer/capacity/verification.json).

- The explicit payment construction leaves resource-budget completion and
  payments in minimal-majority profiles unstated. The audit classifies these
  as free completions using coefficient properties already in the passage.
- At a largest stake of exactly one half, one listed vertex violates the
  stated tie constraint. Correcting the feasible-face description is free;
  the selected optimal mixture itself satisfies that constraint.
- The stake domain does not exclude `(1,0,0)`. In this case quality cannot
  exceed `p`, whereas the formula gives `51/64 > 3/4` in the stated example.
  Excluding zero stakes adds a hypothesis; otherwise this endpoint needs a
  different conclusion.
- The formula is presented even when evaluation cost exceeds `V*d^2/6`,
  where the incentive constraints are infeasible. The feasible-cost domain
  and the no-feasible-rule case must be distinguished.
- The formula divides by ownership without handling zero ownership,
  including a `0/0` boundary. A zero-ownership branch is needed; restricting
  ownership to positive values adds a hypothesis.

## Persistence

[Original report](second_layer/persistence/verification.json).

- A one-step probability of retaining the state does not specify a symmetric
  Markov process conditional on the entire history. A mixture of permanently
  constant and permanently alternating state paths satisfies the stated
  one-step probability while violating the claimed belief bound. Explicit
  Markov transitions strengthen the written assumptions.
- The filtering and payment calculations also require a fixed, fresh signal
  law conditional on history and current state. Within-round independence
  alone is insufficient; the additional across-round condition is a hypothesis.
- The proof does not establish why the continuation value of current
  information drops out of the incentive comparison, or why the resulting
  one-round constraints rule out arbitrary discounted multiround deviations.
  This needs a complete argument; it is not a counterexample to the final
  frontier under suitably specified assumptions.
- The zero-ownership case, including the feasible-cost boundary, is undefined
  in the displayed quotient. It needs its own branch; imposing positive
  ownership instead strengthens the hypotheses.
