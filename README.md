# Why Hedging Breaks Yuma: replication materials

Replication package for **Why Hedging Breaks Yuma: Report-Only Rewards for
Decentralized AI Evaluation**.

**[Download the complete replication package](https://raw.githubusercontent.com/submissionrepo/bittensor-yuma-replication/main/bittensor-yuma-replication.zip)**

The ZIP contains 88 files (approximately 7.8 MB uncompressed). Source code,
saved data, exact-arithmetic certificate outputs, and detailed instructions are
inside the archive. No credentials, private project history, or compiled
executables are included.

## Getting started

Download the archive and extract it, or clone this repository and run:

```sh
python -m zipfile -e bittensor-yuma-replication.zip .
cd bittensor-yuma-replication
python smoke_test.py
```

The smoke test uses the Python standard library. It replays 36 saved official
epoch fixtures and checks the presence of all 36 experiment comparisons, each
based on 2048 paired draws. The independent submission directory passed this
test; the experiment tables and both data figures were also regenerated there.

For table and figure generation, install the included Python dependencies:

```sh
python -m pip install -r requirements.txt
python research_ideas/bittensor_paper_a/make_single_hedge_tables.py
python research_ideas/bittensor_paper_a/tex/figures/make_frontier.py
python research_ideas/bittensor_paper_a/tex/figures/make_influence.py
```

The archive's root `README.md` gives the complete result-to-script mapping,
certificate commands, and instructions for reproducing the full experiment.
Python 3.11 was used. Rebuilding the Rust reference requires Rust 1.89.0 and
downloads of the specified public upstream sources; its build instructions are
in `research_ideas/probes/bittensor/protocol/README.md` inside the archive.

## Included materials

| Material | Location inside the extracted package |
|---|---|
| Numerical tables, figure generators, and quoted-number calculations | `research_ideas/bittensor_paper_a/` |
| Static and dynamic calculations and rational certificates | `research_ideas/probes/bittensor/` |
| Fixed-point Python epoch, Rust reference source, official fixtures, and differential results | `research_ideas/probes/bittensor/protocol/` |
| Multi-miner hedging experiment and sampled 16-bit ownership caps | `research_ideas/probes/bittensor/numerics/` |

The fixed-point implementation targets Subtensor commit
`c004cebf360f4088187ee49d851dfb1a1eaaf710`. Upstream attribution and license
texts are preserved in the archive's protocol directory.

The Monte Carlo experiment uses the legacy path with bond memory off. The
16-bit ownership caps concern a sampled report grid. Software comparisons and
finite numerical checks are not universal proof certificates; the mathematical
statements retain the assumptions and scope given in the paper.
