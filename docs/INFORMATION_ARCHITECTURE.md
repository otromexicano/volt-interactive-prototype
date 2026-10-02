# Phase 03 — Information Architecture

## Status and evidence boundary

This is the canonical Phase 03 information-architecture record for Volt. It defines the working product structure before primary flows, wireframes, final UI, responsive layouts, or implementation technology are selected.

- **Current phase:** PHASE 03 — INFORMATION ARCHITECTURE
- **Status:** COMPLETE / APPROVED
- **Canonical sources:** [BRIEF.md](BRIEF.md) and [UX_ASSUMPTIONS.md](UX_ASSUMPTIONS.md)
- **Repository:** `volt-interactive-prototype`
- **Figma file:** [Volt — E-commerce UI & Interactive Prototype](https://www.figma.com/design/UIEx2VVwyPeGFUzwkh2dkn/Volt-%E2%80%94-E-commerce-UI---Interactive-Prototype)
- **Figma summary:** `IA — 01 Product Architecture` on `02 — IA & Flows` — node `39:2`

Classification rules used throughout:

- **FACT:** Directly supplied by the source brief or observable in an approved artifact.
- **ASSUMPTION:** A provisional belief requiring validation.
- **DESIGN DECISION:** A chosen design interpretation or project constraint, with its status stated.
- **OPEN QUESTION:** Information that has not been supplied or validated.
- **ILLUSTRATIVE:** An example used only to explain structure; not real Volt content, inventory, or taxonomy.

No structure below is validated research, production data, a backend schema, or evidence of user behavior. Product and content data will be deterministic mock or illustrative content unless a later approved source replaces it.

## 1. Architecture principles

- **FACT — SOURCE BRIEF:** Contacting the company is the primary stated goal; catalogue exploration is secondary.
- **DESIGN DECISION — WORKING:** Product discovery remains the central shopping structure while support is available globally and in relevant product contexts.
- **DESIGN DECISION — PROJECT SCOPE:** The architecture supports a bounded interactive browser prototype. Authentication, accounts, payments, checkout, backend commerce, real inventory, and production transactions remain out of scope.
- **DESIGN DECISION — CONTENT INTEGRITY:** Unknown catalogue, category, product, price, availability, and support details are not treated as facts.
- **DESIGN DECISION — PHASE BOUNDARY:** This phase defines information relationships and state boundaries only. It does not define final page layouts, visual styling, responsive breakpoints, components, or implementation technology.

## 2. Major product areas

| Product area | Purpose | Information ownership | Working relationship |
| --- | --- | --- | --- |
| **Home** | Entry point for value proposition, featured discovery, and support access. | Source/content with UI-derived navigation context. | Links into Shop, About, and Support; may surface selected discovery entry points without claiming real merchandising logic. |
| **Shop / Catalogue** | Browse and explore the represented product set. | Source/content plus user-created filters/search and UI-derived results. | Parent of category/collection and product-list structures; links to Product Detail and contextual support. |
| **Category / Collection** | Group related products and support more focused browsing. | Source/content; actual taxonomy remains unknown. | Child of Shop and parent/context for a product list. Category examples, if used later, must be marked **ILLUSTRATIVE**. |
| **Product Detail** | Understand an individual represented product and evaluate fit. | Source/content plus UI-derived selected-product and disclosure state. | Reached from discovery results; relates product imagery, attributes, price, and contextual support. |
| **About / Team** | Provide the company/about-team content requested by the source brief. | Source/content. | Primary navigation destination; also available through footer information architecture. |
| **Contact / Support** | Make company contact easy in line with the primary source goal. | Source/content plus user-created contact input and UI-derived validation state. | Available globally and contextually without replacing Shop or Product Detail. |
| **Information** | Hold general informational content required by the source brief. | Source/content. | Primarily exposed through footer/information navigation unless later evidence justifies top-level prominence. |
| **Privacy** | Hold privacy-policy content required by the source brief. | Source/content. | Footer/information destination; may be referenced from contact-form context if a form is represented. |

No additional major area is added merely to simulate a larger commerce platform.

## 3. Navigation model

### Primary navigation

**DESIGN DECISION — WORKING:** Home → Shop → About → Support.

These labels favor understandable destinations over internal business terminology. “Support” represents the persistent destination; “Contact” may be the action label when the action specifically opens or navigates to contact.

### Utility navigation

| Utility | Working role | Boundary |
| --- | --- | --- |
| **Search** | Direct product-discovery entry point. | Search scope, matching behavior, suggestions, and result ranking remain open. |
| **Contact** | Direct action into the support/contact structure. | Channel and submission behavior remain open. |
| **Cart indicator** | Optional visual prototype element only if later approved as useful context. | No real cart, checkout, payment, persistence, or transaction behavior. Inclusion remains an **OPEN QUESTION**. |
| **Menu on narrow screens** | Compressed access to the primary and necessary utility destinations. | Final component and responsive interaction pattern are not selected here. |

### Footer navigation

The footer provides durable access to About / Team, Contact / Support, Information, Privacy, and broad Shop access where useful.

**DESIGN DECISION — WORKING:** Footer navigation supplements rather than replaces primary or contextual access. Legal and general information should remain findable without competing with the main discovery structure.

## 4. Product-discovery structure

```text
Shop
└── Category / Collection
    └── Product list / visible result set
        └── Product Detail
            └── Contextual Support
```

Category / Collection may be bypassed when a person searches directly or enters a featured discovery path.

| Discovery mode | Entry and movement | Context to preserve |
| --- | --- | --- |
| **Broad discovery** | Home or Shop → broad product list → Product Detail. | Current location and a return path to the originating discovery context. |
| **Category browsing** | Shop → Category / Collection → product list → Product Detail. | Category context and, when useful, prior result state. |
| **Filtered browsing** | Shop or category list → selected filters → visible filtered result set → Product Detail. | Active filter state and enough context to return without losing the represented selection. |
| **Search** | Search access → query → result set → Product Detail. | Search query and represented results until intentionally cleared or replaced. |
| **Product evaluation** | Product list/search result → Product Detail → product information or contextual Support. | Selected product and opened detail sections for the current product. |
| **Support** | Global Support or contextual entry from catalogue/product context. | Origin context may be carried conceptually; what is actually transmitted remains an **OPEN QUESTION**. |

**ILLUSTRATIVE ONLY:** Later sample categories may demonstrate the hierarchy but must not be presented as a real Volt taxonomy.

## 5. Primary entities and relationships

This is a conceptual product-information model, not a database or API schema.

| Entity | Purpose | Source / ownership | Relationships | Important state | Representation |
| --- | --- | --- | --- | --- | --- |
| **Product** | Represent an item for discovery and evaluation. | Source/content. | Relates to categories, images, attributes, price, and Product Detail. | Selected/unselected; content complete/incomplete; availability only if represented. | Deterministic mock / illustrative, not real inventory. |
| **Category** | Group related products for browse orientation. | Source/content. | Parent context for a product list; relates to products. | Active/inactive selection. | Illustrative until a real taxonomy is supplied. |
| **Product Attribute** | Describe a decision-relevant characteristic. | Source/content. | Belongs to a product; may later support filtering or comparison. | Visible, progressively disclosed, or unavailable. | Illustrative content. |
| **Product Image** | Visually represent a product. | Source/content. | Belongs to a product; may have multiple views and accessibility alternatives. | Selected image, fallback, or unavailable. | Illustrative asset. |
| **Price** | Represent price where needed for evaluation. | Source/content. | Belongs to a product. | Displayed or unavailable; currency and pricing rules remain open. | Illustrative value; not a transaction price. |
| **Support Entry Point** | Connect a person to contact/help architecture. | Source/content placement plus UI-derived origin context. | Global destination or contextual relationship to Shop/Product Detail. | Default, focused, activated; contextual origin if represented. | Real prototype navigation; support outcome is simulated or informational. |
| **Information Page** | Hold About/Team, Information, or Privacy content. | Source/content. | Linked from primary and/or footer navigation. | Current page/location. | Deterministic mock / illustrative content unless sourced. |
| **Contact Request** | Represent information entered to seek support. | User-created. | Created through contact and evaluated by form validation state. | Empty, in progress, invalid, ready, simulated success/failure if approved. | Local prototype state; no implied real delivery. |
| **Navigation State** | Represent current location and open navigation controls. | System/UI-derived from user selection and viewport context. | Applies across product areas. | Current destination, active item, mobile menu open/closed. | Prototype state. |
| **Filter State** | Represent selected catalogue constraints. | User-created selections with UI-derived summary/results. | Applies to a catalogue/category result set. | Default, active, cleared, unsupported combination, no results. | Prototype state. |
| **Search Query** | Represent discovery input. | User-created. | Produces a UI-derived result set. | Empty, entered, submitted, revised, cleared, no results. | Prototype state. |

```text
Category ── groups ──> Product
Product ── has ──> Product Attribute / Product Image / Price
Search Query + Filter State ── derive ──> Visible result set
Visible result set ── selects ──> Product Detail
Shop / Product Detail ── offers ──> Support Entry Point
Contact input ── creates ──> Contact Request
Navigation selection + viewport context ── derive ──> Navigation State
```

## 6. Information ownership

### Source / content

Normally owned by commerce or content systems: product title and description, imagery and alternatives, attributes/specifications, price/currency, category assignment, About / Team, Information, Privacy, support content, and contact-channel expectations.

For this portfolio prototype, these are deterministic mock or **ILLUSTRATIVE** values unless a later approved source documents otherwise. Their presence does not imply a production CMS, catalogue, pricing engine, or inventory system.

### User-created

- search query and selected filters
- navigation and disclosure selections
- contact-form input

### System-derived / UI-derived

- visible filtered or searched result set
- active filter summary and result count if represented
- selected product and active navigation state
- responsive navigation and opened detail-section state
- form validation, error, and simulated submission feedback

These are interface consequences of source content, user input, and viewport context. They do not imply server processing.

## 7. State boundaries

| State | Working persistence boundary | Intentional reset conditions |
| --- | --- | --- |
| **Current navigation location** | Persists while moving within the prototype and determines active orientation. | Changes on navigation; resets on prototype restart. |
| **Active catalogue filters** | Persists between a result set and a selected product when returning to that discovery context. | Explicit clear/reset, new incompatible discovery context, or restart. |
| **Search query** | Persists through its represented result set and selected-product excursion. | Explicit clear, replacement query, deliberate broad-navigation action, or restart. |
| **Selected product** | Persists while Product Detail is active and may support an origin-aware return. | Selecting another product, leaving the detail context, or restart. |
| **Opened product-detail sections** | Persists for the current product during the current detail visit. | Product change, later-defined leave/re-entry behavior, or restart. |
| **Mobile menu state** | Temporary state scoped to the current viewport and navigation interaction. | Destination selection, dismissal, appropriate viewport change, or restart. |
| **Contact-form field/error state** | Persists during the current contact attempt for understandable recovery. | Explicit reset, simulated success if represented, intentional abandonment, or restart. |

**DESIGN DECISION — WORKING:** Preserve task-relevant context long enough to avoid unnecessary re-entry while allowing explicit, understandable reset. Cross-session persistence is not required.

## 8. Support / contact architecture

### Global support access

- Support in primary navigation.
- Contact as a direct utility action when action wording is more appropriate.
- Contact / Support in footer navigation.

### Contextual support access

- Support entry within Product Detail for product-specific uncertainty.
- Help entry from catalogue or filtered/no-results context when later flow work justifies it.
- Origin-aware messaging may acknowledge the current product or discovery context, but the information carried remains an **OPEN QUESTION**.

**DESIGN DECISION — WORKING:** Support is a connected layer, not the container for the shopping experience. Discovery, browsing, results, and Product Detail remain coherent without forcing contact; support stays easy to reach where clarification may be useful.

This phase does not select a support component, contact channel, form layout, service model, or response promise.

## 9. Responsive IA considerations

- **Navigation compression:** Primary destinations and necessary utilities remain reachable when horizontal navigation no longer fits; the final menu pattern is deferred.
- **Filter access:** Filter entry, applied-state summary, and clear/reset remain discoverable; drawer, sheet, inline, and staged patterns remain unselected.
- **Search access:** Search remains identifiable without displacing primary navigation or support.
- **Product-detail hierarchy:** Product identity, decision-relevant information, price if represented, and support retain a logical reflow sequence.
- **Support discoverability:** Global and contextual support do not disappear through compression.
- **Footer / information navigation:** About, information, privacy, and contact destinations remain readable when stacked or collapsed.
- **Context preservation:** Viewport changes should not silently discard filters, query, selected-product, or form state unless documented later.

No breakpoint, grid, responsive component, or final content order is selected here.

## 10. Accessibility IA considerations

**DESIGN DECISION — TARGET:** Volt targets WCAG 2.2 AA; compliance is not claimed.

- Use logical page-title and heading hierarchy based on information structure.
- Use understandable, consistent navigation labels and expose current location programmatically.
- Provide appropriate header, navigation, main, complementary/help where justified, and footer landmarks.
- Keep repeated navigation predictable in naming, order, and destination.
- Use breadcrumbs only where hierarchy and return orientation justify them.
- Give Product Detail a comprehensible reading order for identity, images/alternatives, price if represented, attributes, deeper information, and support.
- Associate contact labels, instructions, required state, errors, and summaries programmatically with fields.
- Use clear, unique page titles for major destinations and selected-product contexts.
- Communicate active navigation, filters, validation, availability, and status without relying on color alone.
- Preserve keyboard order and focus context when navigation, filters, disclosures, or validation change.
- Ensure responsive reflow does not sever semantic relationships or hide required routes.

These are structural requirements for later review, not a compliance result.

## 11. Open questions

All items below remain **OPEN QUESTIONS**:

1. Actual catalogue size.
2. Real category/collection taxonomy and cross-category relationships.
3. Search scope, matching, suggestions, sorting, and no-results recovery.
4. Comparison requirements and meaningful comparable attributes.
5. Whether a cart indicator should appear in the bounded prototype and what non-transactional state it represents.
6. Whether product availability should be represented and which states are legitimate.
7. Support model, service boundary, response expectation, and escalation path.
8. Whether contact is form-only or multi-channel, and which fields are required.
9. Any future account requirement; accounts remain out of scope now.
10. Localization, language, currency, regional privacy, and directionality requirements.
11. Real content-management, commerce, integration, and editorial constraints.
12. Legitimate product relationships, recommendations, featured collections, or merchandising rules.
13. Which catalogue, detail, contact, empty, loading, unavailable, success, and failure states need prototype coverage.
14. What contextual information, if any, support should receive from current product or discovery state.

## 12. Traceability and phase boundary

| Requirement | Repository source | Figma summary |
| --- | --- | --- |
| Major product areas and navigation | Sections 2–3 | `IA — 01 Product Architecture` — `39:2` |
| Discovery hierarchy and support relationship | Sections 4 and 8 | `IA — 01 Product Architecture` — `39:2` |
| Entities and information ownership | Sections 5–6 | `IA — 01 Product Architecture` — `39:2` |
| State boundaries | Section 7 | `IA — 01 Product Architecture` — `39:2` |
| Responsive and accessibility structure | Sections 9–10 | Canonical detail remains here; the frame is a concise summary. |
| Unresolved conditions | Section 11 | Open questions remain canonical here. |

- **Phase 01:** COMPLETE / APPROVED — [BRIEF.md](BRIEF.md)
- **Phase 02:** COMPLETE / APPROVED — [UX_ASSUMPTIONS.md](UX_ASSUMPTIONS.md)
- **Phase 03:** COMPLETE / APPROVED — this document and `IA — 01 Product Architecture`
- **Next phase:** Primary Flow. No Primary Flow artifact, product screen, or wireframe is created in this phase.

This architecture remains a working design decision subject to later human review when open questions receive evidence. It does not establish a production taxonomy, backend, inventory, transaction model, completed accessibility conformance, or validated behavior.
