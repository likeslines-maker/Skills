Skills

A collection of skills for AI agents. Each skill is a self-contained folder with a SKILL.md entry point, a human-readable README.md, and an optional references folder.
Available skills
Skill	Description	Languages
three-dimensional-logic	Three-valued logic (T, F, N) through three local contexts (TF, TN, FN). Helps an agent preserve context, distinguish a global value from its local role, compare aspects of an ambiguous task, and coordinate reports from several agents without premature merging.	EN, RU
Repository layout

    README.md — this file (index)

    LICENSE

    three-dimensional-logic/ — one skill, one folder

        SKILL.md — entry point for the agent (YAML frontmatter + body)

        README.md — human-readable description of the skill

        references/ — long-form docs, loaded on demand

            three-dimensional-logic.ru.md

            three-dimensional-logic.en.md

Installation

Claude Code / Claude.ai (and compatible platforms): copy the skill folder into your skills directory. Clone the repository, then copy the folder three-dimensional-logic into your local skills directory (for Claude Code this is the .claude/skills directory in your home folder).

Other agent systems: attach three-dimensional-logic/SKILL.md (and, if the platform supports it, the references folder) according to that system's rules for custom instructions or skills.

Manual use: paste the contents of references/three-dimensional-logic.en.md (or .ru.md) into your agent's system prompt or custom instructions.
Adding a new skill

    Create a folder my-skill/ with SKILL.md (frontmatter: name, description) and README.md.

    Put long-form material in my-skill/references/.

    Make sure name in the frontmatter matches the folder name (lowercase, hyphens).

    Add a row to the table above.
