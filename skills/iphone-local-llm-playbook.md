# Skill: iPhone on-device LLM playbook

Use when helping someone pick, install, benchmark, or build around an open-weight LLM running fully on an iPhone.

## Principles

- Structure (graph + constrained tools + verification) beats raw model size.
- On 8 GB, 2B to 4B at Q4 is the sweet spot; 7 to 8B is marginal with short context. 12 GB gives headroom for 4B to 8B.
- Prefill is usually the bottleneck, not decode. Thermal throttling and iOS memory-pressure kills are real limits; a cool 4B beats a throttling 8B.
- Expert-streaming runtimes can run 30B+ MoE models at about 1 tok/s: quality experiments only.
- Always verify current model cards, Hugging Face listings, and real device reports before recommending; this space changes monthly.

## Steps

1. Confirm device model and RAM, free storage, and what the user wants the model for (chat, reasoning, tools, document graph). Ask about their tolerance for censorship-reduced (abliterated) variants rather than assuming.
2. Pick a runtime app: open-source multi-backend apps (MLX + llama.cpp + Core ML) with a fit check are the default; curated paid apps are easiest; local OpenAI-compatible server apps help for agents. MLX is usually fastest on Apple Silicon; GGUF has the widest model support.
3. Shortlist 2 to 3 models that fit (small Qwen, Gemma, LFM class, or a distilled reasoning model if RAM allows). Look up current quantizations and reported tok/s.
4. Benchmark: tok/s, heat, battery drain, and quality on 5 to 10 of the user's own hard why/how questions. Keep the one that stays cool and answers well.
5. Graph layer (optional): ingest notes or files, extract entity-relation triples with structured output plus an evidence quote, resolve duplicate entities, store in SQLite or JSON with a small embedding index, retrieve with vector plus 1 to 3 hop paths, require cited relationships, timestamp updates and never silently overwrite.
6. Agent layer (optional): small local model as router with grammar-constrained tool calls; a bigger local or API model as worker for deep multi-hop work.
7. Keep an eval set and re-run it after every change. Log what changed and the result.
