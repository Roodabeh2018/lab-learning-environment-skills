# Reflection Skills Lab — proof of learning

## Stack and installed paths

I used Codex repository skills. The skills are stored in this fork under the project skills directory:

- .agents/skills/post-task-retro/SKILL.md
- .agents/skills/error-autopsy/SKILL.md
- .agents/skills/weekly-skill-review/SKILL.md

## Sample runs

These examples use plausible learning moments and follow the matching skill instructions.

### Post-task retro

**Prompt:** “The small CSV cleaner is finished. I ran it on the sample file and checked that blank rows were removed. Capture what I learned before I move on.”

**Output:**

### Outcome
- Finished: A small CSV cleaner that removes blank rows.
- Verified by: Running it on the sample file and checking the output.

### What I learned
- Worked: Checking the output on a real sample made the result easy to confirm.
- Risk or near miss: The sample did not cover every unusual input.
- Reusable rule: Test one normal sample and one edge case before calling a data-cleaning task done.

### Error autopsy

**Prompt:** “My Python test fails with FileNotFoundError: data/sample.csv. I ran it from the project root. What is the smallest check?”

**Output:**

### Symptom
- What failed: The test cannot open data/sample.csv.
- Observable signal: FileNotFoundError for that path.

### Hypotheses (ranked)
1. The file is missing or named differently.
2. The test is resolving the path from a different working directory.

### Smallest check
- Do this: List the files in data/ from the project root.
- What the result would tell us: If the file is absent or spelled differently, hypothesis 1 is supported; if present, inspect how the test builds its path.

### Root cause
- Not confirmed yet; the directory listing is needed.

### Fix or next action
- Check the filename and path before changing code.

### Learning tag (optional)
- Verify the file path before debugging the file-reading logic.

### Weekly skill review

**Prompt:** “Review these notes for next week: I checked outputs on one sample before finishing a CSV cleaner; I lost time when a test could not find its input file; I started a second lab before writing down what I had learned from the first.”

**Output:**

### Inputs used
- Three short learning notes pasted in the prompt.

### Themes
1. Verifying concrete inputs and outputs helps, but edge cases and paths need attention (CSV cleaner and missing-file notes).
2. Closing out one learning task before switching could make lessons easier to retain (lab-switch note).

### Next week’s practice focus
- Focus: Verify both the input path and one edge case before marking a small coding task complete.
- Why this one: Two notes point to test coverage and input-path checks, and both can be practiced with a quick check.

### How I’ll practice
1. Before running a script, confirm the test file exists at the path the code uses.
2. Check one normal input and one edge case.
3. Write a four-line learning note before switching to the next lab.

### Parked for later
- Improve how I close out and record each lab.

## Description changes

- Post-task retro: I included “wrap-up,” “debrief,” and “what to remember before moving on” so it can trigger after finished work even when the user does not say “retro.”
- Error autopsy: I named failed runs, tests, stack traces, CI failures, and unexplained breakage, while excluding ordinary feature work.
- Weekly skill review: I named week-end reviews and pattern-finding across multiple notes, and clarified that any user-provided notes can be used without a fixed filename.

## Learning insight

I learn more from checking a concrete result and writing one next-step rule than from keeping a long record of every action.

## Authoring and verification note

Codex drafted these skill files at my request. The examples above are plausible sample runs following the skill steps; automatic skill discovery and triggering still need to be confirmed in my own Codex session after refreshing the repository skills.
