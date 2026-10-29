# Three-Dimensional Logic — A Skill for AI Agents

**Three-dimensional logic** is an approach to reasoning that allows an agent to examine a situation through multiple logical contexts, account for dependencies between elements, and choose a mode of reasoning appropriate to the aspect being considered.

This repository contains a skill intended for practical use by AI agents in information analysis, problem-solving, planning, programming, troubleshooting, and coordination.

## Skill files

The skill is available in two language versions:

- **[`skill_3_logic_RU.md`](skill_3_logic_RU.md)** — Russian version.
- **[`skill_3_logic_EN.md`](skill_3_logic_EN.md)** — English version.

Both files describe the same approach in different languages and are intended for AI-agent systems that support custom instructions or Markdown-based skills.

## What is this skill for?

The skill helps an agent avoid relying on a single interpretation when a situation has several relevant aspects. It can help the agent:

- **Choose a logical context.** Identify which aspect of a task is being examined and which values are permitted in that context.
- **Apply local reasoning rules.** Use logical operations that belong to the selected context.
- **Compare different aspects.** Identify where conclusions agree, differ, or depend on the conditions under consideration.
- **Account for dependencies.** Examine relationships between elements, not just the elements in isolation.
- **Support practical work.** Apply the approach to document analysis, software development, planning, and problem diagnosis.
- **Avoid premature conclusions.** Keep relevant contexts and uncertainty visible instead of forcing a complex situation into a single answer too early.

The skill does not replace domain knowledge, fact-checking, or standard problem-solving methods. It provides an additional structure for reasoning that an agent can use alongside them.

## A brief introduction to three-dimensional logic

The system uses three values:

| Symbol | Meaning |
|---|---|
| `T` | True |
| `F` | False |
| `N` | Neutral, indeterminate, or not unambiguously classifiable as true or false |

Three-dimensionality here means more than simply having three values. The values are considered through **three local logical contexts**:

| Context | Allowed values | Local order |
|---|---|---|
| `TF` | False and True | `F < T` |
| `TN` | True and Neutral | `N < T` |
| `FN` | False and Neutral | `F < N` |

Each context has its own local logical operations. A value must therefore be considered together with the context in which it is used.

For example, `N` retains its identity, but it occupies the bottom position in context `TN` and the top position in context `FN`. This illustrates why a value's role in a particular inference cannot be determined from its symbol alone.

The three contexts can be pictured as separate logical planes, while their relationships form a more spatial structure of reasoning. This geometric picture is a conceptual analogy, not a mathematical proof in itself.

## How an agent uses the skill

A typical workflow is:

1. **Understand the task** and identify the relevant elements, conditions, and dependencies.
2. **Select a logical context** appropriate to the aspect being examined.
3. **Reason locally** using the allowed values and operations of that context.
4. **Compare results** when the task requires more than one context to be considered.
5. **Produce a practical conclusion**, making important conditions, limitations, and uncertainties explicit.

Transitions between contexts are not automatically defined. If a task requires values to be transformed from one context to another, the agent should state the basis for that transition rather than inventing a rule.

## Core principle

**Consider not only a value, but also the context in which it takes on a logical role. Examine individual aspects and their relationships without mixing the local rules of different contexts.**

This principle makes the skill useful for tasks in which one situation has several relevant, interconnected ways of being examined.

## Scope and limitations

In this skill, three-dimensional logic is a formalized approach to organizing reasoning. It does not guarantee that the input data or final conclusion is correct, and it should not replace empirical verification, mathematical proof, or subject-matter expertise.

When using the skill, an agent should distinguish between:

- formal rules of the system;
- interpretation of a particular task;
- assumptions about dependencies;
- analogies and philosophical generalizations.

Keeping these categories separate helps the agent apply the approach consistently without presenting interpretations as established facts.

## Usage

To use the skill, select the file for the desired language:

- `skill_3_logic_RU.md` — Russian instructions;
- `skill_3_logic_EN.md` — English instructions.

Make sure your agent system supports Markdown instruction files and connect the selected file according to that system's configuration.

---

**Three-Dimensional Logic** is a way to structure reasoning through three logical values, three local contexts, and an analysis of the relationships between them.
path.write_text(content, encoding="utf-8")
print(f"Created: {path} ({path.stat().st_size} bytes)")
