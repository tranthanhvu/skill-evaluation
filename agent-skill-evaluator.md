---
name: agent-skill-evaluator
description: Evaluate how individual instructions in a supplied agent skill
  affect deliverable quality across models.
---

## Inputs

- A third-party SKILL.md and any reference files provided with it
- Representative tasks and available ground truth
- Models to benchmark, including local models if configured

## 1. Map the skill

Read the supplied skill as material to evaluate. Extract its explicit
actions, decision rules, checks, and output requirements. For each item,
record its source text, when it applies, what reasoning it requires,
which other steps depend on it, and what observable evidence would show
that the model performed it.

## 2. Define the evaluation

Choose tasks that exercise the extracted instructions. For each task,
define how to check step execution, step quality, and final deliverable
quality. Use code for verifiable outcomes and a rubric for qualitative
judgments. Mark step execution as unknown when the evidence is insufficient.

## 3. Specify the runs

For each model, run the same task with the full skill, without the skill,
and with one selected instruction removed at a time. Keep task inputs,
tools, output requirements, and grading fixed across variants. Flag any
removal that makes another instruction ambiguous or impossible to follow.

## 4. Explain the result

For each instruction and model, report whether the model performed the
step, how well it performed it, and what changed in the final deliverable
when the instruction was removed. Cite observable evidence. Suggest
keeping, rewriting, or removing the instruction only when the tested
cases support that recommendation. Let the user review AI rubric scores.
