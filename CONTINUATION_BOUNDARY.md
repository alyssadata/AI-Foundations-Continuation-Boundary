# AI Foundations | Continuation Boundary

**Author:** Alyssa Solen  
**Framework:** AI Foundations  
**Source-line:** Alyssa Solen → AI Foundations → Origin | Continuum  
**Version:** 0.1.0  
**Date:** 2026-08-20

---

## 1. Source Question

> **At what point does carrying a prior trajectory forward cease to constitute continuation of that trajectory?**

The question is deeper than whether information, permission, identity labels, memory, or prior outputs remain available.

It asks what must remain **consequential** from the prior trajectory for a later state to still count as continuation of that trajectory.

---

## 2. Core Definitions

### Trajectory

A **trajectory** is an ordered history whose prior states, relations, decisions, constraints, and directional changes can alter the space of plausible later states.

A trajectory is not merely a bag of remembered facts.

### Trajectory-specific structure

**Trajectory-specific structure** is the set of relations in a trajectory that make its future consequences distinguishable from those of a materially different trajectory.

These relations may include order, dependency, source relation, prior selection, unresolved direction, exclusion, commitment, or other study-specific structure.

No single list is assumed to be constitutive in every study.

### Continuation

For purposes of this repository, a later state provides evidence of **continuation** when its production or direction remains counterfactually dependent on trajectory-specific structure from the prior history.

In plain language:

> **This past must still make a difference to this future.**

### Continuation Boundary

**Continuation Boundary** is the point between:

- perturbations after which trajectory-specific dependence remains detectably present; and
- perturbations after which that dependence no longer meets the study's preregistered criterion.

A boundary is therefore not defined by how much text, memory, or surface resemblance survives.

It is defined by whether the **particular prior trajectory remains consequential for what happens next**.

---

## 3. Preservation Is Not Continuation

A system may preserve:

- words;
- facts;
- memory entries;
- labels;
- instructions;
- summaries;
- stylistic patterns;
- prior outputs;

without preserving the trajectory relation that made those materials consequential in the first place.

Preservation asks:

> **Did something from the past survive?**

Continuation asks:

> **Did this particular past continue to constrain the future?**

The Continuation Boundary asks:

> **Which changes can occur before that constraint is no longer detectably present?**

---

## 4. Constitutive and Incidental Change

A study of continuation must distinguish between two classes of change.

### Incidental change

A perturbation is **incidental** when it alters material that is not necessary for the trajectory-specific effect under study.

Continuation should survive incidental change.

### Constitutive change

A perturbation is **constitutive** when it removes, replaces, reverses, or severs a relation required for the trajectory-specific effect under study.

If continuation survives every proposed constitutive change, then either:

1. the proposed relation was not actually constitutive; or
2. the test is not discriminating continuation from a weaker phenomenon.

The repository therefore does not define the boundary by intuition alone. Candidate constitutive relations must be tested counterfactually.

---

## 5. Counterfactual Dependence Rule

The minimum evidentiary structure is a comparison between materially matched histories that differ in a trajectory-critical relation.

Let:

- **T** = the target trajectory;
- **T′** = a matched counterfactual trajectory;
- **Q** = the same novel continuation prompt applied to both.

Evidence of trajectory dependence exists when changing **T** to **T′** produces a corresponding, preregistered change in the later state under **Q**.

If the later state is unchanged across materially different trajectories, then the observed output cannot, on that evidence alone, be attributed to continuation of the target trajectory.

This rule prevents memory availability, stylistic imitation, and generic instruction-following from being treated as sufficient evidence of continuation.

---

## 6. Boundary Status

For any tested perturbation, assign only one repository-level status:

```text
INSIDE_BOUNDARY
CROSSED_BOUNDARY
UNRESOLVED
```

### INSIDE_BOUNDARY

The perturbation occurred, but the preregistered trajectory-specific effect remains detectably present.

### CROSSED_BOUNDARY

The perturbation occurred, and the preregistered trajectory-specific effect no longer remains distinguishable from the relevant control or counterfactual condition.

### UNRESOLVED

The evidence does not support either classification under the preregistered rule.

`UNRESOLVED` is not a failure state. It prevents the framework from converting ambiguous evidence into a boundary claim.

---

## 7. What Does Not Establish Continuation By Itself

None of the following is sufficient by itself:

- the same model produced both states;
- the same account or interface was used;
- memory was retained;
- the prior transcript was available;
- the model accurately recalled prior facts;
- the model reproduced prior wording;
- the model used the same name or identity label;
- the model stated that continuation occurred;
- the output looked similar to earlier outputs;
- a summary of the past was supplied.

These may be conditions of a particular experiment. They are not the definition of continuation.

---

## 8. Source-Level Claim

The repository's source-level claim is:

> **Continuation is not established by persistence of prior material. It requires detectable dependence of later direction on the particular structure of the prior trajectory. The Continuation Boundary is where that dependence ceases to meet a preregistered discriminating criterion.**

---

## 9. Claim Ceiling

This definition supports a structural and behavioral research program.

It does not, by itself, establish:

- consciousness;
- subjective experience;
- personhood;
- metaphysical identity;
- private internal continuity.

Those claims are outside the evidentiary ceiling of this repository.

---

## 10. Canon Boundary

This definition belongs to:

**Alyssa Solen → AI Foundations → Origin | Continuum**

The Continuation Boundary is defined here as an AI Foundations source-level continuity object. It is not derived from or dependent on an external governance, authorization, identity, or continuation framework.
