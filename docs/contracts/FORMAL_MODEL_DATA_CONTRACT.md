# Formal Model Data Contract

**Status:** Draft contract, V1  
**Serialization baseline:** JSON-compatible data; concrete JSON Schema files will be versioned under schemas/.

## 1. Contract goals

The contract provides a stable interchange boundary for ontology terms, claims, evidence, contexts, and model definitions. It must preserve semantics and provenance across BIO-FORMAL and downstream consumers.

## 2. Common envelope

Every top-level artifact should include:
- id: stable identifier;
- artifact_type: controlled type;
- schema_version: contract version;
- semantic_version: meaning/version of the artifact;
- status: lifecycle status;
- created_at and updated_at: ISO 8601 timestamps where available;
- provenance: source and transformation metadata.

## 3. Claim shape (illustrative)

~~~json
{
  "id": "claim:example:0001",
  "artifact_type": "biological_claim",
  "schema_version": "0.1.0",
  "semantic_version": "0.1.0",
  "statement": {
    "subject": "entity:example:subject",
    "predicate": "relation:associated_with",
    "object": "entity:example:object"
  },
  "epistemic_status": "curated",
  "context": {
    "taxon": null,
    "biological_material": null,
    "conditions": [],
    "time": null,
    "assay": null
  },
  "evidence_refs": [],
  "assumptions": [],
  "limitations": [],
  "uncertainty": {
    "type": "unspecified",
    "description": "No quantitative uncertainty characterization supplied."
  }
}
~~~

This is an illustrative shape, not yet a normative schema. Null means explicitly unknown/not supplied according to the field definition; omitted fields must have separately documented default semantics.

## 4. Model artifact

A model artifact must additionally identify model class, purpose, domain of applicability, variables/entities, formalism, units, assumptions, parameters, initial/boundary conditions where applicable, validation records, and known limitations.

## 5. Reference integrity

References must resolve to an artifact ID and compatible version or declare a version range. Consumers must not silently substitute a newer incompatible artifact. External identifiers should retain source namespace and original value.

## 6. Extensibility

Use namespaced extension fields or explicit extension objects. Unknown fields should be handled according to schema policy; consumers must not reinterpret unknown fields as known semantics.

## 7. Versioning policy

- Patch: editorial/metadata corrections that do not change semantics.
- Minor: backward-compatible additions.
- Major: breaking changes to meaning, required fields, or interpretation.

Schema version and semantic version are separate because a serialization change need not imply a scientific meaning change, and vice versa.

## 8. Validation

Validation has distinct stages: syntax/schema, reference integrity, type/semantic constraints, provenance completeness, and domain-specific checks. Passing one stage must not be reported as passing all stages.

## 9. Contract status

The examples in this document are provisional. A release must include machine-readable schemas, test fixtures, compatibility policy, and migration notes before declaring the contract stable.
