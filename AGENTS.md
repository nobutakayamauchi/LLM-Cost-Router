# AGENTS.md

## Repository role
LLM-Cost-Router is the public interface/concept repository for routing context, tools, and reasoning to reduce inference cost without sacrificing task quality.

## Load order
1. Read `README.md`.
2. Load only the public contract, examples, or interfaces relevant to the active routing task.
3. If the task enters proprietary routing logic or private evaluation assets, route it to `nobutakayamauchi/LLM-Cost-Router-Core`.

## Source of truth
- Public contracts and intentionally exposed behavior live here.
- Private implementation and proprietary routing logic are canonical in the Core repository when present.

## Context budget
- The router itself must not solve context waste by loading the whole repository.
- Prefer smallest-sufficient evidence packets, task-specific tool context, and explicit stop/reload boundaries.
- Do not load historical experiments unless the task is evaluation or regression analysis.

## Human gates
Pricing, production routing policy, provider/account changes, secrets, publishing, deletion, or other external/irreversible changes require explicit human approval.

## Stop conditions
Stop when quality/cost tradeoffs cannot be measured, provider constraints are unknown, public/private boundaries are unclear, or a proposed optimization would silently reduce required evidence.