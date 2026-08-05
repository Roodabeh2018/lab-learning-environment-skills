# Reflection Skills

> **How you'll submit this lab**
>
> This repo is your lab. Fork it, do the work described below in your fork, then open a pull
> request back into this repository. An AI reviewer will check your PR against `rubric.md` and
> leave feedback directly on the PR. See `README.md` for the full workflow.

## Learning Goal

You will author three small reflection skills for your coding assistant and prove each one can run once on a real or plausible learning moment.

## Working Context

Skills are not only for shipping code. They can encode **how you learn**: short retros after a task, structured digests when something breaks, and a weekly review that turns scattered notes into deliberate practice.

You will turn three short briefs into installable skills in **your** assistant environment (Codex, Claude Code, Cursor, or another client that supports skills). Do not leave the finished skills living only inside course materials. Copy or recreate them where your agent actually loads skills.

## Proof of Learning

Submit one `lab_proof.md` with:

- Paths (or screenshots) showing the three skills installed in your agent skills location
- One example output from each skill (anonymized is fine)
- One sentence on what you changed in a `description` so the skill would actually trigger

## Pseudocode

```text
INPUT: three skill briefs (post-task retro, error autopsy, weekly review)
DECIDE: where your client loads skills and how description should trigger
BUILD: create three skill folders with SKILL.md from each brief
VERIFY: run each skill once and capture output
EXPLAIN: what you would tighten next in description or steps
```

## Prompt Discipline

Use AI for review, debugging, or critique. Do not ask it to produce the final skill bodies for you.

```text
Role: Skills authoring reviewer
Task: Challenge my draft skill before I install it.
Inputs: name, description, steps, and intended trigger situations.
Constraints: Do not write the SKILL.md for me. Flag vague triggers, mega-scope, and missing boundaries.
Output format: three trigger risks, two cuts to make, one clearer description line.
Verification: Name a user phrase that should load the skill and one that should not.
```

## Build

### Starting briefs (use these)

Work from these three briefs. Open each before you write the matching `SKILL.md`:

| Skill | Brief |
|-------|--------|
| Post-task retro | [post-task-retro.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/post-task-retro.md) |
| Error autopsy | [error-autopsy.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/error-autopsy.md) |
| Weekly skill review | [weekly-skill-review.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/weekly-skill-review.md) |

Treat the briefs as **intent and steps**, not as the final install path. Your installed skill should be a proper `SKILL.md` (YAML frontmatter + body) in the location your client documents.

---

### Step 1: Choose your stack and create the folder tree

Do: Decide whether you are authoring primarily for **Codex**, **Claude Code**, **Cursor**, or another skills-capable client. Create three skill folders under the location **that client** recommends (for example a user- or repo-level skills directory).

**First concrete action:** Create three folders named to match the briefs, for example:

- `post-task-retro/`
- `error-autopsy/`
- `weekly-skill-review/`

Verify: Empty folders exist in your agent skills location; you know how to refresh or restart so the client rediscovers them.

---

### Step 2: Skill 1 — Post-task retro

Do: Turn [post-task-retro.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/post-task-retro.md) into `post-task-retro/SKILL.md`.

**Frontmatter:** Include at least `name` and `description`. The `description` should fire after finishing a task when someone wants a short learning retro, even if they never say “retro.”

**Body:** Keep the brief’s steps. Aim for a short, structured output the brief describes (a compact retro you can keep in your own notes or log).

**Kick-off test:** Finish a tiny real or fake task, invoke the skill, confirm you get a usable 4-part (or 4-line) retro.

---

### Step 3: Skill 2 — Error autopsy

Do: Turn [error-autopsy.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/error-autopsy.md) into `error-autopsy/SKILL.md`.

**`description`:** Should fire on bugs, failed runs, stack traces, or “this broke and I do not know why.”

**Body:** Keep hypothesis → smallest check → one-liner root cause + fix. The point is a reusable diagnostic pattern, not a long incident novel.

**Kick-off test:** Feed a real or plausible error; confirm the output follows the brief’s steps.

---

### Step 4: Skill 3 — Weekly skill review

Do: Turn [weekly-skill-review.md](https://github.com/ai-consulting-bootcamp/ac-bootcamp-public/blob/main/learning_skills/weekly-skill-review.md) into `weekly-skill-review/SKILL.md`.

**`description`:** Should fire at week’s end, or when someone wants to turn scattered retros/errors into next-week practice.

**Body:** Re-read → cluster themes → pick one deliberate practice focus. Point the agent at whatever notes you actually keep (it does not need a fixed filename).

**Kick-off test:** Paste two or three short fake retros/errors and run the review once.

---

### Step 5: Validate YAML and discovery

Do: Confirm each `SKILL.md` parses as Markdown + YAML frontmatter.

**Checklist:**

- [ ] Three folders each contain one `SKILL.md` in **your** skills location
- [ ] Each file has `name` and `description` under `---` frontmatter
- [ ] Client restarted or refreshed per docs if skills did not appear
- [ ] You did **not** rely on linking into course materials at runtime; the agent loads your installed copies

---

## Definition of done

You are done when:

- [ ] Three installed `SKILL.md` files match the intent of the three briefs
- [ ] You ran at least **one** meaningful test per skill
- [ ] You noted **one** insight about how you learn (private notes are enough)

Optional deliverable: link to a personal repo folder or gist (avoid sensitive journal-like content), or a short note plus screenshot that the skill triggered in your client.

---

## Summary

- Skills can scaffold **how you learn**, not only **what you ship**.
- Start from the three briefs, then install real `SKILL.md` packages where your assistant can find them.
- **`description`** is how your assistant finds these rituals when you need them; iterate with patience.

## Verify

A reviewer can open your `lab_proof.md` and see three installed skills plus one sample output each.

## Explain

Which skill’s `description` was hardest to write so it triggers on the right moments and stays quiet otherwise?

## Submission Sanity Check

Before you submit:

- Keep only files for this lab in the submission
- Name files clearly
- Remove secrets, API keys, tokens, and unrelated data
- Make `lab_proof.md` the entry point for the reviewer

## Optional Stretch

- Add a fourth reflection skill of your own (for example a “prep before asking for help” ritual)
- Tighten one `description` using guidance from [agentskills.io](https://agentskills.io/) / [llms.txt](https://agentskills.io/llms.txt)
