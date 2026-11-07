# ADR-0001: Adopt a Unified Biology Foundation

- **Status:** Accepted as initial design direction
- **Date:** 2026-11-08
- **Decision owners:** SCIES-BIO project maintainers

## Context

The SCIES ecosystem spans biological databases, computational biology, simulation, neuro-related modeling, and formal reasoning. Separate vocabularies and incompatible model assumptions would make cross-project reasoning difficult. At the same time, biological knowledge, scientific models, and formal proofs have different epistemic roles and must not be conflated.

## Decision

Adopt a Unified Biology foundation that can represent classical biology, mathematical biology, and computational biology through shared, versioned contracts.

Keep the following concerns distinct within the architecture:
1. ontology and domain semantics;
2. scientific claims and evidence;
3. structural, relational, dynamical, and probabilistic models;
4. formal specifications and Lean 4 proofs;
5. downstream runtime reasoning and analysis.

BIO-FORMAL defines the foundation and contracts. SCIES-LOGIC and other consumers use those contracts without owning or silently redefining the underlying biological semantics.

## Consequences

### Positive
- Shared semantics across SCIES projects.
- Explicit provenance, uncertainty, assumptions, and scope.
- Reusable formal contracts and proofs.
- Clear boundary between knowledge foundation and runtime reasoning.

### Trade-offs
- More upfront work on identifiers, semantics, and versioning.
- Mapping external standards requires ongoing maintenance.
- Unified architecture does not mean one universal model or one forced ontology hierarchy.

## Alternatives considered

- **Independent domain ontologies per subsystem:** rejected as the sole strategy because it risks semantic fragmentation.
- **One monolithic deterministic biology model:** rejected because biological systems are context-dependent, uncertain, and multi-scale.
- **Treat all biological claims as formal axioms:** rejected because formal provability does not establish empirical truth.

## Review triggers

Revisit this decision if domain-specific requirements demonstrate that a shared contract causes unacceptable semantic loss, if external standards require incompatible representations, or if downstream consumers need independently versioned profiles.
