# Phase 04 — Primary Flow

## Status and evidence boundary

This is the canonical Phase 04 primary-flow record for Volt. It defines the bounded critical path before wireframes, product screens, final UI, responsive layouts, or implementation technology are selected.

- **Current phase:** PHASE 04 — PRIMARY FLOW
- **Status:** COMPLETE / APPROVED
- **Canonical sources:** [BRIEF.md](BRIEF.md), [UX_ASSUMPTIONS.md](UX_ASSUMPTIONS.md), and [INFORMATION_ARCHITECTURE.md](INFORMATION_ARCHITECTURE.md)
- **Repository:** `volt-interactive-prototype`
- **Figma file:** [Volt — E-commerce UI & Interactive Prototype](https://www.figma.com/design/UIEx2VVwyPeGFUzwkh2dkn/Volt-%E2%80%94-E-commerce-UI---Interactive-Prototype)
- **Figma summary:** `FLOW — 01 Primary Discovery & Support` on `02 — IA & Flows`

Classification rules used throughout:

- **FACT:** Directly supplied by the source brief or observable in an approved artifact.
- **ASSUMPTION:** A provisional belief requiring validation.
- **DESIGN DECISION:** A chosen design interpretation or project constraint, with its status stated.
- **OPEN QUESTION:** Information that has not been supplied or validated.
- **ILLUSTRATIVE:** An example used only to explain structure; not real Volt content, inventory, taxonomy, or behavior.

No path below is observed behavior, validated research, measured task performance, production usage, or evidence of business impact. The flow specifies intended prototype interaction only.

## 1. Flow objective and boundaries

- **FACT — SOURCE BRIEF:** Volt should make contacting the company easy and encourage catalogue exploration.
- **DESIGN DECISION — WORKING:** The critical path connects product discovery, product understanding, and contextual human support.
- **DESIGN DECISION — PROJECT SCOPE:** The flow ends when a visitor has explored and sufficiently understood a represented product, or has reached the support/contact path for more help.
- **DESIGN DECISION — PHASE BOUNDARY:** This phase defines movement, decisions, recovery, and context continuity. It does not create screens, wireframes, visual branding, components, responsive layouts, or implementation specifications.

Authentication, accounts, payments, checkout, backend commerce, real inventory, order confirmation, and production transactions remain out of scope.

## 2. Working user intent

> A visitor wants to explore everyday electronics, understand whether a product fits their needs, and reach human support easily if they need additional help.

**Classification:** WORKING USER INTENT — REQUIRES VALIDATION.

This is an **ASSUMPTION** used to organize the prototype. It is not an observation of shopping behavior or a research finding.

## 3. Entry points

### Primary

- **Home:** communicates the working Volt value proposition and provides clear access to product discovery and support.

### Secondary / possible

- Shop / Catalogue
- Category / Collection
- Product Detail through internal navigation
- Support / Contact

**DESIGN DECISION — WORKING:** Home is the canonical start for demonstrating the complete critical path. Secondary entries may demonstrate shorter architectural paths without implying external marketing, advertising, referral, or SEO behavior.

## 4. Primary critical path

### 01 — Land on Home

The visitor receives the Volt value proposition and clear access to product discovery.

**Key action:** enter Shop / Catalogue, or use a discovery entry that leads into it.

### 02 — Enter Shop / Catalogue

The visitor begins browsing the represented product set.

**Context established:** current discovery origin and catalogue state.

### 03 — Refine discovery

The visitor may:

- browse broadly;
- browse an illustrative category / collection;
- search; or
- apply relevant catalogue filters.

**DESIGN DECISION — WORKING:** Refinement is optional. The flow must also support direct browsing without requiring a category, query, or filter.

### 04 — Review product results

The visitor scans available **ILLUSTRATIVE** products and represented differentiators.

**Decision:** select a product or continue browsing/refining.

### 05 — Select product

The visitor opens Product Detail for a selected represented product.

**Context established:** selected product and useful origin from the catalogue, category, filtered set, or search results.

### 06 — Understand product

The visitor reviews available product information:

- product imagery;
- product name;
- price, if represented;
- key benefits;
- relevant specifications; and
- supporting product information.

All product and price content remains deterministic mock or **ILLUSTRATIVE** unless a later approved source replaces it.

### 07 — Decision: enough information?

**Yes →** product evaluation is complete within the bounded prototype.

**No →** the visitor enters contextual Support / Contact.

This decision is a flow model, not a claim about observed visitor behavior or support effectiveness.

### 08 — Contact / Support

The visitor reaches an appropriate support/contact path. When entered from Product Detail, the selected-product relationship should remain understandable where conceptually possible.

The support channel, service model, response promise, and information actually transmitted remain **OPEN QUESTIONS**.

### 09 — Complete bounded prototype task

Completion occurs when the visitor has explored a product and either:

1. understood it sufficiently within prototype scope; or
2. reached Support / Contact for additional assistance.

Completion does **not** mean purchase, checkout, payment, account creation, order submission, order confirmation, support resolution, or a production transaction.

## 5. Meaningful decision points

| Decision | Available paths | Flow consequence |
| --- | --- | --- |
| Browse broadly or refine? | Continue with the current result set; choose a category; search; or filter. | Changes the represented result context, not the overall task sequence. |
| Category or search? | Enter an illustrative category/collection or submit a query. | Establishes category or query context for results and return behavior. |
| Apply a filter or continue browsing? | Add a relevant filter, clear/modify criteria, or scan the current set. | Updates active criteria and the visible result context. |
| Select a product or continue browsing? | Open Product Detail or remain in discovery. | Establishes selected-product context or preserves the current result state. |
| Enough information or need help? | Complete product evaluation or enter contextual support. | Produces one of the two valid bounded completion outcomes. |
| Return or continue product exploration? | Return to the prior catalogue context or continue within the current product information. | Preserves orientation and avoids unnecessary re-entry. |

These are the material decisions for the critical path. Minor control-level choices are deferred to wireframes and interaction design.

## 6. Alternate paths

### A — Direct support

`Home → Support / Contact`

This preserves the source brief’s emphasis on easy contact. It is a valid short path but does not replace the primary discovery path.

### B — Category discovery

`Home → Shop → Category / Collection → Product results → Product Detail`

Category labels and membership remain **ILLUSTRATIVE** until a real taxonomy is supplied.

### C — Search-led discovery

`Home or Shop → Search → Results → Product Detail`

Search scope, matching, suggestions, ranking, and sorting remain **OPEN QUESTIONS**.

### D — Filter-led discovery

`Shop → Apply filter → Results → Product Detail`

The specific filter set and its relationship to product attributes remain **OPEN QUESTIONS**.

### E — Product to support

`Product Detail → Contextual Support → Contact`

The visitor should retain an understandable relationship to the selected product. What data, if any, is transmitted remains an **OPEN QUESTION**.

## 7. Return and recovery paths

| Current context | Expected return or recovery | Context expectation |
| --- | --- | --- |
| Product Detail | Return to the prior catalogue, category, filtered, or search-results context. | Preserve the represented query, category, active filters, and result context where applicable. |
| Contextual Support / Contact | Return to the originating Product Detail when the support path began there. | Restore understandable selected-product context without claiming backend persistence. |
| Empty catalogue results | Modify or clear the search/filter criteria. | Keep criteria visible and understandable until the visitor changes or clears them. |
| Search results | Revise or clear the query, or return to broader browsing. | Avoid trapping the visitor in an unproductive result state. |
| Filtered results | Modify or clear filters, or return to the unfiltered catalogue. | Communicate active state textually and provide an explicit reset. |
| Mobile navigation | Dismiss or select a destination and return to the prior content context when no destination is chosen. | Opening and closing navigation should not silently reset the active task. |

**DESIGN DECISION — WORKING:** Every represented state should have an understandable forward action and an understandable return or reset. Browser and implementation mechanics are deferred.

## 8. Context that should persist

### Catalogue context

- search query;
- selected category / collection;
- active filters; and
- represented result context.

This context should persist through a Product Detail excursion when the visitor returns to the originating discovery state. Explicit clear/reset, a new incompatible discovery context, or prototype restart may intentionally reset it.

### Product context

- selected product;
- origin of navigation where useful; and
- opened product-information sections during the current product visit, if represented later.

Selecting another product, intentionally leaving product context, or restarting the prototype may reset this state.

### Support context

When Support / Contact is entered from Product Detail, the relationship to the selected product should remain understandable. The support destination may acknowledge the origin conceptually, but actual data transfer, prefilled fields, and submission behavior remain **OPEN QUESTIONS**.

**DESIGN DECISION — PROTOTYPE INTERACTION INTENT:** Preserve task-relevant state long enough to support return and recovery. This is not a claim of backend, account, cross-session, or production persistence.

## 9. Error, empty, and unavailable states

### Empty catalogue results

- **Cause:** A represented search query or filter combination produces no visible results.
- **Treatment:** State clearly that no results match the current criteria and keep those criteria understandable.
- **Recovery:** Modify or clear the query/filters and return to a useful result set or broad catalogue.

### Invalid contact input

- **Cause:** A represented required field is incomplete or invalid.
- **Treatment:** Provide clear inline guidance associated with the relevant field; do not rely on color alone.
- **Recovery:** Correct the input and retry the simulated submission.

Required fields and submission outcome remain **OPEN QUESTIONS**. Any later submission behavior must remain explicitly simulated unless a real service is approved.

### Missing product information

- **Cause:** A product attribute or content value is not supplied for the represented product.
- **Treatment:** Use an explicit unavailable or missing-content state rather than inventing data.
- **Recovery:** Continue with available product information or enter contextual support if clarification is needed.

### Missing product image

- **Cause:** A represented product image is not available.
- **Treatment:** Use a defined, accessible fallback later; do not fabricate a product image as factual content.
- **Recovery:** Continue to product information without losing product identity or access to support.

### Navigation recovery

At every represented stage, provide clear current-location cues and a predictable return, dismissal, clear, or reset path. Do not introduce backend outages, inventory failures, payment failures, or checkout errors; those systems are outside the prototype.

## 10. Completion criteria

The Phase 04 primary flow is complete when the bounded prototype plan demonstrates:

- entry into Volt;
- catalogue discovery;
- refinement or continued broad browsing;
- product-result review and selection;
- product understanding;
- contextual support access when needed; and
- meaningful return, reset, and recovery behavior.

Two completion outcomes are valid:

- **Outcome A — Product understood:** Product evaluation is complete within prototype scope.
- **Outcome B — Support reached:** The visitor reaches the appropriate support/contact path for additional help.

No checkout, payment, account, order, support-resolution, or transaction completion is required.

## 11. Accessibility flow requirements

**DESIGN DECISION — TARGET:** Volt targets WCAG 2.2 AA. Compliance is not claimed in this phase.

- All critical actions must be keyboard reachable and operable.
- Focus progression must follow a logical task and reading order.
- Links and buttons must have clear, distinguishable purposes.
- Active query, category, and filter state must be communicated textually and not by color alone.
- Validation instructions and errors must be programmatically associated with their fields.
- Error recovery must not erase valid input without an explicit reason.
- Return, clear, reset, and dismissal paths must be predictable.
- Narrow-screen navigation must have a clear entry, current state, and exit.
- Focus must move appropriately into overlays and return to a sensible trigger or next context when they close, if overlays are selected later.
- Dynamic result, validation, or status changes must be perceivable through an appropriate accessible mechanism selected in later design.
- Responsive reflow must preserve logical reading, focus, and task order.

These are interaction requirements for later design and audit, not an accessibility result.

## 12. Responsive flow continuity

The conceptual task sequence remains stable across supported widths:

`Discover → Refine → Select → Understand → Support if needed`

Responsive design may later change the presentation of navigation, filters, search, product lists, Product Detail, and support entry points. It must not remove necessary actions, silently discard task-relevant context, or change the meaning of the two completion outcomes.

No breakpoint, grid, component pattern, drawer, sheet, overlay, content order, or final responsive adaptation is selected in this phase.

## 13. Open questions carried forward

The following remain **OPEN QUESTIONS**:

1. Real catalogue size, product content, category taxonomy, and product relationships.
2. Search scope, matching, suggestions, ranking, sorting, and no-results rules.
3. Which filters are meaningful and how they map to legitimate product attributes.
4. Which product information is necessary for sufficient understanding.
5. Whether comparison is needed; it is not part of the current critical path.
6. Support channel, service boundary, response expectation, and escalation path.
7. Whether contact is form-only or multi-channel and which inputs are required.
8. What product or discovery context, if any, support receives.
9. Which simulated contact success/failure states later prototype coverage requires.
10. Exact state-reset behavior after deliberate navigation, viewport changes, and prototype restart.

These questions do not block documenting the bounded critical path, but they must not be silently resolved in wireframes.

## 14. Figma flow artifact

`FLOW — 01 Primary Discovery & Support` on `02 — IA & Flows` summarizes:

```text
ENTRY
  ↓
DISCOVERY
  ↓
REFINEMENT
  ↓
PRODUCT SELECTION
  ↓
PRODUCT UNDERSTANDING
  ↓
DECISION: ENOUGH INFORMATION?
  ↙                         ↘
ENOUGH INFO                NEED HELP
  ↓                         ↓
COMPLETE                   SUPPORT
                            ↓
                           COMPLETE
```

The artifact also shows the five alternate paths and concise recovery loops. It is a neutral documentation diagram, not a product screen or wireframe. The approved `IA — 01 Product Architecture` remains unchanged.

## 15. Traceability and phase boundary

| Requirement | Canonical section | Figma summary |
| --- | --- | --- |
| Entry and working user intent | Sections 2–3 | Entry and intent annotation |
| Primary critical path and decisions | Sections 4–5 | Main discovery/support flow |
| Alternate paths | Section 6 | Alternate-path summary |
| Return and recovery | Sections 7 and 9 | Recovery/return summary |
| Persistent context | Section 8 | Context-preservation summary |
| Completion | Section 10 | Two bounded completion outcomes |
| Accessibility and responsive continuity | Sections 11–12 | Constraint summary |
| Claim boundary and unresolved conditions | Status boundary and Section 13 | Evidence note and open-question boundary |

- **Phase 01:** COMPLETE / APPROVED — [BRIEF.md](BRIEF.md)
- **Phase 02:** COMPLETE / APPROVED — [UX_ASSUMPTIONS.md](UX_ASSUMPTIONS.md)
- **Phase 03:** COMPLETE / APPROVED — [INFORMATION_ARCHITECTURE.md](INFORMATION_ARCHITECTURE.md) and `IA — 01 Product Architecture`
- **Phase 04:** COMPLETE / APPROVED — this document and `FLOW — 01 Primary Discovery & Support`
- **Next phase:** Wireframes. No wireframe or product screen is created in this phase.

This primary flow is a working design decision subject to later human review when open questions receive evidence. It does not establish observed behavior, validated usability, measured task completion, support effectiveness, conversion impact, production requirements, or completed WCAG conformance.
