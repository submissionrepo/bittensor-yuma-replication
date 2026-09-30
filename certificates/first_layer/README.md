# First layer: exact and symbolic computations

[records.json](records.json) reproduces 15 computational records, including
the new algebra supporting the manuscript repairs, with their statements,
layers, dates, evidence, and limitations. After the repairs, all 14 generators
were rerun successfully; the [replay record](replay.json) and [raw log](replay.md)
document that run. The dates in the original records remain their original
dates. Independent proof audits are listed in the [verification index](../README.md).

`exact` denotes the stated rational/finite certificate; `sympy` denotes the
stated symbolic calculation. Finite enumerations and numerical LP agreement
do not certify arbitrary committee sizes or all deviations. The first layer
does not, by itself, validate economic reductions or infinite-horizon proofs.

Scripts and saved `.md`/`.json` outputs are in the corresponding paths inside
the complete replication ZIP. Some generators also perform explicitly marked
discovery calculations. Their numerical output is not additional proof evidence.

| Paper result | Certified computational scope | Script in the extracted package |
|---|---|---|
| Static frontier | 240 rational candidates and four finite LP optimality certificates; not arbitrary n. | `research_ideas/probes/bittensor/static_frontier_probe.py` |
| Supporting static algebra | Includes 22 finite-n binomial identities. The record also covers separate coalition algebra; that algebra is not a Paper A theorem certificate. | `research_ideas/probes/bittensor/symbolic_frontier_checks.py` |
| Binary Yuma | Twelve rational endpoint cases and 48 positive-softening comparisons. | `research_ideas/probes/bittensor/yuma_endpoint_probe.py` |
| Default memory, zero endpoint | An exact positive-gain deviation against the specified extreme-report continuation. | `research_ideas/probes/bittensor/yuma_endpoint_probe.py` |
| Continuous weights | Twelve finite cases, the three-validator threshold identity, and continuity identities. | `research_ideas/probes/bittensor/yuma_continuous_theory.py` |
| Softer weights and unequal stake | Derivative identities, Bernstein sign certificates, 21 epoch comparisons, and specified threshold-ratio inequalities. | `research_ideas/probes/bittensor/theory_completion_checks.py` |
| Premium capacity | 27 rational support-function instances; not the universal capacity theorem. | `research_ideas/probes/bittensor/rent_capacity_probe.py` |
| Unequal-stake Yuma example | Six specified stake vectors and exact conditional report-margin comparisons. | `research_ideas/probes/bittensor/stake_extension_probe.py` |
| Default informative equilibrium | 324 rational interval inequalities, 84 epoch comparisons, and expectation/state-potential identities. | `research_ideas/probes/bittensor/default_dynamic_certificate.py` |
| Default-memory extensions | 18 derivative bounds, a strict interval bound, and the exact finite-history profitable deviation. | `research_ideas/probes/bittensor/default_dynamic_extensions_certificate.py` |
| Pooling equilibrium | Potential identity and exact cap 8218/8175; 256 finite paths do not prove the general reflection argument. | `research_ideas/probes/bittensor/dynamic_pooling_certificate.py` |
| Persistence, three validators | Symbolic identities and rational substitutions. Numerical LP matches are discovery only. | `research_ideas/probes/bittensor/dynamic_memoryless_probe.py` |
| Persistence, larger committees | 52 symbolic identities at n=3,5,7,9; not the arbitrary-n history-dependent equilibrium theorem. | `research_ideas/probes/bittensor/dynamic_frontier_general_probe.py` |
| Threshold table | 63 new rational substitutions for odd n=11 through 51, combined with 12 reused points. | `research_ideas/bittensor_paper_a/threshold_table.py` |
| Repair algebra | Fourteen exact clipping/reflection, affine-continuation/Bayes, and soft-threshold identity/sign records; not a substitute for the full strategy arguments. | `research_ideas/bittensor_paper_a/repair_checks.py` |

## Reproduce the calculations

After extracting the package and installing `requirements.txt`, run from its root:

```sh
python research_ideas/probes/bittensor/static_frontier_probe.py
python research_ideas/probes/bittensor/symbolic_frontier_checks.py
python research_ideas/probes/bittensor/yuma_endpoint_probe.py
python research_ideas/probes/bittensor/yuma_continuous_theory.py
python research_ideas/probes/bittensor/theory_completion_checks.py
python research_ideas/probes/bittensor/rent_capacity_probe.py
python research_ideas/probes/bittensor/stake_extension_probe.py
python research_ideas/probes/bittensor/default_dynamic_certificate.py
python research_ideas/probes/bittensor/default_dynamic_extensions_certificate.py
python research_ideas/probes/bittensor/dynamic_pooling_certificate.py
python research_ideas/probes/bittensor/dynamic_memoryless_probe.py
python research_ideas/probes/bittensor/dynamic_frontier_general_probe.py
python research_ideas/bittensor_paper_a/threshold_table.py
python research_ideas/bittensor_paper_a/repair_checks.py
```

The scripts write outputs beside themselves. Saved outputs are included, so running these commands is optional for reading the certificates. The software smoke test is a separate check.
