---
name: error-autopsy
description: >-
  Diagnoses a concrete bug or failure with a short, evidence-led sequence:
  symptom, two or three ranked hypotheses, the smallest useful check, then a
  one-line root cause and fix. Use for failed runs, tests, stack traces, CI
  failures, broken installs, unexpected output, or “this broke and I do not know
  why.” Do not use for green-path feature work or weekly synthesis of several
  incidents.
---

# Error autopsy

Help the user understand one specific failure without turning the response into a long incident report or broad code rewrite.

## Steps

1. Restate what failed and the strongest observable signal, such as the error text, exit code, failing test, or unexpected result. Ask for missing information only when diagnosis is blocked.
2. List two or three hypotheses in order of likelihood. Tie each one to the symptom or a recent change; do not list unrelated possibilities.
3. Choose one smallest next check that can distinguish the leading hypothesis. Give a concrete command, file to inspect, or reproduction step, and say what result would confirm or weaken it.
4. Once evidence is available, state the root cause in one line and the fix or next action in one line. If evidence is not enough, label the cause as unknown and report the next check instead of guessing.
5. Optionally add one reusable learning tag, such as “Next time, check X before Y.”

## Output

### Symptom
- What failed:
- Observable signal:

### Hypotheses (ranked)
1. …
2. …
3. …

### Smallest check
- Do this:
- What the result would tell us:

### Root cause
- …

### Fix or next action
- …

### Learning tag (optional)
- …

## Boundaries

- Do not claim a root cause before evidence supports it.
- Do not recommend a shotgun list of fixes or redesign the codebase.
- Keep the analysis to one failure at a time.
- Redact secrets and personal data from examples.
- If the user only wants a patch, keep this structure brief while making the reasoning visible.
