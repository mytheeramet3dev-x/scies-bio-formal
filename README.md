# SCIES-BIO-FORMAL

**A unified, evidence-aware formal foundation for biological knowledge and models.**

SCIES-BIO-FORMAL defines machine-readable biological concepts, model semantics, evidence provenance, uncertainty, and formal contracts. It is intended to provide a stable foundation that computational tools and reasoning systems can consume without conflating biological observations, scientific interpretations, mathematical abstractions, and formal proofs.

## Mission

Build a bounded, versioned, and evidence-backed formal representation of biology that can support:

- interoperable biological knowledge and model definitions;
- explicit context, assumptions, scope, and uncertainty;
- structural, relational, dynamical, and probabilistic models;
- validation of model structure and internal consistency;
- formalization of selected definitions and invariants in Lean 4;
- downstream integration with SCIES tools, including SCIES-LOGIC.

## Scope and boundaries

The project follows a **Unified Biology** approach: classical biology, mathematical biology, and computational biology are represented within one coherent framework.

The project does not claim to encode all of biology in its first version. Initial releases will focus on bounded domains with explicit scope, provenance, versioning, and validation criteria.

A formal proof establishes a consequence of stated definitions and assumptions. It does not, by itself, establish that those assumptions accurately describe biological reality. Empirical validity, model adequacy, implementation correctness, and formal validity are tracked separately.

This repository defines biological foundations and contracts. Runtime reasoning, constraint solving, dependency analysis, and impact analysis belong to consuming systems such as SCIES-LOGIC.

## Conceptual layers

1. **Biological reality** — the physical systems and processes being studied.
2. **Scientific knowledge** — observations, experiments, publications, and interpretations.
3. **Scientific models** — abstractions used to explain or predict selected aspects of reality.
4. **Formal models** — explicit mathematical and computational representations of those abstractions.
5. **Formal specifications and proofs** — machine-checkable definitions, invariants, and theorems under declared assumptions.

These layers must remain distinguishable in data contracts and documentation.

## Initial architecture

- `ontology/` — domain concepts, entity types, relations, and controlled vocabularies.
- `models/` — structural, relational, dynamical, and probabilistic model descriptions.
- `constraints/` — domain-independent and domain-scoped model constraints.
- `evidence/` — evidence records, provenance, uncertainty, and support/conflict links.
- `schemas/` — versioned machine-readable data contracts.
- `formal/Lean/` — Lean 4 definitions and proofs for selected formal properties.
- `tests/` — schema, semantic, consistency, and regression tests.
- `docs/` — architecture, semantics, validation, interoperability, and governance.

## Design principles

- **Evidence before assertion:** empirical claims carry provenance and context.
- **Explicit epistemic status:** distinguish observed, curated, inferred, and hypothesized statements.
- **Contextual semantics:** biological claims identify relevant organism, biological material, conditions, time, and method where applicable.
- **Typed relations:** distinguish association, correlation, regulation, interaction, and causation.
- **Uncertainty is first-class:** unknown or conflicting evidence must not be silently converted into certainty.
- **Versioned contracts:** schemas and model semantics evolve through documented changes.
- **Bounded formalization:** formalize well-scoped properties rather than asserting completeness.
- **Interoperability:** map to established community standards where appropriate without erasing source semantics.

## Documentation status

This repository is at its foundation stage. The initial specifications are design documents, not claims that a complete biological ontology, validated model library, or verified implementation already exists.

See [the documentation index](docs/README.md) as the specification set is added.

## License

License selection is pending. No license is granted by this README alone; until a license file is added, normal copyright applies.
