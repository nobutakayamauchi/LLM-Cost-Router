# Benchmark Protocol

## Purpose

Measure whether LLM Cost Router reduces observable inference usage without reducing the probability that a task reaches the same acceptance gate.

## Comparison arms

For each benchmark set, keep task definitions and acceptance criteria fixed and compare:

- **A — Baseline:** existing workflow with the router disabled
- **B — Routed:** same workflow with LLM Cost Router enabled

Where useful, a third arm may be added for a less-optimized/default agent workflow, but product claims must not depend on an artificially weak baseline.

## Required observations

Capture when observable:

- task identifier and repository revision
- pass / fail against fixed acceptance criteria
- input and output usage
- cache usage if exposed
- files read
- repeated reads of the same file
- deterministic tool calls
- LLM/reasoning calls by tier
- retries
- human interventions
- elapsed time
- final change size

## Canonical metric

`usage_per_accepted_result = total_observable_usage / accepted_results`

A benchmark with zero accepted results is invalid for a savings claim.

## Quality guardrail

Never publish a savings percentage without publishing the acceptance result for the compared arms. If the routed arm materially lowers success quality, the result is a regression, not a saving.

## Claim rules

- No cherry-picking only successful routed tasks.
- No mixing materially different repository revisions without disclosure.
- No comparing different acceptance gates.
- Report missing telemetry explicitly.
- Prefer multiple tasks over a single showcase task.
- Preserve raw benchmark evidence privately before publishing derived summaries.

## First dogfood target

Compare the current optimized development workflow against the same workflow plus LLM Cost Router on a set of real repository tasks. The first objective is evidence, not a predetermined savings percentage.
