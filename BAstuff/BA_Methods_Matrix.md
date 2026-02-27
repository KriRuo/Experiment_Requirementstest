# BA Methods Matrix

## Quick Reference Guide for Business Analysts and Requirements Engineers

This matrix helps you quickly identify:
👉 **"I have problem X → which method helps → what do I do → what artifact will I get?"**

---

| Problem / Situation | BA Method | Short Description | Key Steps | Goal | Deliverable |
|---------------------|-----------|-------------------|-----------|------|-------------|
| **Missing or conflicting vision** | Double Diamond + Vision Canvas | Structured discovery and definition of value | 1) Explore problem space<br>2) Synthesize insights<br>3) Define vision canvas<br>4) Validate with stakeholders | Aligned understanding of value | Vision Canvas |
| **No shared product vision** | Impact Mapping | Goal-oriented visual planning connecting business goals to features | 1) Define business goal<br>2) Identify actors<br>3) Map impacts<br>4) List deliverables<br>5) Prioritize paths | Link features to business outcomes | Impact Map |
| **Unknown or unclear stakeholders** | Stakeholder Map + RACI | Visual identification and role clarification of all parties | 1) Brainstorm all stakeholders<br>2) Map by power/interest<br>3) Define RACI for key activities<br>4) Plan engagement strategy | Clear stakeholder landscape and responsibilities | Stakeholder Map, RACI Matrix |
| **Stakeholder conflicts** | Onion Diagram + Power/Interest Grid | Layered stakeholder analysis with engagement planning | 1) Identify core and peripheral stakeholders<br>2) Map power/interest levels<br>3) Define engagement approach<br>4) Document communication plan | Conflict-aware engagement strategy | Stakeholder Analysis Document |
| **Vague or unclear requirements** | User Story Mapping | Visual decomposition of user journey into actionable stories | 1) Define user backbone<br>2) Map user activities<br>3) Break into tasks<br>4) Slice releases horizontally | Shared scope and priorities | Story Map |
| **Requirements too abstract** | Example Mapping | Collaborative exploration using concrete examples | 1) State the rule<br>2) List examples<br>3) Identify edge cases<br>4) Capture questions<br>5) Refine acceptance criteria | Concrete, testable requirements | Example Map, Acceptance Criteria |
| **Conflicting requirements** | Kano Model Analysis | Classify requirements by customer satisfaction impact | 1) Identify features<br>2) Survey stakeholders<br>3) Classify (Must-be, Performance, Delighters)<br>4) Prioritize based on type | Balanced feature portfolio | Kano Classification Matrix |
| **Requirements prioritization unclear** | MoSCoW Prioritization | Structured classification of requirements by necessity | 1) List all requirements<br>2) Classify (Must/Should/Could/Won't)<br>3) Validate with stakeholders<br>4) Document rationale | Clear development priorities | Prioritized Requirements List |
| **Competing priorities in agile** | WSJF (Weighted Shortest Job First) | Economic prioritization based on cost of delay and effort | 1) Score business value<br>2) Score time criticality<br>3) Score risk/opportunity<br>4) Estimate job size<br>5) Calculate WSJF scores | Data-driven priority decisions | WSJF Score Matrix |
| **Unclear business processes** | BPMN Modeling | Standard notation for process visualization and analysis | 1) Identify process boundaries<br>2) Map activities and flows<br>3) Add gateways and events<br>4) Validate with process owners | Documented and analyzable processes | BPMN Diagram |
| **Process bottlenecks unknown** | Value Stream Mapping | Lean analysis of flow efficiency and waste | 1) Map current state flow<br>2) Measure lead and process times<br>3) Identify waste<br>4) Design future state<br>5) Plan improvements | Optimized process flow | Value Stream Map |
| **Complex domain events unclear** | Event Storming | Collaborative domain modeling using domain events | 1) Generate domain events<br>2) Arrange on timeline<br>3) Add commands and aggregates<br>4) Identify bounded contexts | Shared domain understanding | Event Storm Board |
| **System integration uncertainty** | Context Diagram (C4) | Visual representation of system boundaries and integrations | 1) Identify system context<br>2) Map external actors<br>3) Define interfaces<br>4) Document protocols<br>5) Validate completeness | Clear integration landscape | Context Diagram |
| **Interface definitions missing** | API Contract Specification | Formal definition of system interfaces | 1) Identify endpoints<br>2) Define request/response schemas<br>3) Document error scenarios<br>4) Add authentication requirements<br>5) Review with tech leads | Agreed API contracts | OpenAPI/Swagger Specification |
| **Non-functional requirements missing** | NFR Catalog + Quality Attribute Workshop | Systematic elicitation and documentation of quality needs | 1) Review NFR categories (FURPS+)<br>2) Facilitate quality workshops<br>3) Define measurable criteria<br>4) Prioritize quality attributes<br>5) Document constraints | Complete quality requirements | NFR Specification Document |
| **Performance requirements vague** | ATAM (Architecture Tradeoff Analysis Method) | Evaluate architecture against quality attributes | 1) Present business drivers<br>2) Present architecture<br>3) Identify architectural approaches<br>4) Analyze quality attribute scenarios<br>5) Document tradeoffs | Validated architecture decisions | ATAM Report |
| **Validation of assumptions needed** | Prototyping + Usability Testing | Early validation through tangible artifacts | 1) Identify key assumptions<br>2) Create lo-fi/hi-fi prototype<br>3) Define test scenarios<br>4) Test with users<br>5) Analyze feedback | Validated user experience | Prototype, Test Results |
| **User needs uncertain** | Design Sprint | Time-boxed process from problem to tested prototype | 1) Map problem<br>2) Sketch solutions<br>3) Decide approach<br>4) Build prototype<br>5) Test with users | Fast validation of ideas | Validated Prototype |
| **UI/UX requirements unclear** | Wireframes + UI Mockups | Visual representation of interface structure and behavior | 1) Sketch layout<br>2) Define interactions<br>3) Create wireframes<br>4) Review with stakeholders<br>5) Iterate based on feedback | Clear UI requirements | Wireframes, Mockups |
| **Handover to development incomplete** | Definition of Ready (DoR) | Checklist ensuring requirements are development-ready | 1) Define DoR criteria<br>2) Review each story/requirement<br>3) Check completeness<br>4) Obtain team agreement<br>5) Track readiness | Ready-to-implement requirements | Definition of Ready Checklist |
| **Done criteria ambiguous** | Definition of Done (DoD) | Shared quality standard for completed work | 1) Brainstorm done criteria<br>2) Agree on team standards<br>3) Include testing/documentation<br>4) Document and communicate<br>5) Enforce consistently | Consistent quality standards | Definition of Done Checklist |
| **Acceptance criteria unclear** | Specification by Example (BDD) | Concrete examples defining expected behavior | 1) Identify scenarios<br>2) Write Given-When-Then<br>3) Review with stakeholders<br>4) Automate as tests<br>5) Maintain living documentation | Testable, clear criteria | BDD Scenarios (Gherkin) |
| **Test coverage insufficient** | Test Case Specification | Systematic definition of test scenarios | 1) Analyze requirements<br>2) Identify test scenarios<br>3) Define test steps<br>4) Specify expected results<br>5) Review with QA | Comprehensive test coverage | Test Case Document |
| **Legacy system understanding lacking** | System Archaeology + Documentation Mining | Reverse engineering existing system knowledge | 1) Analyze existing code<br>2) Interview subject matter experts<br>3) Review old documentation<br>4) Map system components<br>5) Document findings | Documented legacy system | System Documentation |
| **As-Is process unknown** | Process Mining + Interviews | Data-driven discovery of actual process execution | 1) Extract event logs<br>2) Apply process mining tools<br>3) Interview process participants<br>4) Compare ideal vs. actual<br>5) Document findings | Accurate as-is process model | Process Model, Analysis Report |
| **Data structure or model unknown** | Entity-Relationship Modeling | Visual representation of data entities and relationships | 1) Identify entities<br>2) Define attributes<br>3) Map relationships<br>4) Add cardinality<br>5) Validate with data owners | Clear data structure | ER Diagram, Data Dictionary |
| **Data lineage unclear** | Data Flow Diagram (DFD) | Show how data moves through the system | 1) Identify data sources<br>2) Map transformations<br>3) Define data stores<br>4) Show data flows<br>5) Add data specifications | Understood data movement | Data Flow Diagram |
| **Business case missing or weak** | Business Case Development | Economic justification for initiative | 1) Define problem/opportunity<br>2) Analyze options<br>3) Calculate costs and benefits<br>4) Assess risks<br>5) Make recommendation | Justified investment decision | Business Case Document |
| **ROI unclear** | Cost-Benefit Analysis | Quantitative comparison of costs versus benefits | 1) Identify all costs<br>2) Identify all benefits<br>3) Assign monetary values<br>4) Calculate NPV/ROI<br>5) Perform sensitivity analysis | Financial justification | Cost-Benefit Analysis Report |
| **Change impact unclear** | Impact Analysis | Systematic assessment of change consequences | 1) Identify affected areas<br>2) Assess impact severity<br>3) Identify affected stakeholders<br>4) Plan mitigation<br>5) Document dependencies | Understood change consequences | Impact Analysis Report |
| **Risk assessment needed** | Risk Register + RAID Log | Structured capture and management of risks and issues | 1) Identify risks<br>2) Assess probability and impact<br>3) Define mitigation strategies<br>4) Assign owners<br>5) Monitor and update | Managed project risks | Risk Register, RAID Log |
| **Requirements traceability missing** | Requirements Traceability Matrix (RTM) | Bidirectional mapping of requirements to tests and implementation | 1) List all requirements<br>2) Link to design elements<br>3) Link to test cases<br>4) Track status<br>5) Maintain throughout lifecycle | Full requirements traceability | Traceability Matrix |
| **Scope creep concerns** | Scope Management + Change Control | Formal process for managing scope changes | 1) Document baseline scope<br>2) Define change process<br>3) Establish change board<br>4) Assess each change request<br>5) Update scope documentation | Controlled scope evolution | Scope Statement, Change Log |
| **Feature set too large** | MVP Definition + Feature Slicing | Identify minimum viable feature set for early delivery | 1) Identify core value proposition<br>2) List potential features<br>3) Apply 80/20 rule<br>4) Define MVP scope<br>5) Plan incremental releases | Focused, deliverable MVP | MVP Scope Document |
| **User journey not understood** | User Journey Mapping | Visual narrative of user experience over time | 1) Define user persona<br>2) Map journey stages<br>3) Identify touchpoints<br>4) Capture emotions and pain points<br>5) Identify opportunities | Empathy and improvement opportunities | User Journey Map |
| **Personas unclear** | Persona Development | Research-based user archetypes | 1) Gather user research<br>2) Identify patterns<br>3) Create persona profiles<br>4) Add goals and pain points<br>5) Validate with data | User-centered design focus | Persona Cards |
| **Requirements elicitation needed** | Requirements Workshop | Facilitated collaborative requirements gathering | 1) Plan workshop agenda<br>2) Invite stakeholders<br>3) Facilitate elicitation activities<br>4) Capture requirements<br>5) Confirm understanding | Comprehensive requirements set | Requirements Document |
| **Glossary terms undefined** | Ubiquitous Language + Glossary | Shared vocabulary for domain concepts | 1) Identify domain terms<br>2) Define each term<br>3) Resolve ambiguities<br>4) Document in glossary<br>5) Enforce usage | Common language across team | Glossary, Data Dictionary |

---

## How to Use This Matrix

1. **Identify your challenge** - Find the row that best matches your current situation
2. **Select the method** - Review the recommended BA method
3. **Follow the steps** - Execute the key steps in sequence
4. **Produce the artifact** - Create the specified deliverable
5. **Achieve the goal** - Validate you've reached the intended outcome

## Method Categories

- **Vision & Strategy**: Double Diamond, Vision Canvas, Impact Mapping
- **Stakeholder Management**: Stakeholder Map, RACI, Onion Diagram
- **Requirements**: User Story Mapping, Example Mapping, BDD
- **Prioritization**: MoSCoW, Kano, WSJF
- **Process Modeling**: BPMN, Event Storming, Value Stream Mapping
- **Architecture & Integration**: Context Diagram, API Contracts, ATAM
- **Quality**: NFR Catalog, DoR/DoD, Test Case Specification
- **Validation**: Prototyping, Design Sprint, Wireframes
- **Data**: ER Modeling, DFD, Data Dictionary
- **Business**: Business Case, Cost-Benefit Analysis, ROI
- **Change & Risk**: Impact Analysis, Risk Register, Scope Management

## Standards & Frameworks Referenced

- **IREB** (International Requirements Engineering Board)
- **BABOK** (Business Analysis Body of Knowledge)
- **Agile/Scrum** practices
- **SAFe** (Scaled Agile Framework)
- **Lean/Six Sigma** principles
- **UX/Design Thinking** methods

---

*This matrix is a living document. Update it as you discover effective methods for new problem situations.*
