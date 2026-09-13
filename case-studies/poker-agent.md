# A poker decision agent

**A small environment for studying bounded autonomous decisions.**

Agent research prototype · source private · September 2026 snapshot

## The question

How should an agent choose an action when it must obey the environment's rules, handle uncertainty, and stop when execution becomes unreliable?

## What exists

The implementation includes legal-action validation, opponent profiling, strategy decisions, shadow-strategy comparison and promotion checks, and a circuit breaker. The repository has a test suite and CI configuration, although CI covers only part of the available checks.

```text
game state → decision → legal-action check → bounded execution
     ↑                                          ↓
     └──────── observation / stop condition ─────┘

candidate strategy → shadow evaluation → promotion decision
```

## What was checked

The repository's configured offline test command, including its type check and self-test commands, passed in an isolated snapshot during review. No live games, betting, deposits, or trading actions were executed.

## What this does not establish

Passing code checks does not establish strategic superiority, profitability, fairness, or safe operation on an external service. The public value of this project is its control and evaluation design, not a claim of winning money.

## The next useful experiment

Use a deterministic simulator to compare the baseline and candidate policies on held-out seeds. Publish legal-action violations, stop behavior, and outcome variance alongside the average result. Keep the demonstration offline.

[Back to the lab](../README.md)
