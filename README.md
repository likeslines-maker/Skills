# Skills

A collection of skills for AI agents. Each skill is a self-contained folder with a `SKILL.md` entry point, a human-readable `README.md`, and an optional `references` folder.

## Available skills

| Skill | Description | Languages |
| --- | --- | --- |
| three-dimensional-logic | Three-valued logic (T, F, N) through three local contexts (TF, TN, FN). Helps an agent preserve context, distinguish a global value from its local role, compare aspects of an ambiguous task, and coordinate reports from several agents without premature merging. | EN, RU |

## Repository layout

- `README.md` — this file (index)
- `LICENSE`
- `three-dimensional-logic/` — one skill, one folder
  - `SKILL.md` — entry point for the agent (YAML frontmatter + body)
  - `README.md` — human-readable description of the skill
  - `references/` — long-form docs, loaded on demand
  - skill_3_logic_RU.md — Russian instructions
  - skill_3_logic_EN.md — English instructions


