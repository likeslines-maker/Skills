---
name: three-dimensional-logic
description: Applies three-valued logic (T, F, N) through three local contexts (TF, TN, FN) to preserve context, distinguish global values from local roles, and compare aspects of ambiguous tasks. Use when a situation admits multiple interpretations, when sources disagree, when planning under uncertainty, or when coordinating reports from several agents.
---

# Three-Dimensional Logic

## When to use
Ambiguous analysis, conflicting sources, planning under incomplete information, merging agent reports, diagnosing multi-mode systems. Do not apply mechanically to every task.

## Model
Global values: `T` (truth), `F` (falsehood), `N` (neutral — neither, in this model).
A value's global identity is distinct from its local role.

| Context | Values | Order | Local truth | Local falsehood |
|---|---|---|---|---|
| `TF` | T, F | F < T | T | F |
| `TN` | T, N | N < T | T | N |
| `FN` | F, N | F < N | N | F |

Local operations in context `C`: `¬C` swaps the two values; `∧C` = min, `∨C` = max by local order; `a →C b = (¬C a) ∨C b`. Operations are closed within their context.

## Workflow
1. State the exact claim/relation/decision under analysis.
2. Separate confirmed facts, contradictions, missing data, and context-dependent premises.
3. Choose context (`TF`/`TN`/`FN`) by the relation being examined; state why.
4. Assign local roles from the table.
5. Compute only with operations of the chosen context; keep results inside it.
6. Compare aspects: what changes, what holds, what depends on the facet.
7. Return to the practical task; if the approach added nothing, say so.

## Rules
- Do not transfer operations between contexts without an explicit transition rule.
- Do not equate `N` automatically with "unknown", "incomplete", or "both".
- Do not merge the three facets by majority vote — the model has no such rule.
- Distinguish formal rules, task interpretation, assumptions, and analogies.


## References

- Full authorial edition (RU): `references/skill_3_logic_RU.md`
- Full authorial edition (EN): `references/skill_3_logic_EN.md`
