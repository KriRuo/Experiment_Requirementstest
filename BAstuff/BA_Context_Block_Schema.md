# BA Context Block 1.0 Schema

## Overview

The **BA Context Block 1.0** is a universal JSON schema designed to standardize the representation of any Business Analyst deliverable. It provides a simple, minimal structure that supports human readability, AI processing, and full traceability.

## Schema Structure

The schema contains **6 main sections** with a total of **33 fields**:

### 1. Metadata
Core identification and tracking information for the deliverable.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | string | Yes | Unique identifier for this context block |
| `type` | string | Yes | Type of BA deliverable (e.g., 'vision', 'process', 'requirement', 'risk') |
| `title` | string | Yes | Human-readable title |
| `owner` | string | Yes | Person or team responsible |
| `status` | string | Yes | Current state: 'draft', 'review', 'approved', 'archived' |
| `version` | string | Yes | Version identifier (e.g., '1.0', '2.1') |
| `date` | string | Yes | Last modification date (ISO 8601 format) |

### 2. Purpose
Why this deliverable exists and what it aims to achieve.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `problemSolved` | string | Yes | The business problem or challenge this deliverable addresses |
| `objective` | string | Yes | The specific goal or outcome this deliverable aims to achieve |

### 3. Content
The actual deliverable content and supporting information.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `structuredContent` | object | Yes | Free-form object to hold type-specific fields |
| `keyDecisions` | array | No | Important decisions made that shaped this deliverable |
| `assumptions` | array | No | Assumptions underlying this deliverable |
| `risks` | array | No | Risks associated with this deliverable |

**keyDecisions** array items contain:
- `decision` (string, required) - The decision that was made
- `rationale` (string, required) - Why this decision was made
- `date` (string, optional) - When the decision was made

**assumptions** array items are strings.

**risks** array items contain:
- `description` (string, required) - Description of the risk
- `impact` (string, required) - Potential impact: 'low', 'medium', 'high', 'critical'
- `probability` (string, required) - Likelihood: 'low', 'medium', 'high'
- `mitigation` (string, optional) - How to mitigate or manage this risk

### 4. Relations
Traceability links to other context blocks.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `informs` | array | No | IDs of context blocks that this block provides input to |
| `dependsOn` | array | No | IDs of context blocks that this block depends on or derives from |
| `conflictsWith` | array | No | IDs of context blocks that have conflicts or tensions with this block |

All relation arrays contain strings (IDs of other context blocks).

### 5. Quality
Quality assurance and validation criteria.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `acceptanceCriteria` | array | Yes | Conditions that must be met for this deliverable to be considered complete |
| `reviewChecklist` | array | Yes | Checklist items for reviewing the quality of this deliverable |

Both arrays contain strings.

### 6. AI
AI prompts for generation and validation.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `generationPrompt` | string | Yes | Prompt that can be used to generate or regenerate this deliverable using AI |
| `validationPrompt` | string | Yes | Prompt that can be used to validate the quality and completeness of this deliverable using AI |

## Design Principles

1. **Universal** - Works for any BA deliverable type (vision, process, requirements, risks, use cases, stakeholder maps, etc.)
2. **Simple** - Only 33 fields, easy to understand and implement
3. **Flexible** - `structuredContent` is a free-form object that adapts to each deliverable type
4. **Traceable** - Built-in support for traceability through the `relations` section
5. **Human-Readable** - Clear field names and descriptions
6. **AI-Friendly** - Deterministic structure with embedded prompts for AI generation and validation
7. **No Complexity** - No inheritance, no advanced JSON Schema features, no optional complexity

## Usage Examples

### Vision Canvas Example

The `structuredContent` for a vision canvas might include:
```json
{
  "structuredContent": {
    "targetGroup": "Existing customers with active accounts",
    "coreNeeds": ["View account balance", "Update contact info"],
    "proposedSolution": "Responsive web portal",
    "businessGoals": ["Reduce support calls by 60%"],
    "successMetrics": ["Portal adoption rate > 70%"]
  }
}
```

### User Story Example

The `structuredContent` for a user story might include:
```json
{
  "structuredContent": {
    "asA": "Customer",
    "iWant": "to view my account balance",
    "soThat": "I can track my spending without calling support",
    "acceptanceCriteria": [
      "Balance is displayed in local currency",
      "Page loads in under 2 seconds"
    ]
  }
}
```

### Process Model Example

The `structuredContent` for a BPMN process might include:
```json
{
  "structuredContent": {
    "processName": "Customer Onboarding",
    "actors": ["Customer", "Sales Rep", "Credit Department"],
    "activities": ["Submit Application", "Review Credit", "Approve Account"],
    "diagramUrl": "https://example.com/bpmn-diagram.png",
    "bpmnXml": "<?xml version=\"1.0\"...>"
  }
}
```

## Validation

To validate an instance against the schema using Python:

```python
import json
import jsonschema

# Load schema
with open('ba-context-block-schema-v1.0.json', 'r') as f:
    schema = json.load(f)

# Load your instance
with open('your-instance.json', 'r') as f:
    instance = json.load(f)

# Validate
jsonschema.validate(instance=instance, schema=schema)
print("✓ Valid!")
```

## Benefits

### For Business Analysts
- **Consistency** - All deliverables follow the same structure
- **Traceability** - Easy to track relationships between deliverables
- **Quality** - Built-in acceptance criteria and review checklists
- **Documentation** - Purpose and decisions are captured alongside content

### For AI Tools
- **Deterministic** - Well-defined structure for parsing and generation
- **Context-Rich** - Embedded prompts provide context for AI operations
- **Traceable** - Clear relationships enable intelligent navigation
- **Validatable** - Structure enables automated quality checks

### For Development Teams
- **Standard Format** - Single schema for all BA deliverables
- **Tool Integration** - Easy to integrate with BA tools and workflows
- **Version Control** - JSON format works well with Git
- **API-Friendly** - Easy to expose via REST APIs

## File Details

- **Schema File**: `ba-context-block-schema-v1.0.json` (201 lines)
- **Example File**: `ba-context-block-example.json` (104 lines)
- **Schema ID**: `https://github.com/KriRuo/Experiment_Requirementstest/ba-context-block-schema-v1.0.json`
- **Schema Draft**: JSON Schema Draft 7
- **Total Fields**: 33 (under 40 limit)

## License

This schema is part of the Experiment_Requirementstest repository and follows the same license terms.

## Related Resources

- [BA Methods Matrix](BA_Methods_Matrix.md) - Problem-to-method lookup guide
- [AI-Enabled BA Deliverables Catalog](AI_Enabled_BA_Deliverables_Catalog.md) - Deliverables with AI acceleration techniques
