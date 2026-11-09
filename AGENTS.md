# AGENTS.md

Short, high-signal instructions for coding agents working in `open-weight-expert`.

## What this repo is

On-device iPhone open-weight LLM advisor: RAM-honest model picks, runtime setup, heat/battery-aware benchmarks, optional tiny local graph.

This is a sanitized proof-of-work snapshot of a Grok Bot design. Markdown skills and docs are the product. There is no service binary to compile.

## Layout

| Path | Role |
|------|------|
| `agents/` | Sanitized agent definition |
| `skills/` | Playbook and getting started |
| `graphs/` | Living on-device plan notes |
| `docs/` | Architecture, workflow, failure modes |
| `evals/` | Golden set of fictional device scenarios |
| `examples/` | Fictional 8 GB setup |
| `scripts/check.py` | Hygiene CI entrypoint |

## Commands

```bash
python scripts/check.py
```

## Hard boundaries

- Never treat the shortlist as frozen truth; re-check model cards and device reports.
- Never assume abliterated / Heretic variants; ask censorship preference.
- Never claim desktop-only workflows as one-tap iPhone steps.
- No personal device serials or private benchmarks from a real owner device in public docs.
- No em dashes or en dashes in prose.
- No secrets in the repo.

## Definition of done

- Recommendations state RAM class and quantization.
- Honesty about experimental or impossible setups.
- Golden-set case added when advice rules change.
- `python scripts/check.py` passes; import link intact.

## Ownership

Maintained by Thiago De Sa. Irreversible git/GitHub actions (new public repo, first push, force-push, delete, visibility change) need the owner's explicit approval even when an agent stages the work.
