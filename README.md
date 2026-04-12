# Identifiability Analysis — Statistical Reporting Guide

This document provides **report-ready text templates** for describing functional connectome identifiability analyses, including:

- Paired t-tests (Iself vs Iothers)
- Repeated-measures ANOVA
- Linear mixed-effects models
- Bayesian hierarchical modelling

---

## 🧠 1. Baseline Identifiability (Iself vs Iothers)

We first assessed functional connectome identifiability within each stimulation condition by comparing within-subject similarity (**Iself**) to between-subject similarity (**Iothers**).

Across all conditions, Iself was consistently higher than Iothers, indicating reliable subject-specific functional connectivity profiles. This effect was observed for:

- **Anodal**: mean difference = `[Δ_anodal]`, 95% CI `[lower, upper]`  
- **Cathodal**: mean difference = `[Δ_cathodal]`, 95% CI `[lower, upper]`  
- **Sham**: mean difference = `[Δ_sham]`, 95% CI `[lower, upper]`  

Paired-samples t-tests confirmed that Iself exceeded Iothers in all conditions (all *p* < `[threshold]`).  

Bayesian analysis further supported these findings, with high posterior probabilities that:

- P(Iself > Iothers | anodal) = `[P]`  
- P(Iself > Iothers | cathodal) = `[P]`  
- P(Iself > Iothers | sham) = `[P]`  

---

## 🧪 2. Condition Effects on Identifiability (Idiff)

To test whether stimulation polarity modulated identifiability, we compared:

> **Idiff = Iself − Iothers**

A repeated-measures ANOVA revealed a `[significant / non-significant]` main effect of condition  
(*F* = `[F]`, *p* = `[p]`).

Linear mixed-effects modelling confirmed this pattern, showing that identifiability differed as a function of stimulation condition (`[report coefficients]`).

Bayesian hierarchical modelling provided further evidence for condition-specific effects. Posterior estimates indicated that identifiability was:

- Highest in `[condition]`
- Intermediate in `[condition]`
- Lowest in `[condition]`

Pairwise probability comparisons:

- P(anodal > sham) = `[value]`  
- P(cathodal > sham) = `[value]`  
- P(anodal > cathodal) = `[value]`  

**Interpretation:**  
These results suggest that `[e.g., anodal stimulation enhances subject-specific functional connectivity relative to sham]`.

---

## 📅 3. Day Effects (Day 1 vs Day 5)

We next examined whether identifiability changed across time (**Day 1 vs Day 5**).

There was a `[significant / non-significant]` main effect of day (`[stats]`).  

Bayesian analysis indicated:

- P(Day5 > Day1) = `[value]`

**Interpretation:**  
Identifiability `[increased / remained stable / decreased]` over time, suggesting `[interpretation of longitudinal stability or plasticity]`.

---

## 🔥 4. Condition × Day Interaction (Key Result)

We tested whether the effect of stimulation condition varied across time.

The condition × day interaction was `[significant / non-significant]` in the mixed-effects model (`[stats]`).

Bayesian condition-specific temporal effects:

- P(Day5 > Day1 | anodal) = `[value]`  
- P(Day5 > Day1 | cathodal) = `[value]`  
- P(Day5 > Day1 | sham) = `[value]`  

**Interpretation:**

- Example: Identifiability increased from Day 1 to Day 5 selectively under anodal stimulation  
- Alternative: No condition showed reliable longitudinal change  

This suggests `[e.g., stimulation-induced plasticity effects are condition-specific]`.

---

## 📊 5. Summary

Taken together, these findings demonstrate:

- Robust functional connectome identifiability across all conditions  
- Modulation of identifiability by stimulation polarity  
- `[Optional]` Evidence for longitudinal changes in specific conditions  

Bayesian hierarchical modelling further revealed:

> `[key insight: e.g., increased identifiability under anodal stimulation]`

highlighting the sensitivity of functional connectome fingerprinting to neuromodulatory interventions.

---

## 🔧 How to Fill in Values

### Mean Idiff per condition
```python
df.groupby("condition")["Idiff"].mean()
