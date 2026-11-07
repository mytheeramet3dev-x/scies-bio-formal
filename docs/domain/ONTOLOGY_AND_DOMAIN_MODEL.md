# Ontology and Domain Model

**Status:** Draft specification, V1 foundation

## 1. Purpose

Define a disciplined representation of biological entities, qualities, states, processes, and relations. The ontology is a semantic vocabulary and typing system; it is not a claim that every biological concept has one universally agreed definition.

## 2. Entity model

An ontology entity should have:
- globally stable project identifier;
- preferred label and optional synonyms;
- definition and scope note;
- entity type and parent/type relations where justified;
- source vocabulary identifiers, if mapped;
- status (proposed, active, deprecated);
- version and change history.

Identifiers must not depend on mutable labels. Deprecated identifiers remain resolvable and should point to replacements when one exists.

## 3. Core categories

Initial high-level categories include:
- material entities: molecule, macromolecule, complex, organelle, cell, tissue, organ, organism;
- informational entities: sequence record, annotation, feature, reference assembly;
- processes: biochemical reaction, transport, signaling, expression, development;
- qualities and states: concentration, activity, conformation, cell state, phenotype;
- contextual entities: environment, condition, time interval, specimen, assay, measurement.

These are starting categories, not a closed list.

## 4. Typed relations

Relations must have explicit domain, range, directionality, and semantics. Examples include:
- part-of / located-in;
- has-participant / participates-in;
- binds-to / interacts-with;
- catalyzes;
- transports;
- regulates;
- precedes / occurs-during;
- associated-with;
- correlated-with;
- causes (only when supported by an appropriately scoped causal model).

Do not use a generic relation such as 'affects' where a more precise relation is available. Association, correlation, regulation, and causation are not interchangeable.

## 5. Context

Biological statements are context-sensitive. A context object may include:
- taxon or organism;
- strain, cultivar, or genotype where relevant;
- tissue, cell type, cell state, or compartment;
- developmental stage and age range where relevant;
- environment and experimental conditions;
- time point or interval;
- biological material and sample preparation;
- assay, instrument, and measurement protocol.

Unknown context must be represented as unknown or unspecified, not filled by inference without recording that inference.

## 6. Epistemic status

At minimum distinguish:
- observed: directly reported measurement or observation;
- curated: normalized assertion based on a cited source;
- inferred: conclusion derived from other assertions or a model;
- hypothesized: proposed but not adequately established;
- disputed: credible evidence or interpretations conflict.

Status is not a numerical confidence score. Store confidence/uncertainty separately.

## 7. Open-world behavior

Absence of a relation in the knowledge base does not imply its negation. A closed-world assumption may be used only within an explicitly bounded dataset or query contract.

## 8. Identity and equivalence

Do not merge entities solely because labels match. Equivalence requires a documented mapping rationale, source identifiers, scope, and version. Distinguish exact identity, close match, broader/narrower concepts, and unresolved mapping.

## 9. Validation requirements

Ontology validation should check identifier uniqueness, relation typing, required metadata, valid references, deprecated-term handling, and prohibited semantic conflations. It cannot establish empirical truth merely by passing structural validation.
