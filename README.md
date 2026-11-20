# Agent Skill Evaluation

Agent Skill Eval is a planned tool for evaluating third-party agent skills.
It reads a SKILL.md, identifies its instructions and reasoning requirements,
and tests how much each instruction contributes across models.

## Workflow

1. Import a skill. Extract explicit steps, conditional rules, and output
   requirements. Link each item to its source text. Record dependencies
   between steps and let the user correct the extracted structure.
2. Use representative tasks that exercise the skill's own requirements.
   Include cases where conditional steps should and should not apply.
3. Run each task with the full skill, without the skill, and with one
   selected instruction removed at a time. Use the same grading criteria
   for every variant. Flag removals that break dependent steps.
4. Report, per instruction and model, whether the step was performed,
   how well it was performed, and how its removal affected the final
   deliverable. Attach evidence from outputs and available tool traces.

Use deterministic checks when expected results can be verified in code.
For qualitative outcomes, an AI reviewer proposes a score with evidence.
Users can inspect the evidence and override the score.

## First milestone

Use 12 invoice fixtures to verify that the runner and automated grader
work end to end. Then evaluate a third-party workflow such as AgentKit's
/ak-plan. Start with pinned Claude Sonnet and GPT versions, with local
model support planned.

If approved, Devin will help implement the skill parser, benchmark runner,
model adapters, and comparison report.

## Status

The project is at the design stage. GitHub hosting is planned.
