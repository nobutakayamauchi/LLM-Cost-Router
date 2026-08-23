# Product Definition

## Promise

LLM Cost Router reduces unnecessary inference usage by routing work through the smallest sufficient context, tool set, and reasoning depth while preserving acceptance quality.

## V1 customer

Primary V1 users are heavy users of coding agents such as Codex who regularly hit usage limits, work across non-trivial repositories, and pay a recurring context/reasoning tax.

## V1 jobs to be done

1. Identify when deterministic tools should run before expensive reasoning.
2. Select only the context needed for the current task.
3. Start at the lowest reasonable reasoning tier and escalate only when evidence requires it.
4. Compress execution evidence so later steps do not need to reread raw logs.
5. Persist cost/usage telemetry for before/after comparison.
6. Detect when lower cost is being purchased by lower quality.

## Non-goals for V1

- claiming universal savings across every model and task
- replacing the coding agent itself
- exposing proprietary routing logic in the public repository
- optimizing solely for token count while ignoring successful completion

## Product success metric

The canonical metric is:

**observable usage per accepted result**

Supporting metrics include retry count, rereads, tool calls, human intervention, elapsed time, and tasks completed before a usage-limit reset.

## Release gate

A paid release requires all of the following:

- installable by a user other than the author
- Router OFF / ON benchmark harness
- fixed acceptance criteria for benchmark tasks
- quality regression detection
- usage/cost ledger
- documented rollback / disable path
- reproducible evidence for every public savings claim
