# Interoperability Strategy

**Status:** Draft strategy, V1 foundation

## 1. Goal

Reuse established biological and scientific standards where they fit, while preserving source identifiers, semantics, version information, and provenance.

## 2. Candidate standards and resources

Potential mappings to evaluate include:
- Gene Ontology (GO): gene product attributes and biological process/function/component concepts.
- Sequence Ontology (SO): sequence feature terminology.
- ChEBI: chemical entities of biological interest.
- UniProt: protein sequence and functional annotation resources.
- NCBI Taxonomy: organism/taxon identifiers.
- OBO Foundry principles and ontology resources: ontology design and identifiers.
- SBML: computational representation of biochemical reaction networks and systems biology models.
- CellML: mathematical models of biological processes.
- BioPAX: pathway data exchange.
- SBGN: graphical notation for biological processes and networks.
- PROV-O: provenance representation.

This list is a candidate landscape, not a declaration of full compliance or endorsement. Each integration requires version-specific review of scope, license, mapping semantics, and maintenance status.

## 3. Mapping rules

For each external resource, document:
- source name, release/version, and canonical identifier format;
- mapping direction and cardinality;
- exact, broader, narrower, related, or unresolved mapping type;
- transformation rules and information loss;
- licensing and attribution requirements;
- update and deprecation policy.

Never overwrite an external identifier with a local identifier. Store both and preserve namespace.

## 4. Lossless versus lossy exchange

A mapping is lossless only when the relevant semantics can be represented without material loss. Otherwise mark it lossy and document omitted distinctions. Do not imply equivalence merely because two formats can serialize similar-looking graphs.

## 5. Units and mathematical formalisms

Where quantitative models are exchanged, preserve units, parameter meanings, mathematical formalism, initial conditions, and model scope. Imported model syntax does not guarantee identical simulation semantics across tools.

## 6. Conformance

Each adapter should have versioned fixtures, round-trip tests where meaningful, and explicit unsupported-feature reports. Conformance applies to a named standard version and profile, not to a standard in the abstract.
