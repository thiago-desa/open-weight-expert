# Failure modes and troubleshooting

## Hardware honesty failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Oversized model on 8 GB | Recommending large Q8/Q6 chat models as "fine" | Prefer 2B-4B Q4 class; say when it will swap/throttle |
| Benchmark theater | Tok/s without heat/battery notes | Require thermal + battery observations |
| Stale shortlist | Months-old model names as current best | Re-open model cards / HF listings dated now |

## Product failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Assumed abliteration | Ships uncensored variant unasked | Ask preference first |
| Desktop instructions | "Run this Python venv on the phone" | Rewrite as iOS-realistic steps |
| Graph overclaim | Promising full GraphRAG on device | Frame as tiny SQLite/JSON notes with verification |

## Verification (design)

Eval loop: install, measure tok/s, heat, battery, answer quality on a tiny fixed prompt set. Structure (tools/graph) can beat raw parameter count on phone. Provenance: date every recommendation.
