# open-weight-expert

On-device open-weight LLM advisor Grok Bot for iPhone-class hardware: picks models that fit 8 GB or 12 GB RAM, recommends runtimes, benchmarks honestly against heat and battery, and optionally layers a small local knowledge graph with Shortcuts automation.

## Problem it solves

Phone-side LLMs change monthly. Advice that ignores RAM, prefill cost, thermal throttling, and iOS memory pressure wastes downloads. This bot keeps a living playbook for practical open-weight setups on iPhone, prefers structure over raw parameter count, and stays honest when a model will not fit.

## How to use with Grok Bot

1. Create a new Grok Bot (suggested name: `open-weight expert`).
2. Paste the contents of `agents/open-weight-expert.md` (the **Description / system instructions** section) into the bot description / instructions.
3. Keep the skills in `skills/` and the living graph notes in `graphs/` alongside the bot.
4. On first run, confirm device RAM, goals, and whether censorship-reduced (abliterated) variants are acceptable.
5. Optionally add a weekly routine that checks for new on-device model releases.

## Import into Grok Bot

Copy this bot into your own Grok Bot: [On-Device iPhone LLM Expert template](https://x.ai/bot/G1ZOTtpS9XPPcAlUenBk1)

## Key files

| Path | What it is |
|------|------------|
| `agents/open-weight-expert.md` | Full sanitized agent definition |
| `graphs/on-device-llm-plan.md` | Living hardware, runtime, and model graph (generalized) |
| `skills/iphone-local-llm-playbook.md` | Pick, install, benchmark, optional graph layer |
| `skills/iphone-llm-getting-started.md` | First-conversation setup |
| `docs/architecture.md` | Phone-scale super-agent adaptations |
| `docs/workflow.md` | Device prep through eval loop |
| `examples/fictional-8gb-setup.md` | Fully fictional 8 GB setup walkthrough |
| `ATTRIBUTION.md` | Design influences and public sources |
| `LICENSE` | MIT |

## Proof-of-work notes

This repository is a cleaned public snapshot of an on-device LLM advisor design:

- Hardware viability layers for 8 GB and 12 GB class iPhones
- Runtime ranking and model shortlist discipline tied to real device limits
- Optional SQLite / JSON graph layer with verification
- Eval set and iteration loop instead of benchmark-chasing alone
- Fictional example only (no personal device serials or private notes)

## License and attribution

MIT License. Copyright (c) 2026 Thiago De Sa.

Design influences and public research sources are listed in `ATTRIBUTION.md`.
