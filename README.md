# LLM-Cost-Router

Route context, tools, and reasoning to reduce LLM/Codex inference cost without sacrificing task quality.

## Repository role

This is the public interface/concept surface. Public contracts, examples, and intentionally exposed routing behavior belong here.

Private/proprietary routing logic and evaluation assets belong in `nobutakayamauchi/LLM-Cost-Router-Core` when applicable.

## Core rule

```text
LOWER CONTEXT != LOWER EVIDENCE
LOWER COST != LOWER REQUIRED QUALITY
```

The router should prefer the smallest sufficient context, load tools only when the active task needs them, and preserve explicit UNKNOWN/CONFLICT instead of compressing uncertainty into a confident answer.

## AI entry

Read `AGENTS.md` first. Do not scan unrelated experiments or private-core material by default.