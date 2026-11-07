# Roadmap and Acceptance Criteria

**Status:** Draft roadmap, V1 foundation

## Phase 0 — Repository foundation
- Establish documentation structure, governance, naming, and versioning.
- Define the separation between biological claims, evidence, models, and proofs.
- Acceptance: documentation index exists; scope and non-goals are explicit; no implementation claims are made without evidence.

## Phase 1 — Core contracts
- Define common artifact envelope, identifier policy, context, epistemic status, and provenance.
- Add machine-readable schemas and positive/negative fixtures.
- Acceptance: schema validation runs in CI; invalid examples fail for expected reasons; contract versioning is documented.

## Phase 2 — Bounded ontology
- Select a limited, evidence-backed biological domain.
- Define entity types, relation semantics, context requirements, and external mappings.
- Acceptance: terms have stable IDs and definitions; relations are typed; provenance and version are traceable; unresolved mappings remain explicit.

## Phase 3 — Model representations
- Add structural, relational, dynamical, and probabilistic model contracts as needed.
- Define units, assumptions, applicability, and composition rules.
- Acceptance: representative examples validate; unsupported semantics are reported; model limitations are documented.

## Phase 4 — Formalization
- Select a small set of mathematical invariants or properties.
- Create Lean 4 project and CI proof checks.
- Acceptance: theorem dependencies and assumptions are documented; proofs reproduce in CI; proof status is not confused with empirical validation.

## Phase 5 — Consumer integration
- Publish versioned contracts for downstream systems such as SCIES-LOGIC.
- Define compatibility tests and migration policy.
- Acceptance: consumers can identify exact artifact versions, preserve provenance, and distinguish invalid, inconsistent, unknown, and not-evaluated outcomes.

## Release gates

A milestone is complete only when its artifacts, tests, limitations, and acceptance evidence are present. Roadmap phase completion must not be inferred from directory creation or documentation alone.

## Prioritization

Prefer a small, high-quality, well-scoped domain over broad but weakly defined coverage. Domain selection should consider evidence quality, community standards, model maturity, and downstream utility.
