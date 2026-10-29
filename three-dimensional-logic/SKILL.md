---
name: three-dimensional-logic
description: Applies the T/F/N model through three local contexts (TF, TN, FN), preserving context and distinguishing global values from local roles. Use when a problem has multiple relational aspects, competing interpretations, or reports that must be compared without inventing an aggregation rule.
---

# Three-Dimensional Logic

Use this skill to keep the context of a claim explicit, analyze relevant aspects separately, and avoid collapsing different relations into one verdict.

## Model

Global values:
- `T` — true
- `F` — false
- `N` — neutral; neither true nor false in this model

Local contexts and their orders:
- `TF`: `F < T`
- `TN`: `N < T`
- `FN`: `F < N`

For a context `C`, its local top is the greatest value in that context and its local bottom is the least:
- `TF`: top `T`, bottom `F`
- `TN`: top `T`, bottom `N`
- `FN`: top `N`, bottom `F`

A value's global identity does not change when its local role changes. In particular, `N` remains `N`; it is the local bottom in `TN` and the local top in `FN`.

## Local operations

Within a selected context `C`:
- `¬C` swaps the two values of that context.
- `a ∧C b = minC(a, b)`.
- `a ∨C b = maxC(a, b)`.
- `a →C b = (¬C a) ∨C b`.

Operations are defined locally and remain within the selected context. Do not apply a result from one context as if it were automatically a result in another.

Example in `FN`, where `F < N`:
- `¬FN(F) = N`
- `N ∧FN F = F`
- `N ∨FN F = N`
- `N →FN F = (¬FN N) ∨FN F = F ∨FN F = F`

The example illustrates local operations only; it does not define a global negation or a rule for moving between contexts.

## Workflow

1. **State the exact claim or question.** Make its subject, scope, time, and criteria explicit.
2. **Identify the relevant relation(s).** Choose `TF`, `TN`, and/or `FN` only when the relationship being examined justifies that context.
3. **Keep facets separate.** Record what each source, agent, or interpretation actually supports.
4. **Operate locally.** Apply negation, conjunction, disjunction, or implication only within a selected context.
5. **Mark evidence and gaps.** Distinguish evidence, contradiction, and missing information. Do not automatically encode missing information as `N`.
6. **Compare results without forced aggregation.** Do not vote, average, or collapse contexts unless a separate aggregation rule has been explicitly defined.
7. **Return to the whole task.** Summarize what is established, what remains unresolved, and what evidence or action would help.

## Example: conflicting agent reports

Two agents report different things about whether a task is complete.

1. Specify the exact completion claim, time, and acceptance criteria.
2. Inspect the evidence each agent used (for example, logs, tests, or a completion marker).
3. Separate distinct questions: whether a completion event occurred, whether the acceptance criteria were met, and whether the available evidence is sufficient.
4. Select a context for each relation only when justified; do not assign `N` merely because one report lacks evidence.
5. Do not decide by majority vote. Report the supported facts, the disagreement, and the next check needed to resolve it.

## Guardrails

- `N` is not automatically “unknown,” “incomplete,” “not applicable,” “doubtful,” or “both true and false.” Use those descriptions only when independently justified.
- Do not invent a transition function between contexts.
- Do not infer a global negation from the local negations.
- A local top/bottom role is not a new global value.
- Do not treat a geometric analogy as a proof of the logical model.
- If a task does not benefit from multiple relational perspectives, use a simpler method.

## Output format

When useful, report:
- **Claim / question**
- **Context(s) and why**
- **Evidence by facet**
- **Local operation(s), if any**
- **What is established**
- **What remains unresolved**
- **Next evidence or action**

Core principle: **Preserve relations and context first; perform local operations second; compare facets only afterward, then return to the whole task.**

## References

- Full Russian authorial edition: `references/skill_3_logic_RU.md`
- Full English authorial edition: `references/skill_3_logic_EN.md`
