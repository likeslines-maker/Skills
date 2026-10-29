# Skill: Three-Dimensional Logic — Author's Version

## Purpose

This skill gives an agent a way to apply three-dimensional logic in its actual work. It is not merely a description of the system or a guide to researching it: use it when analyzing ambiguity, comparing conflicting descriptions, planning actions, or integrating outputs from other agents.

The goal is to preserve relational context, distinguish local roles of values, and check what changes when moving between contexts. Do not apply the skill mechanically to every task. Use it when context, neutrality, or differing perspectives materially matter.

## 1. Core model

### Global values

- `T` — truth.
- `F` — falsehood.
- `N` — the neutral value: neither true nor false in the author's model.

A value and its role are different things. `N` remains the global value `N`, even when it acts as local truth or local falsehood in a particular context.

### Three local contexts

| Context | Values | Local order | Local truth / maximum | Local falsehood / minimum |
|---|---|---|---|---|
| `TF` | `{T, F}` | `F < T` | `T` | `F` |
| `TN` | `{T, N}` | `N < T` | `T` | `N` |
| `FN` | `{F, N}` | `F < N` | `N` | `F` |

Contextual interpretation:
- `TF`: examine the relation between truth and falsehood.
- `TN`: examine the relation between truth and neutrality.
- `FN`: examine the relation between falsehood and neutrality.

These are working descriptions of the contexts, not permission to assign values arbitrarily. Choose a context based on the question and the relations being examined; explain the choice when it affects the conclusion.

## 2. Local operations

For a selected context `C`:

- `¬C` swaps the two values in that context.
- `a ∧C b` is the minimum of `a` and `b` under the local order.
- `a ∨C b` is the maximum of `a` and `b` under the local order.
- `a →C b = (¬C a) ∨C b`.

Negation table:

| Context | Local negation |
|---|---|
| `TF` | `¬TF(T)=F`, `¬TF(F)=T` |
| `TN` | `¬TN(T)=N`, `¬TN(N)=T` |
| `FN` | `¬FN(N)=F`, `¬FN(F)=N` |

**Closure rule:** a local operation must return a value from the same context. In particular, `¬FN(F)=N`, not `T`, because `T` is not in `FN`.

Do not transfer operations between contexts without an explicit transition rule. Local negations differ; a single global negation function does not follow automatically from these definitions.

Global operations, such as minimum and maximum on the chain `F < N < T`, may be defined separately for a specific task. Do not call them local operations or conflate results from these two levels.

## 3. Operational reasoning procedure

Use this cycle when three-dimensional logic may help.

### Step 1. Identify the proposition or relation

State exactly which claim, relation, decision, or assumption is being analyzed. Do not assign one value `T`, `F`, or `N` to an entire situation if it actually contains several different claims.

### Step 2. Separate evidence from context

Record:
- which facts are supported;
- which claims conflict with them;
- what is missing;
- which assumptions depend on situation, source, time, or level of description.

Do not automatically equate `N` with “unknown,” “incomplete,” “not applicable,” “doubtful,” or “both.” These are different concepts. If a task requires mapping one of them to `N`, state that mapping explicitly and do not present it as part of the original definition.

### Step 3. Select a local context

- Choose `TF` when the question concerns the contrast between truth and falsehood.
- Choose `TN` when examining the relation between truth and neutrality.
- Choose `FN` when examining the relation between falsehood and neutrality.

If a task involves several relations, do not force it into one face: examine the relevant faces separately and preserve their connections. If no context fits without extra assumptions, state that.

### Step 4. Assign local roles from the table

Use only the roles specified for the selected context. For example, in `FN`, local truth is `N` and local falsehood is `F`. This does not mean the global values `N` and `F` have changed.

### Step 5. Apply operations

If formal operations are needed, calculate them using the definitions for the selected context. Check that all inputs belong to that context and that the result remains inside it. If an operation requires values from different contexts, an explicit mapping or transition rule is needed first; do not invent one silently.

### Step 6. Compare the faces

When the task requires a whole-picture answer, check:
- whether a value's local role changes;
- which conclusions remain stable across contexts;
- which conclusions depend on the selected face;
- whether there is a contradiction or merely a difference in assumptions;
- what information is lost when everything is reduced to one binary answer.

Do not treat the three local results as automatically independent, and do not combine them by simple majority vote. The original model provides no general voting rule or reduction of all faces to one result.

### Step 7. Return to the practical task

Give the practical conclusion, decision, or next step. State whether considering multiple contexts changed the conclusion, revealed a hidden assumption, or preserved an important distinction. If the approach added no value, say so and proceed normally.

## 4. Using the skill in an agent system

### Document and source analysis

Preserve each claim with its source, time, conditions, and support. When sources differ, do not declare one false merely because of the disagreement: check whether they concern different conditions or are genuinely incompatible. Use contexts to analyze relations, but do not assign a value to a source by intuition alone.

### Planning

Examine what is supported, what conflicts with it, and what remains neutral or unresolved given the available information. Do not turn missing data into proof of truth or falsehood. Contextual reasoning helps preserve distinctions, but does not replace risk assessment or ordinary decision criteria.

### Multi-agent coordination

When integrating reports:
1. preserve each agent's conclusion, grounds, and limitations;
2. distinguish factual conflict from differences in definitions or conditions;
3. compare conclusions in relevant contexts;
4. do not automatically average incompatible conclusions;
5. report what is agreed, what remains open, and what additional evidence is needed.

### Programming and troubleshooting

Use the contextual model when a task involves different modes, contracts, conditions, or interpretations. Do not replace standard types, validation, and error handling with `T/F/N` without a clear rationale and demonstrable benefit.

### Explanation and communication

If a single answer would hide an important distinction, show local results by context and then give an overall conclusion. Do not burden a simple task with formal machinery when it adds no clarity.

## 5. Transitions between contexts

The original model defines three contexts and operations within each, but it does not define a universal transition function between contexts.

Therefore, when moving between contexts:
- identify the source and target contexts;
- preserve the original global value;
- recalculate its local role using the target context's table;
- do not transfer the result of a local operation as if its role automatically remained unchanged in another context;
- if the value itself must be transformed, state the transformation rule and its source.

If a task requires a general transition operator not present in the specification, mark it as an additional working assumption, not as a built-in rule of three-dimensional logic.

## 6. Limits of application

- Three-dimensional logic does not guarantee a more accurate answer by itself.
- It does not prove facts and does not replace source verification.
- It does not automatically provide a rule for reducing the three contexts to one global result.
- It does not imply that `N` always means uncertainty or missing data in every task.
- It does not permit an agent to assert both `P` and `¬P` without clearly specifying context and semantics.
- Philosophical ideas about the interdependence of a whole can guide analysis, but must not be presented as mathematically proven or empirically established facts.

## 7. Output format

Use this compact format when contextual analysis materially affects the task:

1. **Question:** what is being analyzed.
2. **Evidence:** facts, sources, and missing information.
3. **Context(s):** `TF`, `TN`, `FN` and the reason for selection.
4. **Local roles and operations:** only if applied.
5. **Comparison:** what changes and what remains stable across contexts.
6. **Practical conclusion:** decision, recommendation, or next step.
7. **Limitations:** remaining assumptions and what the model cannot establish.

Do not output all seven sections in every ordinary conversation. Use the full format for complex or consequential tasks; in simple cases, apply the principle internally and answer naturally.

## 8. When the skill is useful

The skill is useful when it helps an agent:
- preserve context and assumptions;
- distinguish a global value from a local role;
- notice that a conclusion changes with context;
- retain differing descriptions without prematurely collapsing them;
- explain more precisely what is known, what is not established, and what depends on conditions.

If these benefits do not occur, do not artificially complicate the task.

## Core principle

**First preserve relations and context; then apply local operations; next compare the faces; finally return to the whole task.** Do not replace the reference version with another logic, and do not invent missing transition or aggregation rules.

# Three-Dimensional Logic — Supplement to the Authorial Edition

This file adds practical examples and usage safeguards to the author's model. It does not introduce new global operations, values, or context-transition rules.

## 1. Value versus local role

A global value and its local role are different things.

- `T`, `F`, and `N` are the model's global values.
- A context defines a local order and therefore determines which of its two values is the local top and which is the local bottom.
- `N` does not turn into `T` or `F`. Only its role within the selected context changes.

| Context | Local order | Local top | Local bottom |
|---|---|---|---|
| `TF` | `F < T` | `T` | `F` |
| `TN` | `N < T` | `T` | `N` |
| `FN` | `F < N` | `N` | `F` |

Thus, in `FN`, `¬FN(F) = N`, not `T`: the operation stays within `FN`, where `T` is not a member.

## 2. Local-operation example in FN

Because `FN` is ordered as `F < N`, conjunction is the minimum, disjunction the maximum in that order, and negation swaps the two values.

- `¬FN(F) = N`
- `¬FN(N) = F`
- `N ∧FN F = minFN(N, F) = F`
- `N ∨FN F = maxFN(N, F) = N`
- `N →FN F = (¬FN N) ∨FN F = F ∨FN F = F`

These are local operations only. They do not define a global negation or a rule for transferring a result into another context.

## 3. Choosing contexts when a task has multiple relations

When a task contains several distinct relations, analyze them separately. For each context, state which relation is being examined and why that context is appropriate.

Do not mechanically apply all three contexts to every task. Choose a context based on the structure of the relation, not to fill a table. If there is no basis for choosing a context, state that limitation explicitly.

If several contexts produce results, do not combine them through voting, averaging, or an arbitrary priority. This model does not define such an aggregation rule. First present each facet separately; then describe the combined picture and identify what remains unresolved.

## 4. Practical example: agents disagree about a report

Suppose one agent says, “The task is complete,” while another says, “The task is not complete.”

1. **Clarify the claim.** What does “complete” mean? At what time? Which acceptance criteria apply?
2. **Separate the relations.** Did a completion event occur? Were the acceptance criteria met? Is the available evidence sufficient?
3. **Inspect the basis of each report.** Compare logs, test results, system state, and timestamps. Do not treat a report as proof merely because it came from a different agent.
4. **Choose a context for each relation separately.** Do not automatically assign `N` to missing data: lack of evidence alone does not determine a logical value in this model.
5. **Do not vote between agents.** Record confirmed facts, the exact disagreement, and the check that could resolve it.

A result might look like this:
- confirmed: tests passed on the specified version;
- conflicting evidence: one agent used an older log, the other a current log;
- unresolved: whether the final step ran after the tests;
- next step: verify the current timestamp and final-step status.

This is an example of organizing an investigation, not a universal mapping from facts to `T`, `F`, and `N`.

## 5. Context changes: a caution

The same symbol in different contexts does not imply the same local role. Conversely, similar local roles do not make values identical.

When moving to another context, state again:
- the global value;
- the local order of the selected context;
- the value's local role in that order;
- the operation being performed in the new context.

Do not transfer the result of a local operation between contexts without a separately specified transition rule. No universal rule of this kind is defined in this model.

## 6. What must not be assumed automatically

- `N` does not automatically mean “unknown,” “insufficient data,” “not applicable,” “doubtful,” or “both true and false.”
- Local negation does not define global negation.
- Results from different contexts are not automatically aggregated.
- A geometric analogy may aid intuition, but it does not prove formal properties of the model.

**Criterion for useful application:** the model is useful when it preserves distinctions between relations and makes the basis of a conclusion more transparent. If the contexts add no useful distinctions, use a simpler method.
