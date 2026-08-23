# LLM Cost Router

> Spend reasoning where it matters. Stop paying context tax everywhere else.

LLM Cost Router is a commercial product for reducing unnecessary LLM/Codex inference usage while preserving task quality.

## The problem

Agentic coding often burns usage on work that does not need expensive reasoning: rereading the same context, exploring too broadly, using an LLM where deterministic tools are enough, retrying without evidence, and rebuilding state that could have been persisted.

LLM Cost Router is designed to route each task through the smallest sufficient combination of:

- context
- deterministic tools
- reasoning depth
- evidence
- retries

The product metric is not simply "fewer tokens." The target is **lower inference cost per accepted result without silently reducing quality**.

## Product architecture

This repository is the **public product surface and evidence layer**. It will contain:

- product documentation
- installation and usage guidance
- reproducible public benchmark methodology
- benchmark results safe for publication
- changelog and release information
- commercial release / purchase information

The proprietary routing and optimization implementation is maintained in a separate private core repository.

## What we measure

Where the underlying platform exposes the data, benchmarks may include:

- accepted-task success rate
- input/output usage
- files read and re-read
- tool calls
- retries
- human interventions
- wall-clock completion time
- usage or cost per accepted result
- tasks completed before a usage-limit reset

A reduction claim is considered useful only when the acceptance criteria and quality gate are held constant.

## Status

**V0 product foundation / dogfood.**

The first milestone is a controlled comparison between an existing optimized workflow and the same workflow with LLM Cost Router enabled. Public claims will follow reproducible evidence rather than estimates.

## Commercial / license notice

This is a public repository, not an open-source grant. No license to copy, modify, redistribute, or commercially use proprietary material is granted unless a specific file or release explicitly states otherwise.
