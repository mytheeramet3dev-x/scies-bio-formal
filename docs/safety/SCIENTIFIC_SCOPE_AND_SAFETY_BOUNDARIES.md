# Scientific Scope and Safety Boundaries

**Status:** Draft policy, V1 foundation

## 1. Purpose

Ensure that formal representations and reasoning outputs are interpreted within their actual scientific and technical scope.

## 2. Core distinctions

The project distinguishes:
- logical consistency from biological plausibility;
- mathematical correctness from empirical truth;
- model validation from universal generalization;
- software correctness from scientific validity;
- evidence availability from evidence quality;
- absence of evidence from evidence of absence.

A consistent model can still be biologically wrong. A theorem can be correct while its assumptions are false or inapplicable.

## 3. Scope declarations

Every model and claim must declare its intended context, assumptions, limitations, and intended use. Outputs must not be generalized beyond that scope without additional evidence.

## 4. Uncertainty and conflict

Systems consuming these artifacts should preserve unknown, incomplete, disputed, and conflicting states. They must not silently convert missing information into a negative fact or a definitive conclusion.

## 5. Safety boundary

This repository specifies biological knowledge representations and abstract model semantics. It does not provide operational protocols for genetic modification, pathogen engineering, toxin production, or other hazardous biological procedures. Formal consistency checks are not biosafety approval, regulatory authorization, or clinical advice.

## 6. Responsible interpretation

Reports should state which checks were performed, which were not performed, and what assumptions remain. Avoid unqualified labels such as “safe,” “proven biological truth,” or “fully verified” unless a separately defined, appropriately reviewed process supports the exact claim.
