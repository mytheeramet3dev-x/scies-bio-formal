# Unified Biology Architecture

**Status:** Draft specification, V1 foundation  
**Project:** SCIES-BIO-FORMAL

## 1. Purpose

SCIES-BIO-FORMAL provides a common formal foundation for biological concepts and models across classical biology, mathematical biology, and computational biology. It defines semantics and contracts; it is not itself a runtime reasoning engine.

## 2. Architectural separation

The system distinguishes five epistemic and technical layers:

1. **Biological reality:** physical entities and processes.
2. **Scientific evidence:** observations, measurements, experiments, and curated records.
3. **Scientific interpretation:** claims and explanations inferred from evidence.
4. **Scientific/formal models:** abstractions with explicit scope, variables, relations, and assumptions.
5. **Formal specifications and proofs:** machine-checkable consequences of definitions and assumptions.

No layer may silently be substituted for another. A Lean theorem proves a statement in a formal system; it does not independently validate the biological assumptions used to construct that system.

## 3. Domain layers

- **Molecular:** nucleic acids, proteins, small molecules, complexes, molecular states.
- **Interaction:** binding, catalysis, transport, regulation, and other typed interactions.
- **Pathway and process:** metabolism, signaling, gene regulation, and biological processes.
- **Cellular:** cell types, compartments, states, cycles, and cellular dynamics.
- **Organism and phenotype:** tissues, organs, organisms, traits, and contextual phenotypes.
- **Cross-cutting:** environment, time, biological material, measurement, experimental method, and provenance.

These are conceptual layers, not a claim that all biological phenomena form a strict hierarchy. Cross-layer relations and multi-scale models are expected.

## 4. Core subsystems

- ontology/: stable identifiers, types, definitions, and typed relations.
- models/: structural, relational, dynamical, and probabilistic model descriptions.
- constraints/: domain-independent and domain-scoped model constraints.
- evidence/: evidence objects, provenance, uncertainty, and support/conflict links.
- schemas/: versioned serialization and validation contracts.
- formal/Lean/: selected formal definitions, invariants, and theorems.
- tests/: conformance, regression, and semantic tests.
- docs/: specifications and governance.

## 5. Relationship to SCIES-LOGIC

BIO-FORMAL owns biological semantics, model definitions, evidence metadata, and formal contracts. SCIES-LOGIC consumes versioned contracts to perform runtime reasoning such as SAT/SMT checks, graph analysis, dependency analysis, and impact reporting.

The consumer must preserve source identifiers, versions, assumptions, and evidence references. It must not reinterpret a model's semantics without an explicit mapping or adapter.

## 6. Cross-cutting requirements

Every claim or model element should declare, where applicable:
- stable identifier and version;
- biological scope and context;
- epistemic status;
- source and provenance;
- assumptions and limitations;
- uncertainty or confidence representation;
- applicable schema and semantic version.

## 7. V1 non-goals

V1 does not attempt a complete universal ontology, a universal causal model, automated discovery of biological truth, or a fully verified implementation of every biological model. It does not prescribe experimental or biological intervention procedures.
