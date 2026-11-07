# Model Taxonomy and Semantics

**Status:** Draft specification, V1 foundation

## 1. Purpose

Provide a shared taxonomy for biological models while preserving differences between model classes and their assumptions.

## 2. Model classes

### 2.1 Structural models
Represent entities, components, composition, location, topology, and structure. They describe what is represented and how components are organized.

### 2.2 Relational models
Represent typed interactions, associations, regulatory relations, and other dependencies. Each edge must declare its semantics and evidence status. A graph edge is not automatically causal.

### 2.3 Dynamical models
Represent change over time using state variables, transition rules, differential equations, discrete events, or hybrid systems. They must declare state space, time semantics, parameters, units, initial/boundary conditions, and validity domain.

### 2.4 Probabilistic models
Represent uncertainty, stochastic variation, or probabilistic dependence. They must declare random variables, distributions or transition assumptions, conditioning context, parameter provenance, and interpretation.

### 2.5 Multi-scale and hybrid models
Combine model classes or biological scales. Interfaces between components must define variable mapping, units, temporal resolution, coupling assumptions, and information loss.

## 3. Required model metadata

Each model should declare:
- model ID, title, version, status, authorship/maintainers;
- biological question and intended use;
- domain and context of applicability;
- model class and formalism;
- represented entities and variables;
- assumptions, exclusions, and simplifications;
- parameters, units, and parameter provenance;
- initial/boundary conditions where relevant;
- evidence and calibration/validation references;
- known limitations and uncertainty;
- schema and semantic version.

## 4. Semantics and units

Every quantitative variable must have a declared quantity kind and unit or an explicit dimensionless designation. Unit conversion must be explicit and validated. Avoid comparing values with incompatible dimensions.

Time, concentration, counts, rates, probabilities, and dimensionless scores must not be conflated. A numerical value without unit, scale, or interpretation is incomplete when the quantity is dimensional.

## 5. Causal semantics

Causal claims require an explicit causal interpretation and assumptions. Observational association alone is insufficient. Model documentation should identify confounders, interventions or identification assumptions where relevant, and the population/context to which conclusions apply.

## 6. Model composition

Composing models requires explicit interface contracts:
- compatible entity identity and ontology versions;
- compatible units and coordinate/time conventions;
- mappings between variables and states;
- coupling direction and update semantics;
- assumptions introduced by composition;
- uncertainty propagation strategy;
- provenance of derived outputs.

## 7. Reproducibility

A model run or result should be traceable to model version, parameter set, input dataset versions, software/tool versions, random seed when applicable, and execution configuration. A model definition is not the same artifact as a particular simulation run.

## 8. Model status

Suggested lifecycle: proposed → specified → implemented → validated-for-scope → deprecated. Status transitions require documented criteria. “Validated” must always name the validation scope and evidence; it is never an unqualified assertion of universal truth.
