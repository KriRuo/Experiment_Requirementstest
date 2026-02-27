# Experiment_Requirementstest

Exploring alternative solution delivery approaches and agentic delivery assets for Business Analysis and Requirements Engineering.

---

## Repository Structure

```text
├── BAstuff/                    # Core BA reference materials
├── Context_block_concept/      # Context Block schema and concept definition
├── Context_block_examples/     # Filled-in Context Block examples
├── Context_blocks_templates/   # Blank Context Block templates (17 types)
├── Blogposts/                  # Blog articles (published and in-progress)
├── ArticleAid/                 # Blog writing support and authoring tools
└── SWDocu_templates/           # Software documentation templates
```

---

## BAstuff — Core BA Resources

Reference materials for Business Analysts and Requirements Engineers.

| File | Description |
| ---- | ----------- |
| [BA_Methods_Matrix.md](BAstuff/BA_Methods_Matrix.md) | Problem-to-method lookup: 38+ scenarios mapped to BA techniques |
| [AI_Enabled_BA_Deliverables_Catalog.md](BAstuff/AI_Enabled_BA_Deliverables_Catalog.md) | 16 BA deliverables with AI acceleration prompts and patterns |
| [BA_Deliverables_Matrix.md](BAstuff/BA_Deliverables_Matrix.md) | Deliverables overview matrix |
| [BA_New_Joiner_Guide.md](BAstuff/BA_New_Joiner_Guide.md) | Quick-start guide for BAs joining a new project |
| [BA_Context_Block_Schema.md](BAstuff/BA_Context_Block_Schema.md) | Documentation for the Context Block Schema v1.0 |
| [Context_Blocks_Diagram.md](BAstuff/Context_Blocks_Diagram.md) | Visualizes relationships between all Context Block types |
| [CDM_BrownBag_series.md](BAstuff/CDM_BrownBag_series.md) | CDM brown-bag session content |

---

## Context Block Concept

The **Context Block Schema v1.0** is a standardized, universal JSON format for any BA deliverable — designed to be both human-readable and deterministic for AI processing.

| File | Description |
| ---- | ----------- |
| [ba-context-block-schema-v1.0.json](Context_block_concept/ba-context-block-schema-v1.0.json) | The JSON schema (source of truth) |
| [ba-context-block-example.json](Context_block_concept/ba-context-block-example.json) | Filled-in example of the schema |
| [BA_Context_Block_Schema.md](Context_block_concept/BA_Context_Block_Schema.md) | Schema field documentation |
| [Context_Blocks_Diagram.md](Context_block_concept/Context_Blocks_Diagram.md) | Relationship diagram between block types |

### Schema at a Glance

A minimal JSON structure (33 fields) covering:

- **Metadata** — id, type, title, owner, status, version, date
- **Purpose** — problemSolved, objective
- **Content** — structuredContent, keyDecisions, assumptions, risks
- **Relations** — informs, dependsOn, conflictsWith
- **Quality** — acceptanceCriteria, reviewChecklist
- **AI** — generationPrompt, validationPrompt

Works for any BA deliverable type. Supports full traceability. Deterministic for AI automation.

---

## Context Block Examples

Filled-in Context Block files showing the schema applied to real deliverable types.

| File | Deliverable Type |
| ---- | ---------------- |
| [CB_vIsion_canvas_example_v1.md](Context_block_examples/CB_vIsion_canvas_example_v1.md) | Vision Canvas |
| [CB_stakeholder_map_example_v1.md](Context_block_examples/CB_stakeholder_map_example_v1.md) | Stakeholder Map |
| [CB_context_diagram_example_v1.md](Context_block_examples/CB_context_diagram_example_v1.md) | Context Diagram |
| [CB_bpmn_process_example_v1.md](Context_block_examples/CB_bpmn_process_example_v1.md) | BPMN Process Model |
| [CB_user_story_map_example_v1.md](Context_block_examples/CB_user_story_map_example_v1.md) | User Story Map |
| [CB_product_backlog_example_v1.md](Context_block_examples/CB_product_backlog_example_v1.md) | Product Backlog |
| [CB_use_case_example_v1.md](Context_block_examples/CB_use_case_example_v1.md) | Use Case Specification |
| [CB_backlog_item_example_v1.md](Context_block_examples/CB_backlog_item_example_v1.md) | Backlog Item |

---

## Context Block Templates

Blank templates for all 17 supported deliverable types — ready to fill in.

| Template | Deliverable |
| -------- | ----------- |
| [CB_vision_canvas_template_v1.md](Context_blocks_templates/CB_vision_canvas_template_v1.md) | Vision Canvas |
| [CB_stakeholder_map_template_v1.md](Context_blocks_templates/CB_stakeholder_map_template_v1.md) | Stakeholder Map |
| [CB_context_diagram_template_v1.md](Context_blocks_templates/CB_context_diagram_template_v1.md) | Context Diagram |
| [CB_bpmn_process_template_v1.md](Context_blocks_templates/CB_bpmn_process_template_v1.md) | BPMN Process Model |
| [CB_user_story_map_template_v1.md](Context_blocks_templates/CB_user_story_map_template_v1.md) | User Story Map |
| [CB_product_backlog_template_v1.md](Context_blocks_templates/CB_product_backlog_template_v1.md) | Product Backlog |
| [CB_backlog_item_template_v1.md](Context_blocks_templates/CB_backlog_item_template_v1.md) | Backlog Item |
| [CB_use_case_template_v1.md](Context_blocks_templates/CB_use_case_template_v1.md) | Use Case Specification |
| [CB_data_model_template_v1.md](Context_blocks_templates/CB_data_model_template_v1.md) | Data Model |
| [CB_nfr_catalog_template_v1.md](Context_blocks_templates/CB_nfr_catalog_template_v1.md) | NFR Catalog |
| [CB_acceptance_criteria_template_v1.md](Context_blocks_templates/CB_acceptance_criteria_template_v1.md) | Acceptance Criteria |
| [CB_prototype_template_v1.md](Context_blocks_templates/CB_prototype_template_v1.md) | Prototype / Wireframe |
| [CB_impact_analysis_template_v1.md](Context_blocks_templates/CB_impact_analysis_template_v1.md) | Impact Analysis |
| [CB_business_case_template_v1.md](Context_blocks_templates/CB_business_case_template_v1.md) | Business Case |
| [CB_definition_of_ready_template_v1.md](Context_blocks_templates/CB_definition_of_ready_template_v1.md) | Definition of Ready |
| [CB_test_concept_template_v1.md](Context_blocks_templates/CB_test_concept_template_v1.md) | Test Concept |
| [CB_release_plan_template_v1.md](Context_blocks_templates/CB_release_plan_template_v1.md) | Release Plan |

---

## Blogposts

Articles exploring AI-augmented delivery and the evolving BA/RE role.

| File | Topic |
| ---- | ----- |
| [Blog_Judgement_and_AI.md](Blogposts/Blog_Judgement_and_AI.md) | Judgement and AI |
| [Blog_Judgement_and_AI_V2.md](Blogposts/Blog_Judgement_and_AI_V2.md) | Judgement and AI (revised) |
| [Blog_Agent_augumented_delivery.md](Blogposts/Blog_Agent_augumented_delivery.md) | Agent-augmented delivery |
| [blog_backlog.md](Blogposts/blog_backlog.md) | Planned topics backlog |

---

## ArticleAid — Blog Writing Tools

Support materials for authoring the blog series.

| File | Purpose |
| ---- | ------- |
| [blog_series_manifesto.md](ArticleAid/blog_series_manifesto.md) | Series framing and editorial direction |
| [blog_article_template.md](ArticleAid/blog_article_template.md) | Reusable article structure template |
| [blog_author_profile.md](ArticleAid/blog_author_profile.md) | Author bio and positioning |
| [blog_master_prompt.md](ArticleAid/blog_master_prompt.md) | Master AI prompt for article generation |
| [blog_validatorlayer.md](ArticleAid/blog_validatorlayer.md) | Quality validator for blog output |

---

## Quick Start

**Working with BA methods?**
Open [BAstuff/BA_Methods_Matrix.md](BAstuff/BA_Methods_Matrix.md) and search for your problem situation.

**Creating a deliverable?**
Open [BAstuff/AI_Enabled_BA_Deliverables_Catalog.md](BAstuff/AI_Enabled_BA_Deliverables_Catalog.md) and find your artifact with AI prompts.

**Using Context Blocks?**
Start with [Context_block_concept/ba-context-block-schema-v1.0.json](Context_block_concept/ba-context-block-schema-v1.0.json), pick a template from [Context_blocks_templates/](Context_blocks_templates/), and see a filled-in example in [Context_block_examples/](Context_block_examples/).

**New to the project as a BA?**
Read [BAstuff/BA_New_Joiner_Guide.md](BAstuff/BA_New_Joiner_Guide.md) first.
