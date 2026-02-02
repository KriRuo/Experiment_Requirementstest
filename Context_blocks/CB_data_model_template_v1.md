# Data Model: [TODO: Add Model Name]

## Metadata

| Field | Value |
|-------|-------|
| **ID** | [TODO: Add unique ID, e.g., DM-001] |
| **Type** | data-model |
| **Title** | [TODO: Add full title] |
| **Owner** | [TODO: Add name and role] |
| **Status** | [TODO: draft/review/approved/archived] |
| **Version** | [TODO: Add version number] |
| **Date** | [TODO: Add ISO 8601 date] |

---

## Purpose

### Problem Solved
[TODO: Describe why this data model is needed, e.g., unclear data structure, integration challenges]

### Objective
[TODO: State the goal, e.g., define logical data structure for the system]

---

## Content

### Structured Content

#### Model Type
[TODO: Conceptual/Logical/Physical]

#### Entities

##### Entity: [TODO: Entity Name]

**Description**: [TODO: What this entity represents]

**Attributes**:

| Attribute Name | Data Type | Size | Required | Description |
|----------------|-----------|------|----------|-------------|
| [TODO: ID] | [TODO: Integer] | [TODO: -] | [TODO: Yes] | [TODO: Primary key] |
| [TODO: Name] | [TODO: String] | [TODO: 255] | [TODO: Yes] | [TODO: Description] |
| [TODO: Attribute] | [TODO: Type] | [TODO: Size] | [TODO: Y/N] | [TODO: Description] |

**Keys**:
- **Primary Key**: [TODO: Field(s)]
- **Foreign Keys**: [TODO: Field -> Referenced Entity.Field]
- **Unique Constraints**: [TODO: Fields that must be unique]

**Business Rules**:
- [TODO: Rule 1]
- [TODO: Rule 2]

##### Entity: [TODO: Entity Name]
[TODO: Repeat for each entity]

#### Relationships

| Parent Entity | Relationship | Child Entity | Cardinality | Description |
|---------------|--------------|--------------|-------------|-------------|
| [TODO: Entity A] | [TODO: has/contains] | [TODO: Entity B] | [TODO: 1:M] | [TODO: Description] |
| [TODO: Entity C] | [TODO: references] | [TODO: Entity D] | [TODO: M:M] | [TODO: Description] |

#### Data Dictionary

##### [TODO: Important Field Name]
- **Definition**: [TODO: Business definition]
- **Format**: [TODO: Format/pattern]
- **Valid Values**: [TODO: Enumeration or range]
- **Source**: [TODO: Where data comes from]
- **Usage**: [TODO: How it's used]

#### Data Quality Rules
[TODO: Define data quality constraints]
- **Completeness**: [TODO: Required fields, no nulls where]
- **Validity**: [TODO: Format and value constraints]
- **Consistency**: [TODO: Cross-field validations]
- **Accuracy**: [TODO: Data verification rules]

#### Data Retention
[TODO: Define retention policies]
- **[TODO: Entity Name]**: [TODO: Retention period and archival strategy]

---

### Key Decisions

#### Decision 1: [TODO: Add decision title]
- **Rationale:** [TODO: Explain why this decision was made]
- **Date:** [TODO: Add date]

---

### Assumptions
[TODO: List assumptions about data structure and usage]
- [TODO: Assumption 1]
- [TODO: Assumption 2]

---

### Risks

#### Risk 1: [TODO: Add data model-related risk]
- **Impact:** [TODO: low/medium/high/critical]
- **Probability:** [TODO: low/medium/high]
- **Mitigation:** [TODO: Describe mitigation strategy]

---

## Relations

### Informs
[TODO: List IDs of deliverables informed by this data model]
- [TODO: ID-001]

### Depends On
[TODO: List IDs of deliverables this depends on]
- [TODO: ID-001]

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
[TODO: Define conditions for model completeness]
- [TODO: All entities and relationships identified]
- [TODO: All attributes have data types]
- [TODO: Keys and constraints defined]

### Review Checklist
[TODO: Define validation points]
- [TODO: Normalized to appropriate level]
- [TODO: Reviewed with data architect]
- [TODO: Business rules captured]

---

## AI

### Generation Prompt
[TODO: Provide prompt for AI to generate data model from requirements or existing database]

### Validation Prompt
[TODO: Provide prompt for AI to validate model normalization and identify issues]
