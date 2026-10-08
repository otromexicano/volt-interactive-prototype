# Phase 05 — Interaction Contract

## 1. Purpose and checkpoint

This document is the **one canonical repository Phase 05 Interaction Contract** for Volt. It converts the approved Product Definition, User Flow, Information Architecture, and Phase 05 human interaction-direction selections into an implementation-independent interaction-state specification.

- **Phase:** Phase 05 — Interaction Contract.
- **Current checkpoint:** **PASS / COMPLETE**.
- **Completion boundary:** This artifact and its supporting Figma candidate do not make Phase 05 complete. Completion still requires the formal read-only completion audit and final human approval.
- **Next-phase boundary:** Phase 06 — Visual Direction has not started.
- **Canonical repository artifact:** `docs/05-interaction-contract.md`.
- **Supporting Figma candidate:** `80:2` — `INTERACTION — 01 Canonical Interaction Contract Candidate` on `90 — Candidates`.

This specification defines intended behavior. It is not a polished UI, wireframe, component library, coded prototype, usability result, production observation, or accessibility-conformance claim.

## 2. Authoritative Phase 05 requirements

The Master Workflow requires important component behavior to be defined before UI polish and requires every major component to have an interaction contract.

The required coverage is:

- **Visual states:** default, hover, focused, selected, disabled.
- **Data states:** loading, populated, empty, error.
- **Interaction:** click, keyboard, focus, screen reader.
- **Responsive:** mobile, tablet, desktop.
- **Motion:** entrance, exit, state transition, reduced-motion behavior.
- **Goal:** prevent designing only the happy path.
- **Expected output:** interaction-state specification.
- **Exit gate:** no major interactive component should enter implementation without its states being defined.

Every listed playbook state is explicitly classified below as **APPLICABLE** or **N/A WITH RATIONALE**. No playbook state may be silently omitted.

## 3. Evidence and claim boundary

| Label | Meaning in this artifact |
| --- | --- |
| **FACT** | Directly supplied by the source brief or observable in an approved artifact. |
| **ASSUMPTION** | Provisional behavior or context requiring later validation. |
| **DESIGN DECISION** | A chosen design interpretation not yet human approved. |
| **HUMAN-APPROVED DESIGN DECISION** | A direction explicitly selected at the Phase 05 checkpoint or inherited from approved canonical Phases 02–04. |
| **OPEN QUESTION** | Information not supplied or validated and not silently resolved here. |

This artifact does not claim usability testing, observed user behavior, validated interaction preference, analytics, production behavior, production errors, real backend state, real persistence, device usage, conversion impact, business outcomes, or WCAG conformance.

## 4. Approved scope

### 4.1 Retained

1. Shared navigation and orientation.
2. Home.
3. Catalogue.
4. Product Detail.
5. Contact.
6. Information.
7. About / Team.
8. Privacy Policy.

### 4.2 Deferred

- Category / Collection.
- Search.
- Filters.

### 4.3 Removed or excluded

- Cart, checkout, payment, purchase, and production transactions.
- Accounts and authentication.
- Production inventory.
- Contact Request, Contact fields, required fields, validation, submission, submission feedback, retry, email delivery, support response, SLA, support ticket, backend Contact behavior, and support-case architecture.

No contract below reintroduces deferred or removed behavior. Phase 04 semantic priority tiers do not become visual component families.

## 5. Formal major-interaction inventory

**HUMAN-APPROVED DESIGN DECISION:** Phase 05 contains exactly fourteen major interaction contracts.

| ID | Major interaction | Approved basis | Disposition |
| --- | --- | --- | --- |
| IC-01 | Shared navigation / orientation | Phase 02 retained navigation; Phase 03 shared layer; Phase 04 global access | **RETAINED** |
| IC-02 | Home → Catalogue | Phase 03 primary/alternate flow; Phase 04 approved relationship | **RETAINED** |
| IC-03 | Home → Contact | Phase 03 alternate flow; Phase 04 approved relationship | **RETAINED** |
| IC-04 | Catalogue product selection → Product Detail | Phase 03 UF-02/UF-03; Product Detail beneath Catalogue in Phase 04 | **NARROWED** to broad Catalogue selection |
| IC-05 | Product Detail → prior broad Catalogue context | Phase 03 approved return; Phase 04 return relationship | **NARROWED** to approved origin/fallback |
| IC-06 | Product Detail → Contact | Phase 03 contextual Contact; Phase 04 contextual relationship | **NARROWED** to generic Contact |
| IC-07 | Contact return / abandonment | Phase 03 cancellation/abandonment; Phase 04 direct-entry recovery | **NARROWED** to non-submission navigation |
| IC-08 | Information access / return | Phase 03 Information flow; Phase 04 shared destination | **RETAINED** |
| IC-09 | About / Team access / return | Phase 03 About / Team flow; Phase 04 shared destination | **NARROWED** canonical naming |
| IC-10 | Privacy Policy access / return | Phase 03 Privacy flow; Phase 04 required shared access | **NARROWED** canonical naming/access |
| IC-11 | Direct-entry orientation / recovery | Phase 03 orientation; Phase 04 direct-entry architecture | **RETAINED** |
| IC-12 | Represented Catalogue content unavailable | Phase 03 evidence-safe empty state | **RETAINED** as represented-content state |
| IC-13 | Product Detail content unavailable | Phase 03 evidence-safe missing-content state | **RETAINED** as represented-content state |
| IC-14 | Unreachable destination / broken return / lost orientation | Phase 03 error/recovery; Phase 04 recovery relationships | **RETAINED** |

Catalogue product selection and Catalogue → Product Detail are intentionally one contract, IC-04. No fifteenth contract is implied.

## 6. Contract anatomy

Each major contract defines, where applicable:

1. starting state;
2. trigger and user action;
3. system response and feedback;
4. resulting state and available next actions;
5. return, abandonment, dismissal, or cancellation;
6. unavailable/error behavior and recovery;
7. state that may persist and reset conditions;
8. state that must not persist;
9. click/pointer behavior;
10. keyboard behavior;
11. focus behavior;
12. screen-reader behavior;
13. mobile/tablet/desktop equivalence; and
14. motion and reduced-motion applicability.

Cancellation and temporary-interaction dismissal are **N/A** unless a contract explicitly says otherwise. No temporary disclosure interaction is approved.

## 7. Canonical state-applicability matrix

### 7.1 Component and interaction categories

| Category | Default | Hover | Focused | Selected | Disabled | Loading | Populated | Empty | Error | Entrance | Exit | State transition | Reduced motion |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Destination/navigation action | **APPLICABLE** | **APPLICABLE** as supplementary pointer feedback | **APPLICABLE** | **N/A** for one-shot actions; current-destination action is covered by shared orientation | **N/A**; omit, explain, or recover | **N/A**; no approved asynchronous requirement | **N/A** to action itself | **N/A** | **APPLICABLE** when destination is unreachable | **N/A** by default | **N/A** by default | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Shared current-destination state | **APPLICABLE** | **APPLICABLE** to actions, not the state meaning | **APPLICABLE** | **APPLICABLE** because current destination is meaningful | **N/A** | **N/A** | **APPLICABLE** when destination content is represented | **APPLICABLE** only to approved absent represented content | **APPLICABLE** to unreachable destination | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Represented-product selection | **APPLICABLE** | **APPLICABLE** as supplementary feedback | **APPLICABLE** | **N/A** as a one-shot selection action | **N/A**; unavailable products are not inert controls | **N/A** | **APPLICABLE** when a represented product exists | **APPLICABLE** through IC-12 | **APPLICABLE** through IC-14 | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Product Detail return action | **APPLICABLE** | **APPLICABLE** as supplementary feedback | **APPLICABLE** | **N/A** | **N/A**; broad Catalogue fallback remains valid | **N/A** | **N/A** | **N/A** | **APPLICABLE** for invalid origin/broken return | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Contact action | **APPLICABLE** | **APPLICABLE** as supplementary feedback | **APPLICABLE** | **N/A** except Contact as current destination in shared orientation | **N/A** | **N/A** | **APPLICABLE** to approved generic Contact content | **APPLICABLE** when no Contact content is represented | **APPLICABLE** when Contact is unreachable | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Informational navigation action | **APPLICABLE** | **APPLICABLE** as supplementary feedback | **APPLICABLE** | **N/A** except current destination in shared orientation | **N/A** | **N/A** | **APPLICABLE** to represented destination content | **APPLICABLE** when required represented content is absent | **APPLICABLE** when destination is unreachable | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Unavailable/error recovery action | **APPLICABLE** | **APPLICABLE** as supplementary feedback | **APPLICABLE** | **N/A** | **N/A**; recovery must remain actionable | **N/A** | **N/A** | **APPLICABLE** to missing represented content context | **APPLICABLE** | **N/A** | **N/A** | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Content container/state | **APPLICABLE** | **N/A**; container is not inherently actionable | **N/A** unless the container is a deliberate focus destination | **APPLICABLE** only for meaningful current context | **N/A** | **N/A** for current scope | **APPLICABLE** | **APPLICABLE** only to approved unavailable represented content | **APPLICABLE** only to approved failure contexts | **N/A** by default | **N/A** by default | **APPLICABLE** | **APPLICABLE IF MOTION EXISTS** |
| Navigation disclosure | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** | **N/A** because no disclosure interaction is approved |

### 7.2 State rules

- **Default:** Every retained action has an operable default state.
- **Hover:** Hover may reinforce actionability for pointer users but cannot reveal the only name, state, destination, or recovery cue.
- **Focused:** Every retained action exposes a visible focus state.
- **Selected:** Use only for a meaningful current or persistent state, principally the current shared destination. Do not apply it to one-shot navigation actions.
- **Disabled:** No retained action is disabled in current scope. Prefer a valid fallback, omission, an explanatory unavailable state, or a reachable recovery action. Unexplained inert controls are prohibited.
- **Loading:** **N/A WITH RATIONALE.** Current scope has no approved backend, real inventory, Contact submission, or required asynchronous content fetch. If asynchronous representative content is later introduced, Phase 05 must be amended before implementation.
- **Populated:** Applies to represented destination/content states; it does not claim production data.
- **Empty:** Applies only to approved absent represented-content conditions.
- **Error:** Applies only to the evidence-safe inventory in Section 15.
- **Entrance/exit:** **N/A by default.** Ordinary retained navigation requires no animation.
- **State transition:** Applies wherever state or context changes, even when immediate and non-animated.
- **Reduced motion:** Whenever motion exists, it is nonessential, removable or minimized, and never the sole feedback.

## 8. Shared interaction rules

### 8.1 Activation and feedback

- Pointer/click and standard semantic keyboard activation invoke the same retained action.
- The system presents the named destination or recovery result.
- A meaningful destination/context change is confirmed through ordinary title, heading, current-state, and focus context.
- A hover-only or pointer-only path is prohibited.

### 8.2 Destination focus

- Normal destination changes place focus at the destination heading or equivalent main-content start.
- IC-05 known-origin return is the approved exception: restore focus to the originating represented-product action when it remains available.
- IC-05 fallback places focus at the Catalogue heading or equivalent main-content start.
- Recovery must not strand focus.

### 8.3 Current state and orientation

- The current retained destination is perceivable and not communicated through color alone.
- Current-state semantics are used only where the state is meaningful.
- Shared orientation remains available across retained destinations.
- Direct entry does not depend on browser history.

### 8.4 Responsive equivalence

**HUMAN-APPROVED DESIGN DECISION:** Mobile, tablet, and desktop have equivalent interaction behavior:

- the same retained destinations;
- the same semantic navigation actions;
- the same current-state meaning;
- the same keyboard access;
- the same destination results; and
- equivalent recovery paths.

No hamburger, drawer, sheet, disclosure open/close state, icon, breakpoint, or header layout is defined. Responsive visual composition belongs to later phases. If later evidence requires a disclosure interaction, Phase 05 must be explicitly amended and re-audited before implementation.

### 8.5 Motion

No contract requires motion. If later motion is introduced, state and destination meaning must remain complete without it; nonessential spatial movement is removed or minimized under reduced-motion preference; and timing or movement cannot be the only feedback.

## 9. Fourteen interaction contracts

### IC-01 — Shared navigation / orientation

| Field | Contract |
| --- | --- |
| Starting state | Any retained destination, including direct entry or unknown origin. |
| Trigger / action | Activate a clearly named retained destination through pointer or standard semantic keyboard input. |
| System response / feedback | Present the named destination; expose its heading/title and meaningful current-destination state. |
| Result / next actions | The destination is active; all retained shared destinations remain reachable. |
| Return / abandonment | Ordinary navigation to another retained destination. Cancellation and dismissal are **N/A**. |
| Unavailable / recovery | If a destination is unreachable, present a perceivable explanation and a reachable shared-orientation recovery path under IC-14. |
| Persistence / reset | Shared orientation remains available. Current destination persists until another retained destination activates. |
| Accessibility | No pointer-only dependency; semantic activation; visible focus; current state not color-only; focus moves to heading/main start after destination change. |
| Responsive | Behaviorally equivalent on mobile, tablet, and desktop; no disclosure interaction. |
| Motion | Entrance/exit **N/A**; transition semantics **APPLICABLE**; no motion required. |
| Evidence | **FACT** for required destinations; **HUMAN-APPROVED DESIGN DECISION** for shared behavior. |

### IC-02 — Home → Catalogue

| Field | Contract |
| --- | --- |
| Starting state | Home is active and oriented. |
| Trigger / action | Activate the clearly named Catalogue action. |
| System response / feedback | Present broad Catalogue content without Category, Search, Filters, sorting, inventory, or Cart behavior. |
| Result / next actions | Catalogue is current; browse represented products, activate IC-04, or use shared orientation. |
| Return / abandonment | Ordinary navigation away. Cancellation is **N/A**. |
| Unavailable / recovery | IC-12 if represented Catalogue content is unavailable; IC-14 if Catalogue is unreachable. |
| Persistence / reset | Current destination becomes Catalogue; no Home-specific state persists. |
| Accessibility | Semantic activation; visible focus before activation; focus at Catalogue heading/main start after navigation. |
| Responsive / motion | Equivalent across viewports; no required entrance/exit motion; transition semantics apply. |
| Evidence | **FACT** + **HUMAN-APPROVED DESIGN DECISION** from canonical Phases 02–04. |

### IC-03 — Home → Contact

| Field | Contract |
| --- | --- |
| Starting state | Home is active and oriented. |
| Trigger / action | Activate the clearly named Contact action. |
| System response / feedback | Present approved generic Contact content. |
| Result / next actions | Contact is current; success is reached content, not submission. Use IC-07 or shared navigation to leave. |
| Return / abandonment | Known represented origin may be used; otherwise shared navigation. Cancellation is **N/A**. |
| Unavailable / recovery | Failure if Contact is unreachable or no Contact content is represented; provide shared-orientation recovery. |
| Persistence / reset | Known origin may persist only within the bounded visit; no Contact fields or backend state exist. |
| Accessibility | Semantic activation, visible focus, meaningful Contact heading/main focus, perceivable failure and recovery. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Evidence | **FACT** for Contact goal; **HUMAN-APPROVED DESIGN DECISION** for non-submission reachability. |

### IC-04 — Catalogue product selection → Product Detail

| Field | Contract |
| --- | --- |
| Starting state | Populated broad Catalogue with at least one represented-product action. |
| Trigger / action | Activate a represented product using pointer or standard semantic keyboard input. |
| System response / feedback | Present Product Detail for that represented product and establish the known broad Catalogue origin when available. |
| Result / next actions | Product Detail is active; review represented information, use IC-05, use IC-06, or use shared orientation. |
| Return / abandonment | IC-05 supplies the explicit Catalogue-oriented return. Browser Back is not the contract. |
| Unavailable / recovery | IC-13 for missing Product Detail content; IC-14 if the destination is unreachable. |
| Persistence / reset | Product identity persists while Product Detail is active. Known origin persists only for the bounded excursion. A new product replaces the active product context. |
| Accessibility | Each product action has a meaningful name; visible focus; destination focus moves to Product Detail heading/main start. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Exclusions | No dependency on Category, Search, Filters, sorting, price, availability, inventory, Cart, or backend data. |
| Evidence | **FACT** for product pages; **HUMAN-APPROVED DESIGN DECISION** for represented broad-Catalogue selection. |

### IC-05 — Product Detail → prior broad Catalogue context

| Field | Contract |
| --- | --- |
| Starting state | Product Detail is active; Catalogue origin may be known, unknown, invalid, or unavailable. |
| Trigger / action | Activate a clearly named Catalogue-oriented return action. It is not labelled or defined as browser Back. |
| System response / feedback | Valid known origin → return to represented prior broad Catalogue context. Unknown/invalid/unavailable origin → broad Catalogue. |
| Result / next actions | Catalogue is active with restored origin context when valid, otherwise safe broad-Catalogue fallback. |
| Focus | Known origin → originating represented-product action when still available. Fallback → Catalogue heading or equivalent main-content start. |
| Persistence allowed | Prior broad Catalogue origin; product identity long enough to establish return; represented product neighborhood if later implementation supports it; orientation cue; Product Detail origin through Product Detail → Contact → Product Detail. |
| Reset | New represented product; deliberate unrelated retained destination; invalid/unavailable origin; prototype restart or bounded-session end. |
| Never persist | Search, Filters, Category, sort, inventory, Cart, backend, account, or cross-session history. |
| Accessibility | Clear Catalogue-oriented name; semantic activation; no custom keys or pointer gesture; ordinary destination heading/title/focus communicates the result. |
| Responsive / motion | Equivalent across viewports. No motion required; any future return motion is nonessential and reduced-motion safe. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION — Option A**. |

### IC-06 — Product Detail → Contact

| Field | Contract |
| --- | --- |
| Starting state | Product Detail is active for a represented product. |
| Trigger / action | Activate the clearly named Contact action. |
| System response / feedback | Present generic Contact content while retaining only the bounded Product Detail origin relationship. |
| Result / next actions | Contact is active; return to originating Product Detail when known, recover to broad Catalogue when origin is lost, or use shared navigation. |
| Return / abandonment | IC-07. No product context is transmitted to Contact. |
| Unavailable / recovery | Unreachable or empty Contact is failure; retain a predictable recovery to Product Detail when valid or broad Catalogue. |
| Persistence / reset | Product Detail origin may persist through this contextual excursion; reset under Section 14 lifecycle rules. |
| Accessibility | Semantic action and name; Contact heading/main focus; perceivable failure; reachable recovery. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION** inherited from approved Contact flow and confirmed at Phase 05. |

### IC-07 — Contact return / abandonment

| Field | Contract |
| --- | --- |
| Starting state | Generic Contact is active from a known or unknown origin. |
| Trigger / action | Activate an available return action when represented or any valid shared navigation action. |
| System response / feedback | Known global origin → return there when represented. Known Product Detail origin → return to it. Lost Product Detail origin → broad Catalogue. Otherwise navigate to chosen retained destination. |
| Result / next actions | A valid retained destination is active and oriented. |
| Abandonment / cancellation | Abandonment is ordinary valid navigation away. Cancellation is **N/A** because no request or submission process begins. |
| Unavailable / recovery | A broken return uses shared orientation or broad Catalogue as applicable. |
| Persistence / reset | Only bounded known origin may persist. Deliberate unrelated navigation resets contextual origin. |
| Accessibility | Return/action names describe destination; visible focus; focus moves to valid destination context; no focus trap. |
| Responsive / motion | Equivalent across viewports; no dismissal interaction; no required motion. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION**; Contact direction confirmed sufficient. |

### IC-08 — Information access / return

| Field | Contract |
| --- | --- |
| Starting state | Any retained destination or direct entry. |
| Trigger / action | Activate the clearly named Information action. |
| System response / feedback | Present available represented Information content and its destination context. |
| Result / next actions | Information is current; review content or use shared navigation/known represented return. |
| Return / abandonment | Known represented origin may be used; otherwise shared navigation. Ordinary navigation away; cancellation **N/A**. |
| Unavailable / recovery | Absent content or unreachable destination produces a perceivable explanation and shared-orientation recovery under IC-14. |
| Persistence / reset | Current destination only; no Information-specific cross-destination or cross-session state. |
| Accessibility | Semantic activation; visible focus; focus at heading/main start; current state and errors perceivable. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Evidence | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for destination behavior. |

### IC-09 — About / Team access / return

| Field | Contract |
| --- | --- |
| Starting state | Any retained destination or direct entry. |
| Trigger / action | Activate the clearly named About / Team action. |
| System response / feedback | Present available represented About / Team content and its destination context. |
| Result / next actions | About / Team is current; review content or use shared navigation/known represented return. |
| Return / abandonment | Known represented origin may be used; otherwise shared navigation. Ordinary navigation away; cancellation **N/A**. |
| Unavailable / recovery | Absent content or unreachable destination produces a perceivable explanation and shared-orientation recovery under IC-14. |
| Persistence / reset | Current destination only; no destination-specific cross-session state. |
| Accessibility | Semantic activation; visible focus; focus at heading/main start; current state and errors perceivable. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Evidence | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for canonical naming and behavior. |

### IC-10 — Privacy Policy access / return

| Field | Contract |
| --- | --- |
| Starting state | Any retained destination or direct entry. |
| Trigger / action | Activate the clearly named Privacy Policy action through required shared/global access; optional footer access may supplement it. |
| System response / feedback | Present available represented Privacy Policy content and its destination context. |
| Result / next actions | Privacy Policy is current; review content or use shared navigation/known represented return. |
| Return / abandonment | Known represented origin may be used; otherwise shared navigation. Ordinary navigation away; cancellation **N/A**. |
| Unavailable / recovery | Absent content or unreachable destination produces a perceivable explanation and shared-orientation recovery under IC-14. |
| Persistence / reset | Current destination only; no policy-specific cross-session state. |
| Accessibility | Semantic activation; visible focus; focus at heading/main start; current state and errors perceivable. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Claim boundary | Destination presence does not claim legal adequacy, consent handling, data collection, or production privacy compliance. |
| Evidence | **FACT** for required content; **HUMAN-APPROVED DESIGN DECISION** for shared access and optional footer supplement. |

### IC-11 — Direct-entry orientation / recovery

| Field | Contract |
| --- | --- |
| Starting state | A retained destination is entered without a known in-prototype origin. |
| Trigger / action | Direct entry presents the requested retained destination. |
| System response / feedback | Expose destination title/heading, meaningful current-destination state, main content, and shared orientation. |
| Result / next actions | The visitor can understand the current location and reach another valid retained destination. |
| Return / abandonment | Unknown origin does not create a return promise; use shared navigation. Product Detail specifically uses broad Catalogue fallback. |
| Unavailable / recovery | Unreachable or incomplete destination follows IC-12, IC-13, or IC-14 as applicable. |
| Persistence / reset | Current destination persists until another activates; unknown origin remains unknown and is not fabricated. |
| Accessibility | Heading/title and current-state context are perceivable; focus begins in meaningful destination context; no browser-history dependency. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION** from Phase 03/04 recovery architecture and Phase 05 accessibility model. |

### IC-12 — Represented Catalogue content unavailable

| Field | Contract |
| --- | --- |
| Starting state | Catalogue is reached but no representative product content is present in the prototype. |
| Trigger / action | Catalogue presentation determines that represented content is unavailable. No user retry is required. |
| System response / feedback | Present an explicit, perceivable represented-content-unavailable message without production or inventory explanation. |
| Result / next actions | Catalogue remains oriented; Home, Contact, and other retained shared destinations remain reachable. |
| Return / abandonment | Ordinary navigation away; cancellation **N/A**. |
| Recovery | Use a reachable Home or Contact action or shared orientation. Repeated failure leaves the same valid recovery paths. |
| Persistence / reset | The condition is only a represented prototype state; no inventory/backend/cross-session persistence is claimed. |
| Accessibility | Message and affected context are perceivable; recovery actions are keyboard operable; focus remains predictable and not stranded. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Does not claim | Zero inventory, out of stock, Search no-results, Filter mismatch, Category empty, network/server failure, or future availability. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION** grounded in Phase 03 evidence-safe empty state. |

### IC-13 — Product Detail content unavailable

| Field | Contract |
| --- | --- |
| Starting state | Product Detail is active but required represented information, image, or other content is absent. |
| Trigger / action | The destination presents incomplete represented content. No production fetch or retry is implied. |
| System response / feedback | Identify unavailable represented information without inventing cause; retain any usable represented content. |
| Result / next actions | Continue with available content, use IC-05 to broad Catalogue context/fallback, or use IC-06 to generic Contact. |
| Return / abandonment | Origin-aware return remains available; ordinary navigation away. |
| Recovery | Clear Catalogue or Contact recovery; repeated failure retains a valid route. |
| Persistence / reset | Product identity persists while Product Detail is active; missing content is not production/backend state. |
| Accessibility | Message and affected context are perceivable; recovery actions are reachable; focus remains predictable. |
| Responsive / motion | Equivalent across viewports; no required motion. |
| Does not claim | Production data loss, inventory status, network failure, or Contact’s ability to supply missing content. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION** grounded in Phase 03 evidence-safe missing-content state. |

### IC-14 — Unreachable destination / broken return / lost orientation

| Field | Contract |
| --- | --- |
| Starting state | An intended retained destination cannot be reached, a return target is invalid/unavailable, required represented information prevents continuation, or orientation is lost. |
| Trigger / action | Activation or continuation cannot produce the approved resulting state. |
| System response / feedback | Present an explicit, perceivable message that identifies the affected context without inventing a production cause. |
| Result / next actions | Provide at least one reachable recovery: shared orientation, Home, broad Catalogue, Contact, or a still-valid origin as context permits. |
| Return / abandonment | Broken Product Detail return falls back to broad Catalogue. Lost general orientation restores shared orientation/Home. |
| Repeated failure | The message persists as needed and at least one alternative valid recovery path remains; focus is not stranded. |
| Persistence / reset | Invalid origins reset. No error, backend, analytics, or cross-session state is created. |
| Accessibility | Error and affected context are perceivable; recovery is keyboard operable; focus goes to the message or recovery context only when needed and remains predictable. |
| Responsive / motion | Equivalent across viewports; no required motion; motion cannot convey failure alone. |
| Does not claim | Network/server outage, production error, inventory failure, Contact submission error, or operational retry. |
| Evidence | **HUMAN-APPROVED DESIGN DECISION** grounded in Phase 03/04 recovery direction. |

### 9.15 Per-contract state, input, accessibility, responsive, and motion ledger

The detailed contracts above define starting state, trigger, system response, immediate/resulting state, next actions, return/abandonment, recovery, persistence, reset, exclusions, and evidence. The following ledger makes the remaining required fields explicit for every contract. “Shared” means the rule in Sections 7–8 applies without adding contract-specific behavior.

| Contract | Pointer / click | Keyboard | Focus | Screen reader | Current / selected state | Populated / empty / error | Explicit N/A states |
| --- | --- | --- | --- | --- | --- | --- | --- |
| IC-01 | Same semantic destination action as keyboard | Standard semantic activation; no trap | Visible before activation; destination heading/main start after | Meaningful destination name and current-state semantics | Current destination **APPLICABLE**; one-shot action selected state **N/A** | Populated destination **APPLICABLE**; unavailable destination uses IC-14 | Disabled and loading **N/A**; no inert action or async requirement |
| IC-02 | Activate Catalogue action | Standard semantic activation | Catalogue heading/main start | Catalogue name plus ordinary destination context | Catalogue becomes current; selected state on one-shot action **N/A** | Populated Catalogue **APPLICABLE**; empty IC-12; unreachable IC-14 | Disabled/loading **N/A** |
| IC-03 | Activate Contact action | Standard semantic activation | Contact heading/main start | Contact name plus ordinary destination context | Contact becomes current; one-shot selected state **N/A** | Generic Contact populated **APPLICABLE**; absent/unreachable is failure | Disabled/loading **N/A**; submission states **N/A** |
| IC-04 | Activate represented-product action | Standard semantic activation | Product Detail heading/main start | Meaningful represented-product action name; ordinary destination context | Product Detail becomes current; selection action selected state **N/A** | Product content populated **APPLICABLE**; unavailable IC-13; unreachable IC-14 | Disabled/loading **N/A**; price/inventory states **N/A** |
| IC-05 | Activate explicit Catalogue-oriented return | Standard semantic activation; no custom key | Restore origin product action when valid; otherwise Catalogue heading/main start | Clear Catalogue-oriented name; ordinary result context | Catalogue becomes current; return action selected state **N/A** | Invalid/unavailable origin is error/recovery **APPLICABLE** | Disabled/loading/empty **N/A**; browser Back contract **N/A** |
| IC-06 | Activate Contact action | Standard semantic activation | Contact heading/main start | Contact name; no unnecessary live announcement | Contact becomes current; one-shot selected state **N/A** | Generic Contact populated **APPLICABLE**; absent/unreachable is failure | Disabled/loading **N/A**; prefill/transmission **N/A** |
| IC-07 | Activate valid return or navigation action | Standard semantic activation; no trap | Valid origin context or fallback heading/main start | Return action names its destination | Resulting retained destination becomes current | Broken return uses IC-14 | Disabled/loading/empty **N/A**; cancellation/dismissal **N/A** |
| IC-08 | Activate Information action/recovery | Standard semantic activation | Information heading/main start; predictable recovery focus | Meaningful name, current context, unavailable message | Information current state **APPLICABLE** | Populated **APPLICABLE**; absent/unreachable recovery **APPLICABLE** | Disabled/loading **N/A**; cancellation **N/A** |
| IC-09 | Activate About / Team action/recovery | Standard semantic activation | About / Team heading/main start; predictable recovery focus | Meaningful name, current context, unavailable message | About / Team current state **APPLICABLE** | Populated **APPLICABLE**; absent/unreachable recovery **APPLICABLE** | Disabled/loading **N/A**; cancellation **N/A** |
| IC-10 | Activate shared/global or optional supplementary footer action | Standard semantic activation | Privacy Policy heading/main start; predictable recovery focus | Meaningful name, current context, unavailable message | Privacy Policy current state **APPLICABLE** | Populated **APPLICABLE**; absent/unreachable recovery **APPLICABLE** | Disabled/loading **N/A**; cancellation **N/A** |
| IC-11 | Direct entry itself has no click; subsequent shared/recovery actions use shared pointer behavior | Subsequent actions use standard semantic activation | Enter meaningful destination context | Destination identity/current state conveyed by ordinary context | Entered destination current state **APPLICABLE** | Destination-specific populated/empty/error contract applies | Direct-entry hover/disabled/loading **N/A**; no prior-history control |
| IC-12 | Recovery actions use shared semantic click behavior | Recovery is keyboard operable | Message/context remains predictable; recovery is reachable | Represented-content message and recovery names are perceivable | Catalogue remains current | Empty **APPLICABLE**; technical error **N/A** | Disabled/loading/selected **N/A**; no retry control |
| IC-13 | Catalogue/Contact recovery actions use shared click behavior | Recovery is keyboard operable | Product Detail context remains meaningful; recovery is reachable | Missing represented information and recovery are perceivable | Product Detail remains current until recovery | Empty/missing represented content **APPLICABLE**; technical error **N/A** | Disabled/loading/selected **N/A**; no production retry |
| IC-14 | Recovery action uses shared semantic click behavior | Recovery is keyboard operable; no trap | Message or recovery context receives useful focus only when needed | Problem, known context, and recovery are perceivable | Known current context remains perceivable; selected recovery action **N/A** | Evidence-safe error **APPLICABLE**; populated/empty as originating contract defines | Disabled/loading **N/A**; technical-cause state **N/A** |

| Contract | Mobile | Tablet | Desktop | Entrance motion | Exit motion | State transition | Reduced motion |
| --- | --- | --- | --- | --- | --- | --- | --- |
| IC-01 | Equivalent | Equivalent | Equivalent | **N/A**; no required animation | **N/A**; no required animation | **APPLICABLE** to destination/current-state change | **APPLICABLE IF MOTION EXISTS** |
| IC-02 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to Home → Catalogue | **APPLICABLE IF MOTION EXISTS** |
| IC-03 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to Home → Contact | **APPLICABLE IF MOTION EXISTS** |
| IC-04 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to selection → Product Detail | **APPLICABLE IF MOTION EXISTS** |
| IC-05 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to known-origin return or fallback | **APPLICABLE IF MOTION EXISTS** |
| IC-06 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to Product Detail → Contact | **APPLICABLE IF MOTION EXISTS** |
| IC-07 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to return/navigation result | **APPLICABLE IF MOTION EXISTS** |
| IC-08 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to Information/current/recovery state | **APPLICABLE IF MOTION EXISTS** |
| IC-09 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to About / Team/current/recovery state | **APPLICABLE IF MOTION EXISTS** |
| IC-10 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to Privacy Policy/current/recovery state | **APPLICABLE IF MOTION EXISTS** |
| IC-11 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to direct-entry orientation | **APPLICABLE IF MOTION EXISTS** |
| IC-12 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to represented-content unavailable/recovery | **APPLICABLE IF MOTION EXISTS** |
| IC-13 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to represented-content unavailable/recovery | **APPLICABLE IF MOTION EXISTS** |
| IC-14 | Equivalent | Equivalent | Equivalent | **N/A** | **N/A** | **APPLICABLE** to failure/recovery context | **APPLICABLE IF MOTION EXISTS** |

For every row, behavioral equivalence does not require identical visual layout. No duration, easing, choreography, breakpoint, or responsive disclosure is defined.

## 10. Interaction-level accessibility model

These are intended Phase 05 contract requirements, not verified conformance.

| Rule | Phase 05 contract requirement | Deferred to later Accessibility phase |
| --- | --- | --- |
| Keyboard activation | Every retained action is operable without pointer using its standard semantic activation; logical navigation; no custom shortcut; no keyboard trap. | Verify semantics, ordering, behavior, and traps in implementation. |
| Focus visibility | Every retained action has a visible focus state. | Verify contrast, visibility, clipping, and persistence. |
| Destination focus | Meaningful navigation places focus at heading/main start; IC-05 restores useful origin focus when valid; fallback uses Catalogue heading/main start. | Verify actual focus movement in supported browsers and assistive technology. |
| Current state | Current destination/state is perceivable, meaningful, and not color-only. | Verify programmatic state and visual contrast. |
| Screen-reader names | Actions have meaningful accessible names; current-state semantics are used where meaningful. | Verify computed names, roles, and states. |
| Context change | Ordinary navigation relies on appropriate title/heading/focus context; unnecessary live announcements are avoided. | Verify actual announcements and routing behavior. |
| Error/recovery | Message, affected context, and recovery are perceivable; recovery is reachable; focus is predictable; repeated failure still has a valid route. | Verify reading order, announcement, focus handling, and repeated-failure behavior. |
| Disabled/unavailable | Prefer valid fallback, omission, explanatory unavailable state, or recovery; prohibit unexplained inert controls. | Verify implementation exposes no misleading focusable or disabled dead ends. |
| Reduced motion | Motion is never required to understand state or complete a task. | Verify preferences and any later animation implementation. |
| Responsive | Names, current state, keyboard access, and recovery remain equivalent on mobile/tablet/desktop. | Verify with real viewport and assistive-technology testing. |

Temporary dismissal focus restoration is **N/A** because no temporary interaction is approved. If a disclosure or temporary surface is later approved, Phase 05 must first define open, close, dismissal, focus entry, focus return, keyboard behavior, screen-reader state, and reduced-motion behavior.

## 11. Responsive interaction boundary

- **Mobile:** Same fourteen contracts and same retained destinations.
- **Tablet:** Same fourteen contracts and same retained destinations.
- **Desktop:** Same fourteen contracts and same retained destinations.
- **Material behavior difference:** None approved.
- **Visual composition:** Deferred to later phases.
- **Breakpoint values:** Not defined here.
- **Temporary navigation disclosure:** Not approved.

## 12. Motion and reduced-motion boundary

- Entrance: **N/A by default**.
- Exit: **N/A by default**.
- State transition: **APPLICABLE** whenever a destination, current state, represented content state, origin, or recovery context changes.
- Reduced motion: **APPLICABLE whenever motion exists**.

Every applicable transition defines trigger, system response, feedback, resulting state, persistence/reset, and accessibility behavior even if it is immediate and has no animation.

## 13. Contact boundary

The approved Contact direction is sufficient for Phase 05 remediation:

- **Success:** Contact is reached and approved generic content is presented.
- **Failure:** Contact is unreachable or no Contact content is represented.
- **Global return:** Known represented origin when available; otherwise shared navigation.
- **Product Detail return:** Originating Product Detail when known; broad Catalogue when origin is lost.
- **Abandonment:** Ordinary valid navigation away.
- **Cancellation:** **N/A**.

There are no fields, validation, submission, retry, toast, email delivery, backend, support response, SLA, support ticket, or transmitted product context.

## 14. Persistence and reset boundary

### 14.1 Approved bounded persistence

- shared orientation access remains available;
- current destination persists until another retained destination activates;
- prior broad Catalogue origin persists only for the bounded Product Detail excursion when known;
- represented product identity persists while Product Detail is active; and
- Product Detail origin may persist through the contextual Contact excursion.

### 14.2 Reset events

- another represented product becomes active;
- deliberate navigation to an unrelated retained destination;
- recorded origin becomes invalid or unavailable; or
- prototype restart or bounded-session end.

### 14.3 Forbidden persistence

- Search query;
- Filters;
- Category / Collection;
- sort;
- Cart;
- inventory;
- Contact fields;
- backend state;
- account state; and
- cross-session state or browser-history assumptions.

## 15. Empty, error, and recovery inventory

The approved evidence-safe failure inventory is limited to:

1. unavailable represented product content;
2. unreachable retained destination;
3. missing represented information needed to continue; and
4. broken return path or lost orientation.

| Condition | Communication | Recovery | Explicit non-claim |
| --- | --- | --- | --- |
| Catalogue represented content unavailable | Perceivable represented-content message | Home, Contact, or shared orientation | Not inventory, Search no-results, Filter mismatch, Category empty, or network failure |
| Product Detail content unavailable | Identify missing represented information; retain usable content | Continue, broad Catalogue, or Contact | Not production data loss, inventory, or network failure |
| Retained destination unreachable | Identify affected destination/context | Valid shared destination appropriate to context | Not a server/backend diagnosis |
| Missing information needed to continue | Identify what represented information is absent | Available content, broad Catalogue, Contact, or shared orientation | Not a production data promise |
| Broken return / lost orientation | Explain invalid return/orientation context | Broad Catalogue for Product Detail; Home/shared orientation generally | Not browser-history behavior |

Search no-results, Filter mismatch, Category-empty behavior, inventory failure, network/server error, and Contact submission error are excluded.

## 16. Deferred and removed interactions

| Interaction | Disposition | Phase 05 treatment |
| --- | --- | --- |
| Category / Collection navigation and state | **DEFERRED** | No trigger, result, selection, empty state, or persistence contract. |
| Search | **DEFERRED** | No query, results, no-results, keyboard, recovery, or persistence contract. |
| Filters | **DEFERRED** | No controls, applied state, mismatch, reset, or persistence contract. |
| Sort | **UNAPPROVED / EXCLUDED** | No control or persistent state. |
| Cart | **REMOVED** | No action, indicator, destination, empty state, or persistence. |
| Checkout/payment/purchase | **REMOVED / OUT OF SCOPE** | No transactional contract. |
| Accounts/authentication | **REMOVED / OUT OF SCOPE** | No identity or session contract. |
| Contact form/submission | **REMOVED** | No fields, validation, retry, success/failure feedback, or backend behavior. |
| Price | **OPEN QUESTION / UNKNOWN** | No current interaction or persistence requirement; do not fabricate relevance. |
| Product availability | **OPEN QUESTION / UNKNOWN** | No current interaction, inventory, or unavailable-product control requirement. |
| Production inventory | **OUT OF SCOPE** | No state, loading, error, persistence, or claim. |
| Historical responsive disclosure/mobile-menu ideas | **NOT CURRENTLY APPROVED** | Cannot govern mobile, tablet, or desktop behavior. |
| Historical query/filter/category/Contact-field/menu persistence | **DEFERRED OR REMOVED** | Cannot govern current persistence; menu state is **N/A** because no disclosure exists. |

## 17. Historical disposition and preservation

Historical artifacts may contain Category, Search, Filters, Cart, Contact Request, forms, validation, submission, retry, simulated success/failure, transactional states, inventory, or persistence. Those behaviors remain historical evidence and are not normalized into current scope.

| Historical evidence | Current disposition |
| --- | --- |
| `docs/UX_ASSUMPTIONS.md`, `docs/PRIMARY_FLOW.md`, `docs/INFORMATION_ARCHITECTURE.md`, and other historical documents | Preserved unchanged; supporting or conflicting historical evidence only. |
| `39:2` — `IA — 01 Product Architecture` | Preserved historical Figma evidence. |
| `44:2` — `FLOW — 01 Primary Discovery & Support` | Preserved historical Figma evidence. |
| `61:2` — `FLOW — 02 Canonical User Flow Candidate` | Preserved approved Phase 03 supporting evidence. |
| `70:2` — `IA — 02 Canonical Information Architecture Candidate` | Preserved approved Phase 04 supporting evidence. |
| `90 — Candidates` and `99 — Archive` | Preserved pages; no existing artifact moved, renamed, or overwritten. |

## 18. Traceability

| Phase 02 retained feature | Phase 03 task/flow | Phase 04 architecture | Phase 05 contract | Evidence classification | Supporting source | Figma evidence / history | Disposition |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Site navigation/orientation | Shared global orientation | One shared destination set | IC-01 | **HUMAN-APPROVED DESIGN DECISION** | `docs/02-product-definition.md`; `docs/03-user-flow.md` Global Navigation; `docs/04-information-architecture.md` Global Access | Current `61:2`, `70:2`, `80:2`; historical `39:2`, `44:2` | **RETAINED** |
| Home/Catalogue | UF-01 Home orientation; UF-02 broad Catalogue | Tier 1 Home and Catalogue | IC-02 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2` | **RETAINED** |
| Home/Contact | UF-01 alternate path; UF-04A | Tier 1 Home and global Contact | IC-03 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2` | **RETAINED / NARROWED** to generic Contact |
| Catalogue/Product Detail | UF-02 selection; UF-03 review | Catalogue parent; Product Detail contextual child | IC-04 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2`; historical catalogue concepts preserved | **NARROWED** to broad Catalogue |
| Product Detail/Catalogue | UF-03 approved return | Prior broad Catalogue relationship plus fallback | IC-05 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Product Detail Return; `docs/04-information-architecture.md` Product Detail Architecture | Current `61:2`, `70:2`, `80:2`; historical return preserved | **NARROWED** to bounded origin/fallback |
| Product Detail/Contact | UF-04B | Contextual Contact relationship | IC-06 | **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2` | **NARROWED** to non-submission Contact |
| Contact | Cancellation/abandonment; UF-04A/B recovery | Known-origin/shared-orientation recovery | IC-07 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Contact Flow and Cancellation; `docs/04-information-architecture.md` Contact Architecture | Current `61:2`, `70:2`, `80:2`; historical form behavior preserved only as history | **NARROWED** |
| Information | Information flow | Tier 2 shared destination | IC-08 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2` | **RETAINED** |
| About / Team | About / Team flow | Tier 2 shared destination | IC-09 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2`; historical About naming preserved | **NARROWED** naming |
| Privacy Policy | Privacy Policy flow | Required Tier 2 shared destination; footer optional | IC-10 | **FACT** + **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Current `61:2`, `70:2`, `80:2`; historical footer model preserved | **NARROWED** access semantics |
| All retained destinations | Direct navigation and global orientation | Direct-entry/recovery architecture | IC-11 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Global Navigation; `docs/04-information-architecture.md` Direct Entry / Recovery | Current `61:2`, `70:2`, `80:2` | **RETAINED** |
| Catalogue | UF-02 empty/error/recovery | Catalogue shared destination/parent | IC-12 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Catalogue-level represented content unavailable | Current `61:2`, `70:2`, `80:2`; production claims excluded | **NARROWED** to represented content |
| Product Detail | UF-03 missing-content/recovery | Product Detail missing-content boundary | IC-13 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Product-level represented content unavailable; `docs/04-information-architecture.md` Product Detail Architecture | Current `61:2`, `70:2`, `80:2` | **NARROWED** to represented content |
| Shared orientation and retained destinations | Error states and recovery paths | Direct-entry/recovery and page relationships | IC-14 | **HUMAN-APPROVED DESIGN DECISION** | `docs/03-user-flow.md` Error States/Recovery Paths; `docs/04-information-architecture.md` Direct Entry / Recovery | Current `61:2`, `70:2`, `80:2`; historical technical/error ideas do not govern | **RETAINED / NARROWED** to evidence-safe errors |
| Category / Collection | Excluded | Deferred structure | None | **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Historical `39:2`, `44:2`; exclusion on `61:2`, `70:2`, `80:2` | **DEFERRED** |
| Search | Excluded | Deferred structure | None | **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Historical evidence plus current exclusions | **DEFERRED** |
| Filters | Excluded | Deferred structure | None | **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Historical evidence plus current exclusions | **DEFERRED** |
| Cart | Removed | No destination/state | None | **HUMAN-APPROVED DESIGN DECISION** | Canonical Phases 02–04 | Historical evidence plus current exclusions | **REMOVED** |

The read-only completion audit re-run verified this traceability with no break.

## 19. Figma traceability

| Node | Role | Status |
| --- | --- | --- |
| `80:2` — `INTERACTION — 01 Canonical Interaction Contract Candidate` on `90 — Candidates` | Editable review surface summarizing inventory, state applicability, transitions, recovery, accessibility intent, responsive equivalence, motion, persistence, exclusions, and traceability | **ACCEPTED PHASE 05 REVIEW ARTIFACT / PRESERVED** |
| `61:2` — `FLOW — 02 Canonical User Flow Candidate` | Approved Phase 03 flow evidence | **PRESERVED / SUPPORTING** |
| `70:2` — `IA — 02 Canonical Information Architecture Candidate` | Approved Phase 04 architecture evidence | **PRESERVED / SUPPORTING** |
| `39:2` — `IA — 01 Product Architecture` | Historical architecture evidence | **PRESERVED / HISTORICAL** |
| `44:2` — `FLOW — 01 Primary Discovery & Support` | Historical flow evidence | **PRESERVED / HISTORICAL** |

The Figma candidate is not the canonical specification and is not a polished UI, wireframe, component library, visual-design artifact, coded prototype, or Phase 06 artifact.

## 20. Open questions and later-phase boundaries

- **OPEN QUESTION:** Whether future evidence justifies a temporary responsive navigation disclosure. If approved later, Phase 05 must be amended and re-audited before implementation.
- **OPEN QUESTION:** Whether later implementation needs asynchronous representative content. If so, loading behavior must be added to Phase 05 before implementation.
- **OPEN QUESTION:** Whether Product Detail implementation can restore a represented product neighborhood beyond the originating action. This is permitted only if supported without introducing deferred state.
- **OPEN QUESTION:** Exact visual composition, breakpoint values, typography, color, component anatomy, and animation treatment belong to later phases.
- **OPEN QUESTION:** Production Contact channels, operations, privacy handling, backend behavior, and support outcomes remain outside this prototype contract.

Later Accessibility work must verify implementation using automated and manual testing. Phase 05 does not claim conformance.

## 21. Formal completion record

The approved Phase 05 targeted remediation has produced:

- the one canonical repository interaction-state specification, `docs/05-interaction-contract.md`;
- the editable Figma review candidate `80:2` on `90 — Candidates`;
- explicit state applicability for every playbook state;
- fourteen major interaction contracts;
- interaction-level accessibility intent;
- responsive behavioral equivalence;
- motion/reduced-motion boundaries;
- bounded persistence/reset rules;
- evidence-safe empty/error/recovery behavior;
- explicit deferred/removed scope; and
- repository/Figma traceability with historical preservation.

**READ-ONLY COMPLETION AUDIT RE-RUN:** **PASS**

**PRIOR FIGMA FINDING:** **RESOLVED / PASS**

**FINAL HUMAN APPROVAL:** **APPROVED — October 8, 2026**

**FINAL PHASE STATUS:** **PASS / COMPLETE**

Canonical Phase 05 Figma review artifact:

- `80:2` — `INTERACTION — 01 Canonical Interaction Contract Candidate`

Supporting upstream Figma references preserved:

- `61:2` — `FLOW — 02 Canonical User Flow Candidate`
- `70:2` — `IA — 02 Canonical Information Architecture Candidate`

Historical Figma references preserved:

- `39:2` — `IA — 01 Product Architecture`
- `44:2` — `FLOW — 01 Primary Discovery & Support`

Phase 06 — Visual Direction is the next canonical phase and has not started.
