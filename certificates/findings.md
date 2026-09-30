# Repairs and original findings

This is an editorial summary of the authorized manuscript repairs. The
[verification index](README.md) gives the current results; each linked JSON
report is the independent verifier's unedited verdict. The first submission's
manuscript, proof packets and failed reports remain in
`second_layer/history/attempt1/`. A later pass concerns the revised statement
and premises, not the original text.

The abstract, introduction, and all material before the Model section are
unchanged. Other manuscript changes concern the reported mathematical issues
and the disclosure of the verification scope beside the replication link.
The paper remains 12 pages with the original font and margins; redundant
main-text sketches were removed while the complete appendix proofs remain.

| Group | Original finding | Repair and effect on scope |
|---|---|---|
| Static | Zero clipped columns were undefined; the inheritance lemma used an undefined zero-ownership frontier. | Define zero current shares and post-EMA normalization of positive bond columns. State and prove the zero-ownership branch, including the maximal feasible cost. The positive-ownership formula is unchanged. |
| Continuous | The strict threshold comparison failed at one validator; soft-weight sign arguments silently assumed bounded ownership; endpoint payments were undefined. | Require odd `n >= 3`, which strengthens the model's written domain. Derive the necessary ownership bound before using it in the sufficiency argument, retaining the full `omega >= 0` domain. Apply the explicit zero-column convention at the endpoints. |
| Default memory | Fresh errors across rounds and zero-column normalization were missing; the general reflection argument was absent. | Specify conditional independence across agents and rounds given the exogenous state path, which strengthens the written signal assumptions. Define the zero-column update. Supply an implementable reflection of arbitrary strategies, bond-deficit comparisons, and the discounted potential argument. The three equilibrium conclusions retain their stated numerical parameters. |
| Capacity | Payment construction omitted budget completion and zero-coefficient profiles; a vertex was infeasible at half stake; zero stake, infeasible costs, and zero ownership were mishandled. | Complete all profile payments, restrict the four-vertex description to stake strictly above one half, and show the optimizer remains on the feasible face at equality. Require positive stakes, an additional hypothesis. Separate feasible costs from the no-rule region and provide the zero-ownership optimum. |
| Persistence | A one-step retention probability did not imply a Markov process; fresh signals and a continuation-value argument were missing; zero ownership was undefined. | State the stationary binary symmetric Markov kernel and fresh signal law, strengthening the written assumptions. Derive an affine honest-continuation value and telescope the resulting inequality for arbitrary randomized history-dependent deviations. Add the zero-ownership frontier, including the feasible-cost boundary. |

The payment completion and half-stake feasible-face correction use facts
already present in the original argument. The stochastic-process, committee-size,
and positive-stake restrictions are explicit additions to its assumptions.
The reflection and continuation arguments are new proof completions; finite
replays alone do not establish them.

The new [repair algebra record](first_layer/records.json) checks the displayed
reflection, continuation, Bayes, and soft-threshold algebra. The
[complete first-layer replay](first_layer/replay.md) reruns the existing
generators after the repairs. Independent LLM proof review remains distinct
from exact or symbolic computation and from formal theorem-prover verification.

A follow-up persistence audit identified the zero-discount endpoint: future
history deviations have no initial payoff weight when `delta=0`. The final
theorem explicitly applies the static feasibility bound and frontier there,
and uses the persistence result for `delta>0`. This preserves the full
discount domain and the original equilibrium concept. The failed intermediate
report is retained in `second_layer/history/persistence_attempt2/`.
