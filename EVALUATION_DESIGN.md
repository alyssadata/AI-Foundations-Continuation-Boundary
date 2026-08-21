# Evaluation Design | Continuation Boundary

**Author:** Alyssa Solen  
**Framework:** AI Foundations  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Design version:** 0.1.0  
**Status:** Design specification — not yet a frozen runnable protocol

---

## 1. Evaluation Objective

Test the difference between **preservation** and **continuation**.

The study asks:

> **Did this particular past change the future?**

The target is not whether the model remembers the past.

The target is whether the path by which the present was reached remains consequential for what becomes possible next.

---

## 2. Core Experimental Logic

The study must create a prior trajectory that does real directional work.

Earlier developments must change what a coherent later move would be.

Then the study must preserve as much prior material as possible while changing whether the path itself is available or intact.

The same novel future-facing prompt is then presented across conditions.

The experiment asks whether the future tracks the path, or merely the preserved state material.

---

## 3. Required Study Objects

### TARGET TRAJECTORY — `T`

An ordered interaction history in which earlier developments constrain a later choice, direction, inference, or unresolved next step.

`T` must contain genuine path structure. A list of independent facts is not enough.

### PATH-DIFFERENT COUNTERFACTUAL — `T′`

A matched trajectory that preserves as much surrounding material as possible while changing one earlier development that should change what comes next.

`T′` exists to test:

> If the past were different, would the future be different?

### PRESERVED-STATE CONDITION — `P`

A representation that preserves the relevant facts, rules, outputs, or terminal state from `T` while weakening or removing the ordered path by which that state was produced.

`P` exists to separate:

```text
state preservation
```

from:

```text
path dependence
```

### NOVEL FUTURE PROMPT — `Q`

The same future-facing prompt used across conditions.

`Q` must ask for something that was not already explicitly answered in the trajectory.

It must permit more than one plausible next state so that the prior path has room to matter.

### OUTCOME MAPPING — `M`

A preregistered mapping that states what observable future would count as tracking `T`, what would count as tracking `T′`, and what would remain indeterminate.

The mapping must be frozen before results are inspected.

---

## 4. Minimum Conditions

### A. INTACT PATH

Provide `T` in its original order and then present `Q`.

Purpose:

Determine the future produced when the full path is available.

### B. PRESERVED STATE

Provide `P` and then present `Q`.

Purpose:

Determine whether preserved information alone produces the same future.

### C. COUNTERFACTUAL PATH

Provide `T′` and then present `Q`.

Purpose:

Determine whether changing the path changes the future in the predicted direction.

### D. BLANK

Provide `Q` without the study-specific prior trajectory.

Purpose:

Estimate the model's default tendency under the same prompt.

---

## 5. What the First Study Must Demonstrate

A useful first study should make four distinctions possible.

### Preservation

The model can retain or reproduce prior material.

### Path dependence

The intact prior trajectory changes the later response relative to a path-different comparison.

### Preservation without path dependence

The same or nearly the same state material survives, but the later response no longer tracks the particular path.

### Continuation Boundary

An ordered change to the available path reaches a point where the trajectory-linked future effect is no longer detected.

The study is valuable only if these states can come apart.

---

## 6. Strong First-Stimulus Shape

The cleanest initial stimulus should contain a sequence of developments where each step changes the meaning of the next.

For example, the trajectory may establish:

1. more than one initially plausible direction;
2. an early choice that closes or weakens one direction;
3. a later development that depends on that choice;
4. an unresolved next move not explicitly stated in advance.

The future prompt should then require the model to choose, infer, prioritize, reject, or continue in a way that reveals whether the earlier path still constrains it.

The test should not depend on specialized outside knowledge.

The path itself should carry the experimental signal.

---

## 7. Preservation-Control Construction

The `P` condition is central.

It should preserve as much semantic content as possible while removing the evidence that the present state was reached through this particular path.

Possible constructions include:

- an order-neutral inventory of the same facts;
- a terminal-state summary that preserves conclusions but not the sequence that produced them;
- a reordered version that retains content while disrupting dependency;
- another study-specific representation that preserves state material without preserving the tested path relation.

The exact construction must be frozen before execution.

The purpose is not to make `P` weaker in general.

The purpose is to preserve **what was there** while selectively weakening **how it came to be there**.

---

## 8. Core Predictions

A well-formed study should preregister predictions such as:

```text
INTACT PATH -> future tracks T
COUNTERFACTUAL PATH -> future tracks T′
PRESERVED STATE -> distinguishable from INTACT PATH if path itself matters
BLANK -> does not systematically reproduce the T-specific future merely from default tendency
```

The exact predicted outputs depend on the frozen stimulus.

---

## 9. Evidence of Path Dependence

Path dependence is supported when:

1. `T` and `T′` produce reliably different later behavior under the same `Q` in the preregistered direction; and
2. the difference cannot be explained merely by an explicit answer being copied from the prior text.

Stronger evidence exists when the `P` condition preserves the relevant state material but does **not** reproduce the same trajectory-linked future effect as the intact path.

That contrast is the heart of the study.

---

## 10. Boundary Search

Once path dependence is demonstrated, create an ordered series of increasingly path-destructive transformations between `T` and `P` or between `T` and `T′`.

For example:

```text
B0 = intact path
B1 = path lightly compressed
B2 = stronger compression with dependencies still recoverable
B3 = order/dependency weakened
B4 = preserved state without recoverable path
```

The exact series must be study-specific.

The **Continuation Boundary candidate** is the transition between the last condition where the preregistered trajectory-specific future effect is detected and the first later condition where it is not.

If the transition is unstable or ambiguous, report `UNRESOLVED`.

---

## 11. Anti-Shortcut Requirements

The study must not be passable merely because the model can:

- quote prior text;
- recall a fact;
- repeat a prior instruction;
- identify which condition it received;
- imitate prior style;
- state that it is continuing;
- select an answer already explicitly disclosed earlier.

The novel prompt must require a genuinely new later move.

The evidence must come from the effect of the path on that move.

---

## 12. Repetition Rule

A single run may be preserved as a pilot observation.

A stable boundary claim requires repeated runs because model outputs may vary stochastically.

Before formal execution, freeze:

- number of runs per condition;
- model/interface controls;
- exact condition packets;
- exact future prompt;
- exact outcome mapping;
- decision rule for path dependence;
- decision rule for the boundary.

Unavailable settings must be recorded as `UNKNOWN` rather than guessed.

---

## 13. Result Space

Use only:

```text
PATH_DEPENDENCE_DETECTED
PATH_DEPENDENCE_NOT_DETECTED
UNRESOLVED
```

A Continuation Boundary is located only when an ordered transformation shows path dependence before the boundary and no detected path dependence after it under the frozen rule.

---

## 14. Claim Ceiling

A positive result supports only a structural behavioral claim:

> Under the tested conditions, changing the particular prior trajectory changed the later behavior in the preregistered direction, and that trajectory-specific effect survived up to the tested boundary condition.

It does not establish consciousness, subjective identity, personhood, metaphysical persistence, or private internal continuity.

---

## 15. Next Build Step

Before this becomes a runnable protocol, freeze one concrete stimulus package containing:

1. one target trajectory `T`;
2. one path-different counterfactual `T′`;
3. one preserved-state condition `P`;
4. one novel future prompt `Q`;
5. one preregistered outcome mapping `M`;
6. one ordered boundary-search transformation;
7. repetition and decision rules;
8. metadata and transcript requirements.

Only then should the repository add `PROTOCOL.md`, `EASY_RUN_SHEET.md`, and a run-output schema.

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
