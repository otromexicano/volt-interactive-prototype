# Phase 04 — Information Architecture

## Canonical Status

- **Canonical phase:** Phase 04 — Information Architecture.
- **Canonical output:** This document is the one canonical repository Information Architecture output required by `docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`.
- **Current state:** **PASS / COMPLETE**.
- **Targeted remediation:** Completed on 2026-10-03 after the formal initial read-only audit and human IA-direction selection checkpoint.
- **Canonical Figma artifact:** `IA — 02 Canonical Information Architecture Candidate`, node `70:2`, on `90 — Candidates`.
- **Completion boundary:** The read-only completion audit re-run passed and final human approval was provided on October 3, 2026.
- **Progression boundary:** Phase 05 — Interaction Contract is the next canonical phase and has not started.
- **Evidence boundary:** This artifact records source-supplied facts, human-approved design decisions, bounded design decisions, assumptions where stated, and open questions. It is not research, card sorting, tree testing, navigation testing, validated findability, an observed mental model, analytics, a production taxonomy, production inventory, production legal architecture, production behavior, or evidence of business outcomes.

## Evidence Classification

| Classification | Meaning in Phase 04 |
| --- | --- |
| **FACT** | Directly supplied by the source brief or observable in an approved artifact. |
| **ASSUMPTION** | A provisional belief requiring validation. It must not govern the current architecture unless separately approved as a design decision. |
| **DESIGN DECISION** | A bounded architectural interpretation grounded in approved scope; not research or observed behavior. |
| **HUMAN-APPROVED DESIGN DECISION** | A Phase 02, Phase 03, or Phase 04 direction explicitly selected by the user. |
| **OPEN QUESTION** | Information not supplied, validated, or approved for the current architecture. |

Unknowns remain unknown. Historical assumptions and prior decisions are preserved for traceability but do not govern current architecture where they conflict with approved scope.

## Approved Scope

### Retained

1. Site navigation and orientation.
2. Home.
3. Catalogue.
4. Product Detail.
5. Contact.
6. Information.
7. About / Team.
8. Privacy Policy.

### Deferred

- **DEFERRED:** Category / Collection.
- **DEFERRED:** Search.
- **DEFERRED:** Filters.

Deferral is explicit traceability, not hidden or active architecture.

### Removed or excluded

- **REMOVED:** Cart.
- **REMOVED:** Contact Request.
- **REMOVED:** Contact fields, validation state, and submission state.
- **OUT OF SCOPE:** Checkout, payment, purchase, accounts, authentication, backend inventory, real inventory, production transactions, real Contact submission, submission feedback, email delivery, support tickets, service-level agreements, and backend handling.

## Canonical Naming

| Canonical label | Current use |
| --- | --- |
| Home | Shared/global destination and orientation entry. |
| Catalogue | Shared/global destination for broad represented product browsing. |
| Product Detail | Contextual destination beneath Catalogue. |
| Contact | Shared/global destination and contextual destination from Product Detail. |
| Information | Shared/global supporting-information destination. |
| About / Team | Shared/global supporting-information destination. |
| Privacy Policy | Shared/global supporting-information destination; footer relationship is optional and supplementary. |

Historical labels—`Shop`, `Shop / Catalogue`, `Support`, `Contact / Support`, `About`, `Privacy`, and `Info`—appear only in historical traceability and disposition records. They are not current canonical labels.

## IA Principles

1. **HUMAN-APPROVED DESIGN DECISION:** All six retained global destinations belong to one shared orientation layer.
2. **HUMAN-APPROVED DESIGN DECISION:** Semantic priority is expressed through two IA-level tiers; tiers do not define visual placement or interaction behavior.
3. **HUMAN-APPROVED DESIGN DECISION:** Product Detail is contextual to Catalogue and is not a seventh global destination.
4. **HUMAN-APPROVED DESIGN DECISION:** Contact is both globally reachable and contextually reachable from Product Detail.
5. **HUMAN-APPROVED DESIGN DECISION:** Privacy Policy is globally reachable; a footer relationship is supplementary and optional.
6. **DESIGN DECISION:** Every retained destination must avoid an architectural dead end by reconnecting to known origin and/or shared orientation.
7. **DESIGN DECISION:** Deferred and removed concepts remain explicit for traceability but must not operate as current hierarchy, navigation, metadata, or state.
8. **DESIGN DECISION:** The architecture defines information relationships without specifying visual navigation components, responsive controls, focus behavior, or implementation mechanics.

## Top-Level Architecture

```text
SHARED GLOBAL ORIENTATION LAYER
├─ Tier 1 — Core task / orientation
│  ├─ Home
│  ├─ Catalogue
│  └─ Contact
└─ Tier 2 — Supporting required information
   ├─ Information
   ├─ About / Team
   └─ Privacy Policy

CONTEXTUAL PRODUCT INFORMATION
└─ Catalogue
   └─ Product Detail
      ├─ Contact
      └─ Prior broad Catalogue context
         └─ Fallback: broad Catalogue
```

This structure does not create a Category parent, Search parent, filter-derived result hierarchy, Cart, checkout, account, or transaction hierarchy.

## Navigation Architecture

### Shared orientation layer

The shared orientation layer provides conceptual reachability to:

- Home;
- Catalogue;
- Contact;
- Information;
- About / Team; and
- Privacy Policy.

Every destination remains part of the same shared set even though the set has two semantic priority tiers.

### IA boundary

This section does not establish:

- header composition;
- menu order or visual position;
- dropdowns, tabs, or hamburger menus;
- responsive navigation controls;
- focus order;
- keyboard behavior;
- hover, pressed, open, or dismissed states; or
- visual prominence.

Those concerns belong to later eligible phases.

## Hierarchy

### Global hierarchy

The six shared destinations are peers in reachability. Tier 1 and Tier 2 describe content priority, not parent/child containment.

### Contextual hierarchy

`Catalogue → Product Detail`

Product Detail belongs contextually beneath Catalogue because a represented product is selected from broad Catalogue browsing. Product Detail does not require Category / Collection, Search, Filters, price, availability, or inventory.

## Sections

The canonical IA contains these architectural sections:

1. Shared orientation.
2. Core task/orientation destinations.
3. Supporting required-information destinations.
4. Contextual product information.
5. Direct-entry orientation and recovery.
6. Deferred and removed architecture.
7. Minimal current metadata.
8. Evidence, source, and historical traceability.

These are information-architecture sections, not page-layout regions or visual components.

## Groups

### Core task / orientation

- Home
- Catalogue
- Contact

### Supporting required information

- Information
- About / Team
- Privacy Policy

### Contextual product information

- Product Detail beneath Catalogue

Contact remains a member of the core global group and also has a contextual relationship from Product Detail. This dual relationship does not create a separate Contact destination or support-case architecture.

## Parent / Child Relationships

| Parent or origin | Child or destination | Relationship | Boundary |
| --- | --- | --- | --- |
| Catalogue | Product Detail | Contextual parent/child relationship established by selection of a represented product. | No Category, Search, Filters, price, availability, or inventory dependency. |
| Product Detail | Contact | Contextual route to the same generic globally reachable Contact destination. | No Contact Request, field, validation, submission, or support-case entity. |
| Product Detail | Prior broad Catalogue context | Approved return relationship when the origin is known. | Preserve only approved broad-Catalogue origin context. |
| Product Detail | Broad Catalogue | Recovery fallback when prior origin is unavailable. | No invented query, filter, category, sorting, or inventory context. |

## Content Priority

### Tier 1 — Core task / orientation

Home, Catalogue, and Contact are the first architectural priority because they provide orientation, the approved broad product-exploration route, and the source-stated Contact goal.

### Tier 2 — Supporting required information

Information, About / Team, and Privacy Policy remain globally reachable source-required destinations. “Supporting” does not mean hidden, optional, inaccessible, or visually subordinate.

### Contextual priority

Product-specific information becomes contextually relevant inside Product Detail after a represented product is selected.

**DESIGN DECISION:** This priority is grounded in approved project scope. It is not a claim about validated user priority, findability, mental models, or observed behavior.

## Global vs Contextual Access

| Destination | Global/shared | Contextual | Current role |
| --- | --- | --- | --- |
| Home | Yes | Recovery/orientation destination | Landing and orientation. |
| Catalogue | Yes | Parent and recovery destination for Product Detail | Broad represented product browsing. |
| Contact | Yes | Yes, from Product Detail | Generic Contact content surface. |
| Information | Yes | None required | Required general information. |
| About / Team | Yes | None required | Required company/team information. |
| Privacy Policy | Yes, required | Footer may supplement | Required privacy-policy content without legal-compliance claims. |
| Product Detail | No | Yes, beneath Catalogue | Represented product information. |

## Direct Entry / Recovery

| Direct-entry destination | Orientation and recovery relationship |
| --- | --- |
| Home | Shared orientation remains available. |
| Catalogue | Shared orientation remains available. |
| Contact | Return to known origin when represented; otherwise use shared orientation. |
| Information | Return to known origin when represented; otherwise use shared orientation. |
| About / Team | Return to known origin when represented; otherwise use shared orientation. |
| Privacy Policy | Return to known origin when represented; otherwise use shared orientation. |
| Product Detail | Return to prior broad Catalogue context when known; fallback to broad Catalogue; shared orientation remains available. |

No retained destination may become an architectural dead end. This does not define browser-history mechanics, menu behavior, or component-level interaction.

## Product Detail Architecture

- **Role:** Present the represented information available for one represented product.
- **Classification:** Contextual destination beneath Catalogue.
- **Entry:** Represented product selection from broad Catalogue; legitimate direct entry remains recoverable.
- **Exit:** Prior broad Catalogue context, broad Catalogue fallback, generic Contact, or shared orientation.
- **Persistent conceptual context:** represented product identity and approved origin/return context while the Product Detail context is active.
- **Missing-content boundary:** represented Product Detail content availability may be recorded without inventing production product metadata.
- **Excluded dependencies:** Category, Search, Filters, query, filter state, price, availability, inventory, account, Cart, purchase, and backend data.

## Contact Architecture

- **Global access:** Contact is reachable through the shared orientation layer.
- **Contextual access:** Contact is reachable from Product Detail.
- **Role:** Generic Contact content surface.
- **Success boundary inherited from Phase 03:** Contact content is reached and presented.
- **Return:** Known origin when represented; Product Detail for contextual entry; otherwise shared orientation or broad Catalogue recovery as applicable.

The canonical architecture does not include:

- Contact Request;
- Contact fields or required fields;
- validation;
- form state;
- submission processing;
- success confirmation;
- retry;
- email delivery;
- support tickets;
- service-level agreements; or
- backend handling.

## Information Architecture

- **Role:** Source-required general information destination.
- **Classification:** Tier 2 shared/global destination.
- **Entry:** Shared orientation or legitimate direct entry.
- **Recovery:** Known origin when represented; otherwise shared orientation.
- **Boundary:** No purpose, behavior, or outcome is invented beyond access to required content.

## About / Team Architecture

- **Role:** Source-required company/team information destination.
- **Classification:** Tier 2 shared/global destination.
- **Entry:** Shared orientation or legitimate direct entry.
- **Recovery:** Known origin when represented; otherwise shared orientation.
- **Boundary:** No trust outcome, employee-contact function, or organizational claim is inferred.

## Privacy Policy Architecture

- **Required:** Shared/global orientation access.
- **Optional:** Supplementary footer relationship.
- **Not required for Phase 04 completion:** Footer presence.
- **Recovery:** Known origin when represented; otherwise shared orientation.

The Privacy Policy destination does not imply legal adequacy, consent handling, data collection, production privacy implementation, validated findability, or user expectation.

## Search / Filter Structure

The Master Workflow requires search/filter structure to be addressed. The approved current structure is:

| Concept | Status | Current treatment |
| --- | --- | --- |
| Category / Collection | **DEFERRED** | Not part of current committed hierarchy or navigation. |
| Search | **DEFERRED** | Not part of current committed navigation or page relationships. |
| Filters | **DEFERRED** | Not part of current committed navigation, hierarchy, or metadata. |
| Search query | **DEFERRED** | No current query entity, result model, recovery, or persistence. |
| Filter state | **DEFERRED** | No current filter entity, result model, reset behavior, or persistence. |
| Category membership | **DEFERRED** | No current taxonomy or grouping assignment. |

These concepts are deferred, not hidden until needed. Their historical presence does not establish current approval.

## Metadata Boundary

### Canonical current metadata

Phase 04 may record only:

- destination identity;
- canonical destination label;
- destination role;
- global/shared or contextual classification;
- parent/context relationship;
- valid entry relationships;
- valid exit/recovery relationships;
- retained/deferred/removed disposition;
- evidence classification;
- supporting source;
- represented product identity;
- represented Product Detail content availability;
- approved origin/return context; and
- conceptual current destination/orientation state.

### Open questions / deferred or excluded metadata

| Metadata concept | Status |
| --- | --- |
| Real catalogue taxonomy | **OPEN QUESTION / UNKNOWN** |
| Category membership | **DEFERRED** with Category / Collection |
| Product price | **OPEN QUESTION / UNKNOWN**; removed from current committed Phase 04 metadata only |
| Product availability | **OPEN QUESTION / UNKNOWN**; removed from current committed Phase 04 metadata only |
| Production inventory | **OUT OF SCOPE** |
| Search query | **DEFERRED** with Search |
| Filter state | **DEFERRED** with Filters |
| Contact Request | **REMOVED** from committed architecture |
| Contact fields | **REMOVED** from committed architecture |
| Validation state | **REMOVED** from committed architecture |
| Submission state | **REMOVED** from committed architecture |
| Production Privacy/legal structure | **OPEN QUESTION / UNKNOWN** |

Removing price or availability from current Phase 04 metadata does not mean either is permanently forbidden, disproven, or known not to exist. Future product/content status requires separate evidence and approval.

## Page Relationships

### Approved primary relationship

```text
Home
→ Catalogue
→ Product Detail
→ either prior broad Catalogue context
   or generic Contact
```

### Approved shared relationships

- Home → Catalogue.
- Home → Contact.
- Any retained destination → shared orientation → another retained shared destination.
- Shared orientation → Information.
- Shared orientation → About / Team.
- Shared orientation → Privacy Policy.
- Footer → Privacy Policy may exist as an optional supplementary relationship.

### Approved contextual relationships

- Catalogue → Product Detail.
- Product Detail → Contact.
- Product Detail → prior broad Catalogue context.
- Product Detail → broad Catalogue fallback.

No page relationship reintroduces Category, Search, Filters, Cart, checkout, account, inventory, purchasing, or Contact submission.

## What Information Does the User Need First?

At the IA level:

1. understandable current location or entry context;
2. Home access for orientation;
3. Catalogue access for approved product exploration; and
4. Contact access for the approved Contact goal.

This is a **DESIGN DECISION** grounded in approved scope, not validated user priority.

## What Belongs Together?

- **Core task/orientation:** Home, Catalogue, Contact.
- **Supporting required information:** Information, About / Team, Privacy Policy.
- **Contextual product information:** Product Detail beneath Catalogue.
- **Dual Contact relationship:** Contact remains globally reachable and contextually reachable from Product Detail.

These are semantic IA groups, not visual menu groups.

## What Should Be Hidden Until Needed?

No approved global destination is structurally hidden from the shared orientation layer.

Product-specific information is contextual inside Product Detail and becomes relevant after selection of a represented product.

Category / Collection, Search, Filters, Cart, and Contact submission architecture are deferred, removed, or excluded—not hidden.

## What Should Remain Persistent?

At the conceptual IA level only:

- shared orientation access;
- current-destination context;
- originating broad Catalogue context during a Product Detail excursion when known;
- represented product identity while Product Detail is active; and
- known origin when moving from Product Detail to Contact.

The architecture does not claim persistence for Search queries, Filter state, Category state, Cart, inventory, Contact fields, backend data, browser history, cross-session state, or analytics-derived behavior.

## Deferred / Removed Architecture

| Concept | Disposition | Canonical consequence |
| --- | --- | --- |
| Category / Collection | **DEFERRED** | No hierarchy, navigation, membership metadata, or state. |
| Search | **DEFERRED** | No utility, query entity, result model, recovery, or persistence. |
| Filters | **DEFERRED** | No control group, filter state, result model, reset behavior, or persistence. |
| Cart | **REMOVED** | No destination, utility, indicator, relationship, or state. |
| Contact Request | **REMOVED** | No entity or workflow. |
| Contact validation | **REMOVED** | No fields, required state, validation, or errors. |
| Submission states | **REMOVED** | No submission, confirmation, failure, retry, or delivery behavior. |
| Price | **REMOVED FROM CURRENT PHASE 04 METADATA** | Future product/content status remains an **OPEN QUESTION**. |
| Availability | **REMOVED FROM CURRENT PHASE 04 METADATA** | Future product/content status remains an **OPEN QUESTION**. |
| Production inventory | **OUT OF SCOPE** | No inventory entity or behavior. |
| Checkout/payment/purchase/accounts/authentication | **REMOVED / OUT OF SCOPE** | No transactional or account hierarchy. |

## Historical Disposition

| Historical concept | Disposition | Current canonical treatment |
| --- | --- | --- |
| Home | **RETAINED** | Shared/global orientation destination. |
| Shop / Catalogue | **NARROWED** | `Catalogue`; broad browsing only. |
| Product Detail | **NARROWED** | Contextual child of Catalogue; no Category/Search/Filters dependency. |
| Support / Contact | **NARROWED** | `Contact`; generic global and Product Detail relationship; no support-case architecture. |
| Information | **RETAINED** | Shared/global supporting-information destination. |
| About | **NARROWED** | `About / Team`; shared/global destination. |
| Privacy | **NARROWED** | `Privacy Policy`; shared/global required; footer supplementary. |
| Category / Collection | **DEFERRED** | Preserved historically; excluded from current committed architecture. |
| Search | **DEFERRED** | Preserved historically; excluded from current committed architecture. |
| Filters | **DEFERRED** | Preserved historically; excluded from current committed architecture. |
| Cart | **REMOVED** | No current architecture or state. |
| Contact Request | **REMOVED** | No current entity or workflow. |
| Contact validation | **REMOVED** | No current field or validation model. |
| Submission states | **REMOVED** | No current submission behavior. |
| Price | **REMOVED FROM CURRENT PHASE 04 METADATA** | Future status remains an **OPEN QUESTION**. |
| Availability | **REMOVED FROM CURRENT PHASE 04 METADATA** | Future status remains an **OPEN QUESTION**. |
| Query state | **DEFERRED** | Deferred with Search. |
| Filter state | **DEFERRED** | Deferred with Filters. |

## Historical Preservation

- `docs/INFORMATION_ARCHITECTURE.md` remains unchanged as historical repository evidence.
- `docs/PRIMARY_FLOW.md` remains unchanged as historical repository evidence.
- Figma node `39:2`, `IA — 01 Product Architecture`, remains unchanged.
- Figma node `44:2`, `FLOW — 01 Primary Discovery & Support`, remains unchanged.
- Figma node `61:2`, `FLOW — 02 Canonical User Flow Candidate`, remains unchanged as approved Phase 03 evidence.
- Figma page `99 — Archive` remains unchanged.
- Historical labels, assumptions, conflicts, and approval records remain visible rather than being silently normalized.

## Figma Traceability

| Artifact | Role | Status |
| --- | --- | --- |
| `39:2` — `IA — 01 Product Architecture` on `02 — IA & Flows` | Historical IA evidence containing prior scope and naming. | **PRESERVED UNCHANGED / NON-CANONICAL FOR CURRENT SCOPE** |
| `44:2` — `FLOW — 01 Primary Discovery & Support` on `02 — IA & Flows` | Historical User Flow evidence. | **PRESERVED UNCHANGED** |
| `61:2` — `FLOW — 02 Canonical User Flow Candidate` on `90 — Candidates` | Approved Phase 03 User Flow evidence. | **PRESERVED UNCHANGED** |
| `70:2` — `IA — 02 Canonical Information Architecture Candidate` on `90 — Candidates` | Accepted canonical Phase 04 Figma artifact created during targeted remediation. | **APPROVED / CANONICAL PHASE 04 FIGMA ARTIFACT** |
| `99 — Archive` | Protected historical archive page. | **PRESERVED UNCHANGED** |

Node `70:2` is an editable Figma frame composed of live auto-layout frames and text layers. It is not a screenshot, image-fill workaround, website mockup, navigation component, wireframe, or prototype screen.

## Requirement Traceability

| Phase 02 retained feature / requirement | Phase 03 task or destination | Phase 04 destination / relationship | Evidence classification | Supporting source | Historical artifact | Disposition | New Figma candidate |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Site navigation and orientation | UF-08 shared navigation and recovery | Shared orientation layer; direct-entry recovery | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§8, 10–11; `docs/03-user-flow.md` §§Global Navigation, Recovery | `docs/INFORMATION_ARCHITECTURE.md`; `39:2` | **NARROWED** | `70:2` |
| Home | UF-01 Home entry and orientation | Tier 1 global Home | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` UF-01 | Historical Home area; `39:2` | **RETAINED** | `70:2` |
| Catalogue | UF-02 broad Catalogue browsing | Tier 1 global Catalogue; parent context for Product Detail | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` UF-02 | Historical Shop/Catalogue; `39:2` | **NARROWED** | `70:2` |
| Product Detail | UF-03 Product Detail review | Contextual child of Catalogue; return or Contact relationships | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` UF-03 | Historical Product Detail; `39:2` | **NARROWED** | `70:2` |
| Contact | UF-04A global Contact; UF-04B Product Detail to Contact | Tier 1 global Contact plus Product Detail contextual relationship | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` Contact Flow | Historical Support/Contact and Contact Request; `39:2` | **NARROWED** | `70:2` |
| Information | Information Flow | Tier 2 global Information | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` Information Flow | Historical Information; `39:2` | **RETAINED** | `70:2` |
| About / Team | About / Team Flow | Tier 2 global About / Team | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` About / Team Flow | Historical About; `39:2` | **NARROWED** | `70:2` |
| Privacy Policy | Privacy Policy Flow | Tier 2 global Privacy Policy; optional footer supplement | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§10–11; `docs/03-user-flow.md` Privacy Policy Flow; Phase 04 Decision 01 | Historical Privacy/footer model; `39:2` | **NARROWED** | `70:2` |
| Category / Collection | Excluded from committed Phase 03 | Explicit deferred structure; no active hierarchy | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §10; `docs/03-user-flow.md` Approved Scope | Historical Category entity/hierarchy; `39:2` | **DEFERRED** | `70:2` |
| Search | Excluded from committed Phase 03 | Explicit deferred structure; no query or result model | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §10; `docs/03-user-flow.md` Approved Scope | Historical Search utility/query; `39:2` | **DEFERRED** | `70:2` |
| Filters | Excluded from committed Phase 03 | Explicit deferred structure; no filter state or result model | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §10; `docs/03-user-flow.md` Approved Scope | Historical Filter state; `39:2` | **DEFERRED** | `70:2` |
| Cart | Removed from Phase 02 | No current destination, utility, relationship, or state | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §10; `docs/03-user-flow.md` Approved Scope | Historical optional Cart record | **REMOVED** | `70:2` |
| Generic non-submission Contact boundary | No Contact submission | No Contact Request, fields, validation, or submission metadata | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md` §§5, 7; `docs/03-user-flow.md` Contact Flow | Historical Contact Request/form states; `39:2` | **REMOVED / NARROWED** | `70:2` |

## Human IA-Direction Selection Record

The following selections were explicitly approved by the user on 2026-10-03. They are **HUMAN-APPROVED DESIGN DECISIONS**, not research or validation findings.

| Decision | Approved selection | Canonical consequence |
| --- | --- | --- |
| 01 — Privacy Policy placement | Option B — required globally; footer supplementary | Privacy Policy remains in shared orientation. Footer access is optional and not required for Phase 04 completion. |
| 02 — Global grouping and content priority | Option B — one shared set with two IA-level priority tiers | Tier 1: Home, Catalogue, Contact. Tier 2: Information, About / Team, Privacy Policy. Product Detail remains contextual. |
| 03 — Metadata boundary | Option A — minimal current-scope metadata | Only destination, relationship, recovery, disposition, evidence, represented product identity, represented Product Detail content availability, and approved orientation context metadata are canonical. Product availability remains **OPEN QUESTION / UNKNOWN** and is excluded from current Phase 04 metadata. |
| Canonical artifact strategy | Approved | Create this new canonical document; preserve the historical IA unchanged. |
| Figma strategy | Approved | Preserve `39:2`, `44:2`, `61:2`, and `99 — Archive`; create a new candidate on `90 — Candidates`. |

## Open Questions / Validation Boundary

The following remain **OPEN QUESTIONS** and are not resolved by this architecture:

- actual user needs, behavior, mental models, terminology expectations, and accessibility needs;
- whether the source-stated audience is a meaningful real-world segment;
- real catalogue size, taxonomy, categories, relationships, and product-content model;
- whether future evidence supports Category / Collection, Search, Filters, sorting, comparison, price, or availability;
- which represented Product Detail information is necessary or sufficient;
- production Contact channel, staffing, operational outcome, privacy handling, and service model;
- production Privacy/legal structure, legal adequacy, data collection, consent, and content ownership;
- production navigation behavior, browser-history behavior, persistence, analytics, integrations, and backend data;
- validated labeling, findability, comprehension, usability, task success, or business outcomes; and
- detailed component interactions, focus behavior, keyboard behavior, menu behavior, responsive controls, and motion, which belong to later eligible phases.

## Phase Exit Boundary

Targeted remediation created the canonical repository Information Architecture and the current-scope Figma artifact and reconciled approved Phase 04 decisions with canonical Phase 02 and Phase 03 scope. The formal read-only completion audit re-run subsequently passed every mandatory checkpoint, and final human approval was explicitly provided.

- **CANONICAL REPOSITORY IA CREATED:** YES.
- **CANONICAL PHASE 04 FIGMA ARTIFACT:** `IA — 02 Canonical Information Architecture Candidate`, node `70:2`.
- **HISTORICAL IA FIGMA EVIDENCE:** `IA — 01 Product Architecture`, node `39:2` — preserved unchanged.
- **HISTORICAL USER FLOW FIGMA EVIDENCE:** `FLOW — 01 Primary Discovery & Support`, node `44:2` — preserved unchanged.
- **APPROVED PHASE 03 FIGMA EVIDENCE:** `FLOW — 02 Canonical User Flow Candidate`, node `61:2` — preserved unchanged.
- **HISTORICAL EVIDENCE PRESERVED:** YES.
- **TARGETED REMEDIATION:** COMPLETE.
- **READ-ONLY COMPLETION AUDIT:** **PASS**.
- **FINAL HUMAN APPROVAL:** **APPROVED — October 3, 2026**.
- **FINAL PHASE STATUS:** **PASS / COMPLETE**.
- **LAST PHASE PASSING 100%:** Phase 04 — Information Architecture.
- **NEXT CANONICAL PHASE:** Phase 05 — Interaction Contract.
- **PHASE 05 STARTED:** NO.

This completion record closes Phase 04 and does not begin Phase 05.
