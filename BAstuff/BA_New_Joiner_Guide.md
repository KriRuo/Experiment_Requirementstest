# BA Quick-Start Guide

A concise reference for BAs joining a new project. Work through the phases in order — but expect to revisit earlier phases as you learn more.

---

## The BA Flow at a Glance

```
Understand Assignment
      ↓
Understand the Problem
      ↓
Understand Vision & Goals
      ↓
Analyse Stakeholders
      ↓
Gather Information
      ↓
Elicit Needs
      ↓
Prioritise Needs
      ↓
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Iterative delivery loop (repeat):
  ├─ Implement backlog items
  ├─ Validate business value
  └─ Inspect the process (retro)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
      ↓
Lessons Learned (after each major increment)
```

---

## Phase 1 — Understand Your Assignment

**Questions to answer:** What is my role? Who do I report to? What outputs am I expected to produce? How does the team collaborate?

| Deliverable | Purpose |
|---|---|
| Task description | Written summary of your responsibilities |
| Collaboration setup | Who, when, how you work with the team |
| Output formats | Agreed formats/tools for your deliverables |

**Tip:** Get this in writing early. Misaligned expectations are the most common BA frustration on new projects.

---

## Phase 2 — Understand the Problem

**Questions to answer:** What is actually broken or missing? Why does the current situation fall short? What are the root causes?

| Deliverable | Purpose |
|---|---|
| Root cause analysis (Fishbone, Heat Map) | Understand why the problem exists, not just what it is |
| Open issues list | Track unresolved questions for follow-up |

**Methods to consider:** Process interviews, Process Mining, Value Stream Mapping.

**Tip:** Don't jump to solutions. Spend real time here — a poorly understood problem produces well-built wrong solutions.

---

## Phase 3 — Understand Vision & Goals

**Questions to answer:** Is there a documented vision? Does leadership align on it? Is the vision shared across the team?

| Deliverable | Purpose |
|---|---|
| Product Position Statement / Vision Canvas | One-page strategic direction, target group, goals, and success metrics |
| Increment Vision | What does success look like for this delivery phase? |
| Product Roadmap | Sequenced plan of increments over time |

**Quality check:** A good Vision Canvas fits on one page and is understandable in under 2 minutes. If stakeholders interpret it differently, it needs work.

**Tip:** If no vision exists yet — facilitate creating one. If one exists but is contested — surface that conflict early rather than letting it derail later work.

---

## Phase 4 — Analyse Stakeholders

**Questions to answer:** Who has a stake? What do they want? Are there conflicts? Are the right people involved?

| Deliverable | Purpose |
|---|---|
| Stakeholder List | All parties with name, role, interest |
| Onion Model | Layers of proximity to the project (core team → affected users → peripheral parties) |
| Stakeholder Map / Power-Interest Grid | Engagement strategy by power and interest |
| Impact Map | Links business goals → actors → impacts → features |
| RACI Matrix | Clarifies who is Responsible, Accountable, Consulted, Informed |

**Common mistake:** Only mapping internal stakeholders. Regulators, operations, and future maintainers are also stakeholders.

**Tip:** Update the stakeholder map regularly — it is never finished.

---

## Phase 5 — Gather Information

**Questions to answer:** What documents, processes, products, standards, and constraints already exist?

| Deliverable | Purpose |
|---|---|
| Glossary | Shared language — prevents misunderstanding across teams |
| Source list | Reference documents used |
| Process documentation (AS-IS) | How things work today |
| Feature Tree | Overview of existing or planned capabilities |
| Constraints & standards | Non-negotiable boundaries (legal, technical, organisational) |

**Methods to consider:** Document analysis, process walkthroughs, competitor analysis, legacy system archaeology.

**Tip:** Build the glossary from day one. Ambiguous terms cause subtle, hard-to-detect requirements defects.

---

## Phase 6 — Elicit Needs

**Questions to answer:** What do stakeholders actually need (not just what they ask for)? What are the pain points? What quality attributes matter?

| Deliverable | Purpose |
|---|---|
| Epics in Product Backlog | Large-grain requirements ready for decomposition |
| Customer Journey / Experience Map | User experience across touchpoints and time |
| Storyboard | Narrative of how the solution fits into work life |
| Personas | Representative user archetypes |
| UX Prototype (if needed) | Early visual validation of key interactions |
| Non-Functional Requirements (NFR Catalog) | Quality attributes: performance, security, usability, reliability (FURPS+) |
| Definition of Done (DoD) | Team-agreed quality bar for "complete" |
| Definition of Ready (DoR) | Checklist before a story enters a sprint |

**Methods to consider:** Workshops, interviews, observation, example mapping, BDD (Given-When-Then).

**Tip:** Elicit needs along the roadmap, biggest pain points, or the feature tree — not randomly. Structure your elicitation sessions.

---

## Phase 7 — Prioritise Needs

**Questions to answer:** What delivers the most value soonest? What can wait? What generates the fastest learning?

| Deliverable | Purpose |
|---|---|
| Prioritised Product Backlog | Ordered list — top items are ready to build |
| Story Map | User journey with horizontal release slices (MVP → v2 → v3) |
| MVP / Concept variants | Early-iteration options for fast validation |

**Methods to consider:** MoSCoW, Kano Model, WSJF (Weighted Shortest Job First).

**Tip:** Prioritisation is not a one-time event. Reprioritise after every iteration based on what you learned.

---

## Phase 8 — Iterative Implementation

Work through the prioritised backlog in short iterations. Collaborate with the team to develop solutions, get fast feedback, and maintain quality.

| Deliverable | Purpose |
|---|---|
| User Stories with Acceptance Criteria | "As a [user], I want [action] so that [benefit]" + Given/When/Then |
| DoD with NFR criteria | Quality gate per story |
| Minimum Viable Product (MVP) | Smallest working slice that delivers real value |
| Automated test cases | Living regression safety net |
| CI/CD pipeline | Continuous integration and delivery enabler |
| Living product documentation | Documentation that evolves with the product |

**Key principle:** Aim for the 80/20 sweet spot. Don't ship bare-minimum and call it done; don't gold-plate either. The right answer is a solution that genuinely serves the validated need.

**Alpha → Beta progression:**
- **Walking Skeleton / MVP** — end-to-end, minimal feature set
- **MMP (Minimal Marketable Product)** — enough to release to real users

---

## Phase 9 — Validate Business Value (Iterative)

After each iteration: did we build the right thing? Are we meeting customer needs and business goals?

| Deliverable | Purpose |
|---|---|
| Assumption verification | Were our story/feature assumptions correct? |
| Feature/goal validation | Are acceptance criteria met in the real context? |
| Reprioritisation | Updated backlog based on learnings |
| Change Requests | Formally captured scope changes |

**Tip:** Measure actual usage and outcomes — not just test pass rates. A feature that passes all tests but nobody uses has no business value.

---

## Phase 10 — Inspect the Process (Iterative)

Regularly reflect: what is working, what is not, what risks are emerging?

| Deliverable | Purpose |
|---|---|
| Improvement measures | Actions to make the process better |
| Risk minimisation actions | Concrete steps to reduce identified risks |

**Tip:** Keep retrospectives short and action-oriented. One good improvement acted on beats ten improvement ideas ignored.

---

## Phase 11 — Lessons Learned (After Major Increments)

Capture what the team learned to avoid repeating mistakes and to improve future work.

| Deliverable | Purpose |
|---|---|
| Lessons Learned report | Documented insights per increment |
| Improvement measures | Actions carried into the next increment |
| RUAs (Risks, Uncertainties, Assumptions) | Explicit capture of what remains unknown |

---

## Cross-Cutting Concerns

These are not tied to a single phase — maintain them throughout the project.

| Concern | Why it matters |
|---|---|
| **Risks** | Inform decisions, requirements, and architecture early |
| **Decisions** | Log key decisions with rationale — future BAs will thank you |
| **Data** | Understand data structures and flow before requirements solidify |
| **NFRs** | Address quality attributes early; retrofitting is expensive |
| **Traceability** | Link requirements → tests → implementation for impact analysis and change management |

---

## Deliverable Quick-Reference

| Phase | Key Artifact | Primary Method |
|---|---|---|
| 1. Assignment | Task description | Onboarding discussion |
| 2. Problem | Fishbone / Heat Map | Root cause analysis |
| 3. Vision | Vision Canvas | Double Diamond |
| 4. Stakeholders | Stakeholder Map + RACI | Power/Interest Grid, Onion Model |
| 5. Information | Glossary, Process docs | Document analysis, interviews |
| 6. Elicitation | Epics, Personas, NFR Catalog | Workshops, BDD, Journey Mapping |
| 7. Prioritisation | Story Map, Prioritised Backlog | MoSCoW, WSJF, Kano |
| 8. Implementation | User Stories + AC + DoD | Scrum, CI/CD, BDD |
| 9. Value validation | Assumption verification | Metrics, user feedback |
| 10. Process check | Improvement actions | Retrospectives |
| 11. Lessons learned | LL Report | Structured review |

---

## Common Mistakes to Avoid

- **Jumping to solutions** before deeply understanding the problem
- **Static stakeholder maps** — update them as the project evolves
- **Vague NFRs** — "fast" and "secure" are not requirements; measurable thresholds are
- **Gold-plating** — building more than the validated need requires
- **Skipping the glossary** — undefined terms create silent defects
- **Creating DoR/DoD without the team** — if they didn't write it, they won't follow it
- **One-time prioritisation** — reprioritise after every iteration

---

## Further Reference

| Resource | Use it when |
|---|---|
| `BA_Methods_Matrix.md` | You have a problem and need the right method |
| `BA_Deliverables_Matrix.md` | You need to produce a specific artifact |
| `AI_Enabled_BA_Deliverables_Catalog.md` | You want AI prompts to accelerate artifact creation |
| `BA_Context_Block_Schema.md` | You need a standard JSON format for any BA deliverable |
| `Context_Blocks_Diagram.md` | You want to understand how all artifacts relate to each other |
