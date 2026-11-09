# On-device open-weight LLM plan (living graph)

Generalized public snapshot of a phone-first open-weight operating plan (late 2026 framing). Re-verify every model and tok/s claim before recommending.

## Mission

Turn an iPhone (8 GB or 12 GB RAM class) into a practical offline LLM machine running the strongest open-weight model that fits, with optional graph structure and Shortcuts automation.

## Core principles

- Structure (graphs + constrained tools + verification) beats raw model size.
- On 8 GB, 2B to 4B Q4 is the practical sweet spot. Prefill is usually the bottleneck, not decode. Thermal throttling and iOS memory pressure are real limits.
- Abliteration / Heretic techniques can reduce refusals on small models; ask before recommending them.
- Expert-streaming runtimes can make large MoE models technically possible at about 1 tok/s: quality experiments, not daily chat.

## Hardware viability

| Device class | RAM | Comfortable | Marginal |
|--------------|-----|-------------|----------|
| Base iPhone (A-series, 8 GB class) | 8 GB | 0.8B to 4B | 7B to 8B short context |
| Pro / higher RAM class | 12 GB | 4B to 8B, longer context | Still not a workstation |

Single-focus viability rises with Focus Mode, Screen Time limits, closed background apps, and plugged-in or cooled sessions.

## Runtime ranking (practicality first)

1. Open-source multi-backend apps (MLX + llama.cpp + Core ML) with a fit check before download
2. Curated paid apps with strong abliterated / Heretic catalogs
3. Clean MLX-focused apps
4. Apps with grammar-constrained tool calling (good agent foundation)
5. On-device OpenAI-compatible local API servers
6. Experimental large-MoE streaming from storage
7. Hybrid: phone as client to a local Mac or remote API for deep multi-hop work

MLX is often fastest on Apple Silicon for supported models; GGUF usually has the widest catalog.

## Model shortlist discipline

Prefer a small daily driver (Qwen / Gemma / LFM class in the 2B to 4B band, Q4) and optionally one distilled reasoning model if RAM allows. Treat 30B+ MoE streaming as experimental. Full frontier MoE models stay hybrid or API-only.

Always re-check Hugging Face quantizations and real device reports before naming a "best" pick.

## Phone-scale graph layer

1. Ingest (notes, files, OCR, Shortcuts)
2. Extract entity-relation triples with structured output plus an evidence quote
3. Resolve duplicate entities
4. Store in SQLite or JSON with a small embedding index (avoid heavyweight graph DBs)
5. Retrieve with vector plus 1 to 3 hop paths
6. Require cited relationship types; flag contradictions
7. Timestamp updates; never silently overwrite

## Super-agent adaptations on phone

- Event-driven via Shortcuts + Focus Mode
- Inline and spill + chain of recall for tiny context windows
- Small local model as router; larger local or API model as worker

## Eval loop

Keep 10 to 20 hard personal why/how questions. Re-run after every change. Optimize for usable speed, low unwanted refusal (per owner preference), and graph accuracy, not leaderboard scores alone.
