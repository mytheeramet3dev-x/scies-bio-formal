# Lean 4 Formalization Strategy

**Status:** Draft strategy, V1 foundation

## 1. Purpose

Use Lean 4 to formalize selected mathematical structures, definitions, invariants, and theorems that arise from explicitly scoped biological models.

## 2. What a proof means

A Lean proof establishes that a proposition follows from the definitions, axioms, and assumptions encoded in the formal environment. It does not establish that:
- the axioms are empirically true;
- the model is an adequate representation of nature;
- source data are correct;
- a software implementation conforms to the specification;
- a biological intervention is safe or effective.

These are separate validation questions and must be reported separately.

## 3. Formalization targets

Good initial targets include:
- type and structural invariants;
- conservation properties when assumptions are explicit;
- dimensional and algebraic properties;
- properties of finite-state transition systems;
- consistency of definitions and constraints;
- mathematical properties of a specified model.

Avoid encoding unverified empirical claims as unquestioned axioms. Empirical assumptions should be named, sourced, scoped, and visible in theorem dependencies.

## 4. Layered Lean project

Suggested layout:

~~~text
formal/Lean/
├── lakefile.lean
├── lean-toolchain
├── SCIES/
│   ├── Core/
│   ├── Ontology/
│   ├── Models/
│   ├── Constraints/
│   └── Verification/
└── README.md
~~~

The actual module structure should follow the first selected formalization domain. Do not create placeholder theorems that imply proof coverage where none exists.

## 5. Proof documentation

Every significant theorem should document:
- intended mathematical statement;
- definitions and assumptions;
- imported modules and dependencies;
- scope and exclusions;
- proof status and reproducible command;
- relationship to the scientific model and evidence.

Use explicit names for assumptions and avoid hiding substantive premises in broad axioms.

## 6. Proof levels

Report separately:
1. formal specification exists;
2. theorem is stated;
3. theorem is proved in Lean;
4. implementation is shown to refine or satisfy the specification;
5. empirical model has been evaluated against data.

Do not collapse these into a single “verified” label.

## 7. Mathlib and dependencies

Pin Lean and dependency versions. Record toolchain and package lock information. Review imported axioms and theorem dependencies for critical results. Rebuild proofs in CI.

## 8. Relation to runtime engines

Lean formalization artifacts may be consumed by SCIES-LOGIC, but proof terms, theorem names, assumptions, and version identifiers must be preserved. A runtime SAT/SMT result is not automatically a Lean theorem; an SMT result and a Lean proof have different trust and reproducibility requirements.
