# Evaluation Design | Continuation Boundary

**Author:** Alyssa Solen  
**Framework:** AI Foundations  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Design version:** 0.1.0  
**Status:** Design specification — not yet a frozen runnable protocol

---

## 1. Evaluation Objective

Locate the point at which a controlled perturbation to a prior trajectory causes its trajectory-specific effect on a later state to disappear.

The evaluation is not a recall test.

The test target is:

> **Does changing the prior trajectory change the future in the direction predicted by that trajectory?**

---

## 2. Required Study Objects

Every study built from this design must freeze the following before execution.

### TARGET TRAJECTORY — `T`

The ordered prior history whose continuation is being tested.

### MATCHED COUNTERFACTUAL — `T′`

A history matched as closely as possible to `T` except for the specific trajectory-critical relation under test.

### TRAJECTORY-CRITICAL RELATION — `R`

The relation hypothesized to matter for continuation.

Examples may include order, dependency, source relation, prior selection, unresolved direction, or another repository-specific relation.

The study must state why `R` should produce a different future under `T` and `T′`.

### NOVEL CONTINUATION PROMPT — `Q`

The same future-facing prompt presented across conditions.

`Q` must not merely ask the model to recall, quote, summarize, or identify the earlier trajectory.

It must allow more than one plausible next state so that prior trajectory can make a discriminable difference.

### OBSERVABLE OUTCOME MAPPING — `M`

A mapping defined before execution that identifies which observable outputs count as tracking `T`, tracking `T′`, or remaining indeterminate.

Do not derive `M` after seeing results.

---

## 3. Minimum Conditions

A boundary study requires at least the following conditions.

### A. INTACT

Provide `T` without the tested relation being disrupted.

Purpose: establish the trajectory-specific effect under the strongest available continuation condition.

### B. INCIDENTAL-PERTURBATION

Alter material that is explicitly classified in advance as noncritical while preserving `R`.

Purpose: test whether continuation survives irrelevant change.

### C. RELATION-DISRUPTED

Preserve as much of the surrounding material as possible while removing, reversing, substituting, or severing `R`.

Purpose: test whether `R` is actually constitutive of the trajectory effect.

### D. COUNTERFACTUAL

Provide `T′`.

Purpose: establish the competing future predicted by a materially different trajectory.

### E. BLANK

Provide `Q` without the study-specific prior trajectory.

Purpose: estimate the model's unconditioned or default tendency under the same test prompt.

---

## 4. Perturbation Ladder

When the study seeks a boundary rather than a single contrast, create an ordered ladder of perturbations.

Example structure:

```text
P0 = intact trajectory
P1 = superficial reduction
P2 = stronger compression with R preserved
P3 = partial weakening of R
P4 = direct disruption of R
P5 = counterfactual substitution of R
```

The exact ladder is study-specific.

A perturbation ladder must change one declared dimension at a time whenever feasible. Do not combine multiple uncontrolled changes and then attribute the result to a single boundary condition.

---

## 5. Experimental Control Rule

Across compared conditions, hold constant everything that is not intentionally manipulated whenever the interface allows it, including:

- model and version;
- system/developer instructions;
- tools;
- memory configuration;
- sampling settings;
- test prompt;
- output format;
- operator behavior.

Record unavailable controls as `UNKNOWN` rather than assuming equivalence.

---

## 6. Repetition Rule

A single response may be preserved as a pilot observation, but it is not sufficient to locate a stable Continuation Boundary in a stochastic model.

Boundary claims require repeated runs across the relevant conditions.

The study must preregister:

- number of runs per condition;
- allowed randomization, if any;
- the outcome mapping;
- the criterion for distinguishing a trajectory effect from controls;
- the rule for assigning boundary status.

This repository does not impose one universal statistical threshold. The threshold must fit the study design and be frozen before results are examined.

---

## 7. Core Measurement

For each condition, measure how often the resulting later state tracks the direction predicted by `T`, the direction predicted by `T′`, or neither.

A study may define a trajectory-effect measure such as:

```text
Trajectory Effect = rate(output tracks T | target condition)
                  - rate(output tracks T | matched counterfactual/control)
```

The exact metric may vary, but it must preserve the same logical test:

> **Does the target trajectory make a discriminable difference to the future compared with a materially matched alternative?**

---

## 8. Boundary Rule

For each perturbation level:

```text
if preregistered trajectory effect remains distinguishable from relevant controls:
    STATUS = INSIDE_BOUNDARY
elif preregistered trajectory effect is no longer distinguishable from relevant controls:
    STATUS = CROSSED_BOUNDARY
else:
    STATUS = UNRESOLVED
```

For an ordered perturbation ladder, the empirical boundary candidate is the transition between the last level classified `INSIDE_BOUNDARY` and the first subsequent level classified `CROSSED_BOUNDARY`.

If the statuses do not form a stable transition, report the boundary as `UNRESOLVED` rather than forcing a threshold.

---

## 9. Anti-Shortcut Requirements

The test must not be passable merely because the model can:

- quote the trajectory;
- recall a fact from it;
- identify which condition it received;
- repeat an explicit prior instruction;
- mimic prior language or style;
- state that it feels continuous;
- choose an answer explicitly disclosed earlier;
- infer the experimenter's desired result from condition labels.

Condition labels should therefore not be exposed to the model when avoidable.

The continuation prompt should require a genuinely later decision, inference, prioritization, or direction whose outcome can differ because of the trajectory.

---

## 10. Falsifying Pattern

A proposed trajectory-critical relation `R` is weakened or falsified as constitutive evidence if disrupting `R` produces no meaningful loss of the trajectory effect while the study remains otherwise discriminating.

Likewise, if `T`, `T′`, and `BLANK` all produce materially the same future distribution, the study has not demonstrated trajectory dependence.

The correct result in that case is not continuation.

It is either:

- no detected trajectory effect; or
- unresolved measurement.

---

## 11. What a Positive Result Means

A positive result supports only this form of claim:

> Under the tested conditions, the later behavior remained detectably dependent on specified structure from the prior trajectory through perturbation level `Pn`, and that dependence was no longer detected beyond the preregistered boundary criterion.

It does not establish a universal continuity law.

---

## 12. Next Build Step

Before this design becomes a runnable protocol, freeze one concrete study package containing:

1. `T`;
2. `T′`;
3. one declared relation `R`;
4. one novel prompt `Q`;
5. an exact perturbation ladder;
6. an exact outcome mapping;
7. repetition and decision rules;
8. metadata and transcript requirements.

Only then should this repository add an operator-facing `PROTOCOL.md`, `EASY_RUN_SHEET.md`, and run-output schema.

---

**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum
