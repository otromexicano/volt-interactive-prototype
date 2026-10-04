# Phase 03 — User Flow

## Canonical Status

- **Canonical phase:** Phase 03 — User Flow
- **Canonical repository output:** This document is the one canonical repository User Flow output required by `docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`.
- **Current status:** **PASS / COMPLETE**.
- **Initial read-only audit:** Complete. The audit identified incomplete system responses and success/failure coverage, missing required informational flows, and conflicts between historical flow scope and the approved Phase 02 scope.
- **Human flow-direction selection:** **COMPLETE / APPROVED — October 3, 2026**.
- **Targeted remediation:** Complete on October 3, 2026.
- **Canonical Figma candidate:** `FLOW — 02 Canonical User Flow Candidate` on `90 — Candidates`, node `61:2`; accepted as the approved Phase 03 Figma artifact.
- **Completion audit:** **PASS — October 3, 2026**.
- **Final human approval:** **APPROVED — October 3, 2026**.
- **Completion boundary:** Phase 03 is complete. Phase 04 — Information Architecture is the next canonical phase and has not started.
- **Evidence boundary:** The flows below are human-approved design decisions for a bounded prototype. They are not research findings, observed behavior, validated journeys, analytics, production behavior, usability results, or evidence of product or business impact.

## Evidence Classification

| Classification | Meaning in this User Flow |
| --- | --- |
| **FACT** | Information directly supplied by the source brief or directly observable in a current approved artifact. |
| **ASSUMPTION** | A provisional belief that requires validation and must not be presented as observed behavior. |
| **DESIGN DECISION** | A selected prototype interpretation, mechanism, constraint, or flow treatment. |
| **HUMAN-APPROVED DESIGN DECISION** | A design decision explicitly selected by the user for this Phase 03 remediation. It is not research evidence. |
| **OPEN QUESTION** | Information that is not supplied or validated and must not be silently resolved. |

No statement in this document establishes user research, interviews, usability findings, analytics, real catalogue structure, production inventory, production errors, a real contact workflow, backend behavior, conversion, sales, leads, or other outcomes.

## Approved Scope

### Retained Phase 02 scope

1. Site navigation and orientation.
2. Landing / Home.
3. Catalogue overview and broad product browsing.
4. Product Detail.
5. Contact entry points and a generic Contact surface.
6. Information page.
7. About / Team.
8. Privacy Policy.

### Deferred or removed from committed Phase 03 flow scope

- **DEFERRED:** Category / Collection.
- **DEFERRED:** Search.
- **DEFERRED:** Filters.
- **REMOVED:** Cart indicator and cart behavior.
- **OUT OF SCOPE:** Checkout, payment, purchase, orders, authentication, accounts, backend commerce, real inventory, production transactions, and Contact submission.

Deferral or removal does not erase the historical artifacts in which those paths appear. It means they do not govern the current canonical flow.

## Primary Task Inventory

| Task ID | Task / destination | Approved purpose | Classification |
| --- | --- | --- | --- |
| UF-01 | Home entry and orientation | Provide the source-required landing destination and a bounded entry to Catalogue or Contact. | **FACT** for required landing content; **HUMAN-APPROVED DESIGN DECISION** for its flow role. |
| UF-02 | Broad Catalogue browsing | Let a visitor review representative catalogue items without Category, Search, or Filters. | **FACT** for the catalogue-viewing goal; **HUMAN-APPROVED DESIGN DECISION** for broad browsing. |
| UF-03 | Product Detail review | Present the available information for one represented product. | **FACT** for required product pages; **HUMAN-APPROVED DESIGN DECISION / ASSUMPTION** for the information-review task. |
| UF-04 | Generic Contact access | Demonstrate that the generic Contact surface is reachable through global and contextual entry points. | **FACT** for the contact goal; **HUMAN-APPROVED DESIGN DECISION** for reachability as completion. |
| UF-05 | Information access | Present the source-required Information content for review. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |
| UF-06 | About / Team access | Present the source-required About / Team content for review. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |
| UF-07 | Privacy Policy access | Present the source-required Privacy Policy content for review. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |
| UF-08 | Shared navigation and recovery | Make every retained destination reachable and prevent dead ends without mapping every possible route permutation. | **HUMAN-APPROVED DESIGN DECISION** grounded in the approved destination inventory. |

## Primary Flow

### Canonical high-level model

```text
Home
  ↓
Catalogue
  ↓
Product Detail
  ↓
Next decision
  ├─ Return to previous broad Catalogue context when available
  │    └─ Fallback: broad Catalogue
  └─ Reach generic Contact surface
```

This flow does not include Category / Collection, Search, Filters, Cart, checkout, payment, purchase, accounts, or Contact submission.

### UF-01 — Home entry and orientation

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Home, including legitimate direct navigation to Home. |
| **User action** | Review the available landing content and open Catalogue or Contact. |
| **System response** | Present the available source-required landing content and reachable retained destinations. |
| **Next decision** | Continue to broad Catalogue browsing or reach the generic Contact surface. |
| **Success** | The selected retained destination is reached. |
| **Failure** | The selected retained destination is unreachable or presents no destination content. |
| **Happy path** | Home → Catalogue. |
| **Alternate path** | Home → Contact. |
| **Cancellation** | **NOT APPLICABLE.** No transaction or committed process begins on Home. Navigating elsewhere is ordinary navigation. |
| **Error path** | Selected destination is unreachable. |
| **Empty state** | If required landing content is not represented, state that the content is unavailable and keep retained destinations reachable. |
| **Permissions** | **NOT APPLICABLE.** No permission is required for this task. |
| **Recovery** | Remain on Home and use another documented retained destination. |

### UF-02 — Broad Catalogue browsing

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Home or the shared global orientation layer. |
| **User action** | Browse the broad represented catalogue and select a represented product. |
| **System response** | Present available representative catalogue items without Category, Search, Filters, sorting, inventory behavior, or personalization. |
| **Next decision** | Continue broad browsing or open Product Detail for a represented product. |
| **Success** | Product Detail is reached for the selected represented product. |
| **Failure** | No representative items are available or the selected Product Detail destination is unreachable. |
| **Happy path** | Home → Catalogue → Product Detail. |
| **Alternate path** | Direct navigation → Catalogue → Product Detail. |
| **Cancellation** | **NOT APPLICABLE.** Browsing does not initiate a transaction. Leaving through navigation is abandonment. |
| **Error path** | Unavailable represented catalogue content or unreachable Product Detail. |
| **Empty state** | No representative catalogue items are currently available in the prototype. |
| **Permissions** | **NOT APPLICABLE.** No permission is required for broad catalogue browsing. |
| **Recovery** | Go to Home or Contact. A refresh, retry, or future item availability is not promised. |

### UF-03 — Product Detail review and next decision

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Select a represented product from the broad Catalogue. |
| **User action** | Review the available represented Product Detail information. |
| **System response** | Present supplied product content and explicit unavailable states for any image, attribute, or other information that is not supplied. |
| **Next decision** | Return to the previous broad Catalogue context or reach the generic Contact surface. |
| **Success** | The previous broad Catalogue context is restored, the broad Catalogue fallback is reached, or the generic Contact surface is reached. |
| **Failure** | Missing represented information prevents continuation, the return path is broken, orientation is lost, or Contact is unreachable. |
| **Happy path** | Catalogue → Product Detail → previous broad Catalogue context. |
| **Alternate path** | Catalogue → Product Detail → Contact. |
| **Cancellation** | **NOT APPLICABLE.** Product review is not a transaction. Leaving through an approved return or navigation path is abandonment. |
| **Error path** | Missing represented Product Detail content, broken return path, lost orientation, or unreachable Contact. |
| **Empty state** | A Product Detail attribute, image, or other information is not supplied. |
| **Permissions** | **NOT APPLICABLE.** No permission is required to review represented product information. |
| **Recovery** | Continue with available information, return to broad Catalogue, or reach Contact. |

## Global Navigation / Orientation

### Shared layer

```text
SHARED GLOBAL ORIENTATION LAYER
├─ Home
├─ Catalogue
├─ Contact
├─ Information
├─ About / Team
└─ Privacy Policy
```

Privacy Policy may additionally be reached through footer navigation. The shared layer is represented once; the canonical flow does not duplicate every destination-to-destination permutation.

### Flow-level requirements

- Every retained destination must be reachable.
- Current destination or orientation must be understandable.
- Direct-entry destinations must provide a return or global-navigation recovery path.
- No retained destination may become a dead end.
- No pointer-only dependency is implied.
- Destination names and current orientation must remain understandable without relying only on color.
- Detailed keyboard, focus, menu, disclosure, and dismissal behavior is deferred to Phase 05 — Interaction Contract.

## Product Detail Return

**HUMAN-APPROVED DESIGN DECISION — OPTION A:** Return to the previous broad Catalogue context when available.

**Fallback:** Broad Catalogue.

### Context that may be preserved

- originating broad Catalogue destination;
- represented catalogue position or item neighborhood if later implementation supports it;
- identity of the represented product; and
- a visible orientation cue.

These are prototype context decisions, not claims of production or cross-session persistence.

### Context that must not be invented

- Search query;
- Filter state;
- Category / Collection state;
- sort or ranking state;
- inventory state;
- account state;
- cross-session history;
- backend persistence; or
- analytics-derived personalization.

## Contact Flow

### Approved success and failure model

- **SUCCESS:** The intended generic Contact surface is reached and its approved generic contact/help content is presented.
- **FAILURE:** The intended Contact destination cannot be reached from the represented entry point, or the destination contains no Contact content.

Success does not mean a message was sent, contact occurred, support responded, a lead was generated, email was delivered, a form was submitted, or a backend transaction succeeded.

### UF-04A — Global Contact

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Home or the shared global orientation layer. |
| **User action** | Open Contact. |
| **System response** | Present the approved generic Contact/help content. |
| **Next decision** | Continue reviewing the content or leave through a valid return/global-navigation path. |
| **Success** | Contact content is reached and presented. |
| **Failure** | Contact is unreachable or contains no Contact content. |
| **Happy path** | Home or global orientation → Contact. |
| **Alternate path** | Any retained destination → shared orientation layer → Contact. |
| **Cancellation** | **NOT APPLICABLE.** No transaction or submission exists. |
| **Error path** | Unreachable or empty Contact destination. |
| **Empty state** | No approved Contact content is represented. This is a failure state, not a submission state. |
| **Permissions** | **NOT APPLICABLE.** No permission is required. |
| **Recovery** | Return to the immediately preceding represented destination when known, or use global navigation. |

### UF-04B — Product Detail to Contact

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Product Detail. |
| **User action** | Open the generic Contact surface. |
| **System response** | Present approved generic Contact/help content while keeping the originating Product Detail relationship conceptually understandable. |
| **Next decision** | Review Contact content or return to the originating Product Detail. |
| **Success** | Contact content is reached and presented. |
| **Failure** | Contact is unreachable, contains no Contact content, or provides no valid return path. |
| **Happy path** | Product Detail → Contact. |
| **Alternate path** | Product Detail → prior broad Catalogue context instead of Contact. |
| **Cancellation** | **NOT APPLICABLE.** No transaction or submission exists. |
| **Error path** | Unreachable Contact or broken Product Detail return. |
| **Empty state** | No approved Contact content is represented. |
| **Permissions** | **NOT APPLICABLE.** No permission is required. |
| **Recovery** | Return conceptually to the originating Product Detail; if origin is lost, recover to broad Catalogue. |

No product data transfer, prefill, Contact form state, unsaved-input warning, retry, confirmation, submission, or delivery behavior is implied.

## Information Flow

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Global navigation or an approved internal destination. |
| **User action** | Open Information. |
| **System response** | Present the available source-required Information content. |
| **Next decision** | Continue reviewing or navigate to another retained destination. |
| **Success** | The Information destination and its available content are reached for review. |
| **Failure** | The destination is unreachable or the required represented content is absent. |
| **Happy path** | Global navigation → Information → content review. |
| **Alternate path** | Approved internal destination → Information. |
| **Cancellation** | **NOT APPLICABLE.** Navigating away is ordinary abandonment, not transaction cancellation. |
| **Error path** | Unreachable destination or absent represented Information content. |
| **Empty state** | Information content is not supplied or represented. |
| **Permissions** | **NOT APPLICABLE.** No permission is required. |
| **Recovery** | Return to the represented origin when known or use global navigation. |

## About / Team Flow

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Global navigation or an approved internal destination. |
| **User action** | Open About / Team. |
| **System response** | Present the available source-required About / Team content. |
| **Next decision** | Continue reviewing or navigate to another retained destination. |
| **Success** | The About / Team destination and its available content are reached for review. |
| **Failure** | The destination is unreachable or the required represented content is absent. |
| **Happy path** | Global navigation → About / Team → content review. |
| **Alternate path** | Approved internal destination → About / Team. |
| **Cancellation** | **NOT APPLICABLE.** Navigating away is ordinary abandonment. |
| **Error path** | Unreachable destination or absent represented About / Team content. |
| **Empty state** | About / Team content is not supplied or represented. |
| **Permissions** | **NOT APPLICABLE.** No permission is required. |
| **Recovery** | Return to the represented origin when known or use global navigation. |

No additional motivation, trust outcome, or staff-contact behavior is inferred from the source requirement.

## Privacy Policy Flow

| Required anatomy | Canonical definition |
| --- | --- |
| **Entry** | Global and/or footer navigation. |
| **User action** | Open Privacy Policy. |
| **System response** | Present the available source-required Privacy Policy content. |
| **Next decision** | Continue reviewing or navigate to another retained destination. |
| **Success** | The Privacy Policy destination and its available content are reached for review. |
| **Failure** | The destination is unreachable or the required represented content is absent. |
| **Happy path** | Global/footer navigation → Privacy Policy → content review. |
| **Alternate path** | Another approved internal destination → Privacy Policy when represented. |
| **Cancellation** | **NOT APPLICABLE.** Navigating away is ordinary abandonment. |
| **Error path** | Unreachable destination or absent represented Privacy Policy content. |
| **Empty state** | Privacy Policy content is not supplied or represented. |
| **Permissions** | **NOT APPLICABLE.** No permission is required. |
| **Recovery** | Return to the represented origin when known or use global navigation. |

The presence of a Privacy Policy destination does not establish legal adequacy, consent handling, data collection, production privacy compliance, or any real data practice.

## Happy Paths

1. `Home → Catalogue → Product Detail → previous broad Catalogue context`
2. `Home → Catalogue → Product Detail → Contact`
3. `Home → Contact`
4. `Global navigation → Information → content review`
5. `Global navigation → About / Team → content review`
6. `Global/footer navigation → Privacy Policy → content review`

These paths are intended prototype behavior, not observations of actual visitor behavior.

## Alternate Paths

- `Home → Contact`
- `Home → Catalogue`
- `Catalogue → Product Detail`
- `Product Detail → Contact`
- `Product Detail → prior broad Catalogue context`
- `Global navigation → Information`
- `Global navigation → About / Team`
- `Global/footer navigation → Privacy Policy`
- `Any retained destination → shared global orientation layer → another retained destination`

The shared orientation layer represents general cross-destination access. The flow intentionally does not draw every possible destination pair.

## Cancellation / Abandonment

- No retained Phase 03 task initiates a transaction or submission.
- **Cancellation is NOT APPLICABLE** to Home, Catalogue browsing, Product Detail review, Contact, Information, About / Team, or Privacy Policy.
- Abandonment means leaving the current destination through a valid return or navigation path.
- Global Contact returns to the immediately preceding represented destination when known or uses global navigation.
- Contact entered from Product Detail provides a conceptual return to the originating Product Detail.
- No unsaved-input warning, form state, retry state, confirmation, or submission state is represented.

## Empty / Missing Content States

### Catalogue-level represented content unavailable

- **State:** No representative catalogue items are currently available in the prototype.
- **System response:** State the prototype content limitation explicitly.
- **Recovery:** Home or Contact.
- **Does not claim:** zero production inventory, out of stock, Search no-results, Filter mismatch, network/server failure, discontinued products, or any production catalogue condition.

### Product-level represented content unavailable

- **State:** A Product Detail attribute, image, or other information is not supplied.
- **System response:** Identify the content as unavailable rather than inventing a value.
- **Recovery:** Continue with available information, return to broad Catalogue, or reach Contact.
- **Does not claim:** production data loss, inventory state, network failure, or that Contact can necessarily provide the missing content.

### Informational-content unavailable

- **State:** Required represented Information, About / Team, Privacy Policy, or Contact content is absent.
- **System response:** Identify the represented content as unavailable.
- **Recovery:** Return to the known origin or use global navigation.
- **Flow consequence:** If Contact contains no Contact content, the approved Contact failure condition is met.

## Error States

### Retained evidence-safe flow errors

1. Unavailable represented product content.
2. Unreachable intended retained destination.
3. Missing represented information needed to continue.
4. Broken return path or lost orientation.

These are prototype flow defects or represented-content states. Broken routes remain identifiable as defects and must not be presented as successful recovery behavior.

### Removed historical error types

- invalid Contact input;
- required Contact-field validation;
- simulated submission failure or retry;
- email or message delivery failure;
- Search no-results;
- Filter-generated empty results;
- Category-empty states;
- backend, inventory, payment, checkout, account, or transaction errors.

## Recovery Paths

| Error or unavailable state | Recovery |
| --- | --- |
| Unavailable Catalogue content | Home or Contact. |
| Missing Product Detail content | Continue with available content, return to broad Catalogue, or reach Contact. |
| Unreachable retained destination | Return to the last reachable destination and use another documented navigation route. |
| Broken Product Detail return | Use broad Catalogue as the fallback. |
| Lost product-exploration origin | Catalogue. |
| Lost general orientation | Home or the shared global orientation layer. |
| Unavailable informational content | Return to the represented origin when known or use global navigation. |

## Permissions

**NOT APPLICABLE.**

No retained Phase 03 task requires authentication, account access, camera, location, notifications, microphone, file-system access, or another device permission. The prototype flow therefore has no permission-request, permission-denied, or permission-recovery branch.

This does not establish future production permission requirements; those remain unknown unless supported by later evidence and approved scope.

## Screen → Flow Rationale

| Destination | Non-circular reason to exist | Source / approved need | Evidence classification |
| --- | --- | --- | --- |
| Navigation / orientation | Makes all retained destinations and recovery paths coherently reachable without duplicating every route permutation. | Smallest mechanism needed to connect the eight approved Phase 02 features. | **HUMAN-APPROVED DESIGN DECISION**, grounded in approved scope. |
| Home | Provides the required landing destination and bounded entry to Catalogue or Contact. | Source-required landing content; approved Phase 02 role. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for flow role. |
| Catalogue | Enables broad viewing of represented products without Category, Search, or Filters. | Source-stated catalogue-viewing goal. | **FACT** for the goal; **HUMAN-APPROVED DESIGN DECISION** for broad browsing. |
| Product Detail | Presents the information available for one represented product. | Source-required product pages; approved Phase 02 scope. | **FACT** for product pages; **HUMAN-APPROVED DESIGN DECISION / ASSUMPTION** for information review. |
| Contact | Demonstrates that generic Contact is reachable globally and from Product Detail. | Source’s primary Contact goal; approved generic Contact boundary. | **FACT** for the Contact goal; **HUMAN-APPROVED DESIGN DECISION** for reachability and entry points. |
| Information | Provides the general information content required by the source. | Source-required Information page. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |
| About / Team | Provides the About the Team content required by the source. | Source-required About / Team content. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |
| Privacy Policy | Provides the privacy-policy content required by the source. | Source-required Privacy Policy. | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination treatment. |

No destination is justified merely because it appears in a historical IA or flow artifact.

## Deferred / Removed Historical Paths

| Historical behavior | Current disposition | Current treatment |
| --- | --- | --- |
| Broad Catalogue browsing | **RETAINED** | Remains the approved discovery mechanism. |
| Product Detail | **RETAINED** | Remains the represented product-information destination. |
| Global and contextual Contact | **RETAINED** | Narrowed to generic Contact reachability and content presentation. |
| Product Detail return | **NARROWED** | Previous broad Catalogue context only; broad Catalogue fallback. |
| Category / Collection | **DEFERRED** | Preserved historically; excluded from committed Phase 03 scope. |
| Search | **DEFERRED** | Preserved historically; excluded from committed Phase 03 scope. |
| Filters | **DEFERRED** | Preserved historically; excluded from committed Phase 03 scope. |
| Search/filter no-results recovery | **DEFERRED** | Not a current empty-state model. |
| Cart indicator | **REMOVED** | No current flow path or state. |
| Contact form input and validation | **REMOVED** | No required fields or validation flow. |
| Contact submission, retry, and confirmation | **REMOVED** | No submission or delivery behavior. |
| Checkout, payment, purchase, order, account, backend, and transaction paths | **REMOVED / OUT OF SCOPE** | Not represented in canonical Phase 03. |

## Historical Preservation

- `docs/PRIMARY_FLOW.md` remains unchanged as historical supporting evidence.
- Figma node `44:2`, `FLOW — 01 Primary Discovery & Support`, remains unchanged as historical visual evidence.
- Historical Category / Collection, Search, Filters, and their result-state logic remain preserved as prior decisions.
- Historical Contact input, validation, simulated submission, failure, and retry states remain preserved as prior decisions.
- Historical approval remains traceable but does not establish current canonical completion.
- None of those historical behaviors govern the current Phase 03 scope where they conflict with the approved Phase 02 Product Definition.
- Figma pages `90 — Candidates` and `99 — Archive` remain preserved. The new current-scope flow is a candidate on `90 — Candidates`; no archive action was needed in this remediation.

## Figma Traceability

| Artifact | Role | Status |
| --- | --- | --- |
| Figma node `44:2` — `FLOW — 01 Primary Discovery & Support` on `02 — IA & Flows` | Historical visual evidence for the former Volt flow direction. | **PRESERVED UNCHANGED / NON-CANONICAL FOR CURRENT SCOPE** |
| Figma node `61:2` — `FLOW — 02 Canonical User Flow Candidate` on `90 — Candidates` | Current-scope visual candidate implementing the approved Phase 03 direction. | **APPROVED PHASE 03 FIGMA ARTIFACT** |
| `docs/PRIMARY_FLOW.md` | Historical repository flow evidence associated with node `44:2`. | **PRESERVED UNCHANGED** |
| `docs/03-user-flow.md` | One canonical repository User Flow output. | **PASS / COMPLETE** |

The Figma candidate is fully editable and contains no imported screenshot or flattened complete-UI rendering. It remains a candidate until the required read-only design audit, any separately authorized remediation, and final human approval.

## Requirement Traceability

| Phase 02 retained feature / requirement | Canonical Phase 03 task or destination | Evidence classification | Supporting source | Historical artifact where applicable | Historical disposition | New Figma candidate |
| --- | --- | --- | --- | --- | --- | --- |
| Site navigation and orientation | UF-08 shared global orientation and recovery | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§8, 10–11 | `docs/PRIMARY_FLOW.md` §§7, 11; node `44:2` | **NARROWED** to current retained destinations and flow-level accessibility | `61:2` |
| Landing / Home | UF-01 Home entry and orientation | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/00-project-brief.md`; `docs/02-product-definition.md` §§10–11 | `docs/PRIMARY_FLOW.md` §§3–4; node `44:2` | **RETAINED** | `61:2` |
| Catalogue overview and broad browsing | UF-02 Broad Catalogue browsing | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/01-discovery.md`; `docs/02-product-definition.md` §§4, 10–11 | `docs/PRIMARY_FLOW.md` §§4–6; node `44:2` | **NARROWED** by removing refinement paths | `61:2` |
| Product Detail | UF-03 Product Detail review | **FACT** + **HUMAN-APPROVED DESIGN DECISION / ASSUMPTION** | `docs/00-project-brief.md`; `docs/02-product-definition.md` §§3, 10–11 | `docs/PRIMARY_FLOW.md` §§4–8; node `44:2` | **RETAINED** with bounded return state | `61:2` |
| Contact entry points and generic Contact surface | UF-04A Global Contact and UF-04B Product Detail to Contact | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/01-discovery.md`; `docs/02-product-definition.md` §§4–5, 10–11 | `docs/PRIMARY_FLOW.md` §§4, 6–9; node `44:2` | **NARROWED** to reachability; submission removed | `61:2` |
| Information page | Information Flow | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/00-project-brief.md`; `docs/02-product-definition.md` §§10–11 | Historical IA; omitted from node `44:2` | **RETAINED / ADDED TO CANONICAL FLOW** | `61:2` |
| About / Team | About / Team Flow | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/00-project-brief.md`; `docs/02-product-definition.md` §§10–11 | Historical IA; omitted from node `44:2` | **RETAINED / ADDED TO CANONICAL FLOW** | `61:2` |
| Privacy Policy | Privacy Policy Flow | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/00-project-brief.md`; `docs/02-product-definition.md` §§10–11 | Historical IA; omitted from node `44:2` | **RETAINED / ADDED TO CANONICAL FLOW** | `61:2` |
| Explicit system responses and success/failure | All task-anatomy tables | **MASTER WORKFLOW REQUIREMENT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`; approved selection | Incomplete in `docs/PRIMARY_FLOW.md` and node `44:2` | **REMEDIATED** | `61:2` |
| Empty, error, cancellation, permissions, and recovery coverage | Dedicated state and recovery sections | **MASTER WORKFLOW REQUIREMENT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`; approved selections | Historical states retained in `docs/PRIMARY_FLOW.md` | **NARROWED / REMOVED / REPLACED** as documented | `61:2` |

## Human Flow-Direction Selection Record

The following are **HUMAN-APPROVED DESIGN DECISIONS** supplied on October 3, 2026. They are not research findings, observed behavior, validated journeys, analytics, production behavior, or impact evidence.

| Decision | Human-approved selection |
| --- | --- |
| 01 — Canonical artifact | Create `docs/03-user-flow.md` as the one canonical repository output; preserve `docs/PRIMARY_FLOW.md` and node `44:2`. |
| 02 — Primary flow | Home → Catalogue → Product Detail → previous broad Catalogue context or generic Contact; retain direct access to required destinations. |
| 03 — Global orientation | Use one shared orientation layer; do not duplicate every route permutation. |
| 04 — Product Detail return | Return to previous broad Catalogue context when available; broad Catalogue fallback. |
| 05 — Contact success/failure | Success is Contact reached with approved generic content; failure is unreachable or empty Contact. |
| 06 — Contact return/abandonment | Return globally to known origin or navigation; contextual Contact returns to Product Detail; no cancellation transaction. |
| 07 — Informational flows | Represent Information, About / Team, and Privacy Policy as source-required content access and review; cancellation N/A. |
| 08 — Empty/missing content | Use represented-content-unavailable states at Catalogue and Product Detail levels. |
| 09 — Error model | Retain only unavailable content, unreachable destination, missing required information, and broken return/orientation errors. |
| 10 — Alternate paths | Retain only approved broad Catalogue, Product Detail, Contact, informational, and orientation paths. |
| 11 — Screen rationale | Use the approved non-circular source/need rationale for every retained destination. |
| 12 — Figma strategy | Preserve node `44:2`; create a new candidate on `90 — Candidates`; audit and approve separately. |

## Open Questions / Validation Boundary

The following remain **OPEN QUESTIONS** and are not resolved by this flow:

- Actual user needs, behavior, motivations, accessibility needs, and current journeys.
- Whether the source-stated audience is a meaningful basis for real segmentation.
- Real catalogue size, content, product relationships, specifications, pricing, availability, and imagery.
- Whether future evidence supports Category / Collection, Search, Filters, sorting, comparison, or other discovery mechanisms.
- Which represented product information is necessary or sufficient for understanding.
- Contact channel, required content, service boundary, staffing, response, escalation, privacy handling, and operational outcome.
- Whether any product context should be transmitted to Contact; current flow preserves only a conceptual origin relationship.
- Production navigation behavior, browser-history behavior, persistence boundaries, analytics, integrations, data shape, backend behavior, and failure modes.
- Exact component interaction, keyboard, focus, disclosure, menu, dismissal, and responsive behavior; these belong to later eligible phases.
- Legal adequacy and content ownership for Privacy Policy and other informational content.
- Usability, accessibility conformance, task success, conversion, leads, sales, revenue, or product/business impact.

## Phase Exit Boundary

Targeted remediation created the canonical repository User Flow and the new Figma candidate and reconciled the approved Phase 03 direction with current Phase 02 scope. The formal read-only completion audit subsequently passed all mandatory requirements, and final human approval was explicitly provided.

- **CANONICAL REPOSITORY USER FLOW:** PASS.
- **CANONICAL FIGMA CANDIDATE:** `FLOW — 02 Canonical User Flow Candidate`, node `61:2` — approved Phase 03 Figma artifact.
- **HISTORICAL FIGMA EVIDENCE:** `FLOW — 01 Primary Discovery & Support`, node `44:2` — preserved unchanged.
- **HISTORICAL EVIDENCE:** Preserved.
- **READ-ONLY COMPLETION AUDIT:** **PASS**.
- **FINAL HUMAN APPROVAL:** **APPROVED — October 3, 2026**.
- **FINAL PHASE STATUS:** **PASS / COMPLETE**.
- **LAST PHASE PASSING 100%:** Phase 03 — User Flow.
- **NEXT CANONICAL PHASE:** Phase 04 — Information Architecture.
- **PHASE 04 STARTED:** **NO**.
