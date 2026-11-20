# Agent Skill Evaluation

Agent Skill Eval is a planned tool for testing which instructions in an
AI agent's SKILL.md improve its work. It compares models on the same
tasks and shows the effect of removing individual instructions.

## How it works

1. Import a SKILL.md. The runner extracts the steps from the skill,
   and you select which ones to test.
2. Run the same task with the full skill and again with one selected
   step removed. Keep the model version, inputs, tools, output schema,
   and grading rules fixed between the two runs.
3. Compare the results. The report shows evidence of whether the model
   performed each step and how removing the instruction affected the
   final deliverable, latency, and token usage.

## First benchmark

The first benchmark uses 12 rental invoices with known answers. Four
are correct, six contain one error, and two contain multiple errors.
Each fixture has expected line items, totals, and discrepancies.

The first comparison uses pinned Claude Sonnet and GPT versions, with
three runs per fixture per condition. The runner checks exact VND
amounts, missed discrepancies, and false positives automatically.
An AI reviewer can score explanation quality against a rubric, cite
the evidence, and let users review or override its score.

Local model support is planned. A smaller model might expose an
instruction that relies on unstated assumptions. A stronger model
might reliably do the same work after that instruction is removed.
The report shows the evidence for each model on the tasks tested.

## Devin workflow

If approved, Devin's first PR will implement the 12 fixtures and their
answer keys for me to review. The next PRs will add the runner, model
adapters, and comparison report. In CI, the runner will compare skill
changes against the approved baseline. Devin can reproduce a flagged
regression and propose a fix or a new fixture in a PR.

## Status

The benchmark is designed. Implementation and repository setup are
pending. The project will be hosted on GitHub.
