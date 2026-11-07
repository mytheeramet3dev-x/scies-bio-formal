# Evidence, Provenance, and Uncertainty

**Status:** Draft specification, V1 foundation

## 1. Purpose

Make the origin, interpretation, uncertainty, and disagreement of biological claims explicit and machine-traceable.

## 2. Separate claims from evidence

A claim is an assertion with defined semantics and scope. An evidence item is a source or observation that supports, weakens, or contextualizes a claim. Do not encode a citation as if it were itself the claim, and do not assume that one source proves every interpretation derived from it.

## 3. Evidence record

An evidence record should include, where available:
- evidence ID and version;
- source type (publication, database record, experiment, measurement, curated resource);
- persistent source identifier or resolvable reference;
- authorship/provider and publication/release date;
- access date where relevant;
- method, assay, sample, and experimental context;
- reported result and units;
- extraction/curation method and responsible agent;
- limitations, quality notes, and license/usage constraints.

## 4. Claim-evidence links

Each link should identify:
- target claim and evidence item;
- support, refute, qualify, or contextualize relation;
- rationale and scope of applicability;
- direct versus indirect evidence;
- curation status and provenance.

Conflicting evidence must be retained and represented, not silently discarded. Evidence can support a claim in one context and fail to support it in another.

## 5. Uncertainty

Distinguish at least:
- measurement uncertainty;
- sampling variability;
- parameter uncertainty;
- model/structural uncertainty;
- epistemic uncertainty due to incomplete knowledge;
- disagreement among sources or curators.

A confidence score is not a substitute for a probability distribution, confidence interval, evidence grade, or explicit qualitative uncertainty statement. The meaning and calibration of every numeric score must be documented.

## 6. Provenance graph

Derived assertions should record their input claims/evidence, transformation or inference rule, tool and version, parameters, and timestamp. Provenance should support tracing from a result back to primary sources and forward to dependent models.

## 7. Evidence quality

Quality assessment is domain- and question-dependent. Record criteria and rationale rather than imposing one universal score. Database inclusion, peer review, replication, sample size, and methodological suitability may inform assessment but do not independently guarantee correctness.

## 8. Missing and negative evidence

Distinguish “not measured,” “not reported,” “no evidence found,” and “evidence of absence.” Negative results require method sensitivity, detection limits, and scope where relevant.

## 9. Auditability

Changes to claims, evidence links, uncertainty, or interpretation should be versioned with a reason and attributable provenance. Historical states must remain reconstructable.
