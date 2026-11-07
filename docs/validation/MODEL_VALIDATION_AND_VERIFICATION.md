# Model Validation and Verification

**Status:** Draft specification, V1 foundation

## 1. Purpose

Define separate validation activities so that a structurally valid artifact is not mistaken for a scientifically valid model or a formally proved result.

## 2. Validation dimensions

### A. Data and schema validity
Checks serialization, required fields, types, enumerations, and schema version.

### B. Ontology and semantic validity
Checks identifiers, relation typing, domain/range constraints, unit compatibility, and declared semantics.

### C. Provenance validity
Checks source resolution, lineage, attribution, evidence links, and version traceability.

### D. Mathematical/formal validity
Checks mathematical well-formedness and, where formalized, machine-checked properties under declared assumptions.

### E. Implementation correctness
Checks that software behavior conforms to a specification through refinement proofs, code-level verification, testing, or a combination. A proof about an abstract specification alone does not prove an implementation.

### F. Empirical/scientific validity
Evaluates whether a model is appropriate for its intended biological question and context using relevant data, experimental evidence, calibration, validation, replication, and uncertainty analysis.

## 3. Validation report

A report should include:
- artifact and exact version;
- validation dimensions executed;
- tools and versions;
- input datasets and versions;
- assumptions and test conditions;
- pass, fail, inconclusive, or not evaluated status per dimension;
- diagnostics and evidence references;
- limitations and reproducibility instructions.

## 4. Status semantics

- **Pass:** the specified check completed and met its criterion.
- **Fail:** the check completed and violated its criterion.
- **Inconclusive:** available information or solver outcome is insufficient.
- **Not evaluated:** no check was run for that dimension.

Do not map missing data or unsupported checks to Pass.

## 5. Regression and reproducibility

Maintain versioned fixtures for schemas, ontology rules, model examples, and known edge cases. Record deterministic configuration and random seeds where applicable. Changes to semantics require regression review and migration notes.

## 6. Scientific review

Validation criteria must be tied to intended use and biological context. A model may be valid for one taxon, tissue, assay, or condition and invalid or untested elsewhere. Record the scope explicitly.

## 7. Release gate

A release candidate should pass schema and contract tests, resolve required references, document known semantic limitations, and provide reproducible formal checks for any theorem advertised as proved. Empirical validation claims require their own evidence and review record.
