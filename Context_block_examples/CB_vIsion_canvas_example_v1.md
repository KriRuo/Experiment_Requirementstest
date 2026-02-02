# Vision Canvas: Customer Portal Vision

## Metadata

| Field | Value |
|-------|-------|
| **ID** | VIS-001 |
| **Type** | Vision_Canvas |
| **Title** | Customer Portal Vision |
| **Owner** | Ruohonen Kristoffer, BA |
| **Status** | approved |
| **Version** | 2.0 |
| **Date** | 2026-01-19T10:30:00Z |

---

## Purpose

### Problem Solved
Customers cannot self-serve account information and must call support, resulting in high support costs and customer frustration

### Objective
Enable 80% of customer inquiries to be self-served through an intuitive web portal, reducing support calls by 60% within 6 months

---

## Content

### Structured Content

#### Target Group
Existing customers with active accounts

#### Core Needs
- View account balance and history
- Update contact information
- Download invoices and statements
- Submit support requests

#### Proposed Solution
Responsive web portal with secure authentication, integrated with existing CRM and billing systems

#### Business Goals
- Reduce support call volume by 60%
- Improve customer satisfaction score from 3.2 to 4.5
- Achieve 10,000 active portal users in first quarter

#### Success Metrics
- Portal adoption rate > 70%
- Support ticket reduction > 50%
- Customer satisfaction score > 4.0
- Portal uptime > 99.5%
- Average page load time < 2 seconds

---

### Key Decisions

#### Decision 1: Build responsive web portal rather than native mobile apps
- **Rationale:** Web portal provides cross-platform access with lower development and maintenance costs. Analytics show 85% of customer access would be via desktop or mobile browser
- **Date:** 2026-01-10

#### Decision 2: Integrate with existing CRM rather than build separate customer database
- **Rationale:** Maintains single source of truth, reduces data synchronization complexity, leverages existing security controls
- **Date:** 2026-01-12

---

### Assumptions
- Customers have basic internet literacy
- Existing CRM APIs can support required read/write operations
- Infrastructure team can provision necessary hosting environment
- Customer support team will promote portal adoption

---

### Risks

#### Risk 1: Low customer adoption if portal is not intuitive
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Conduct usability testing with representative customers, implement progressive disclosure, provide contextual help

#### Risk 2: CRM integration performance issues under load
- **Impact:** critical
- **Probability:** medium
- **Mitigation:** Implement caching layer, conduct load testing early, establish SLAs with CRM vendor

---

## Relations

### Informs
- REQ-Portal-001
- REQ-Portal-002
- ARCH-Portal-001
- TEST-Portal-001

### Depends On
- STRATEGY-2026
- STAKEHOLDER-MAP-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- Vision fits on one page
- Target group clearly defined with demographics
- All business goals are SMART (Specific, Measurable, Achievable, Relevant, Time-bound)
- Validated and approved by executive sponsor
- All success metrics have baseline values and targets

### Review Checklist
- Understandable by non-technical stakeholders in under 2 minutes
- Aligned with company strategy and existing initiatives
- All stakeholder concerns addressed or documented
- Scope boundaries are clear (what's in and out)
- Technical feasibility confirmed by architects

---

## AI

### Generation Prompt
Given interview transcripts with executive sponsor, customer support manager, and 5 customers discussing pain points with current customer service model, synthesize a Vision Canvas including: target group characteristics, their top 3 problems, proposed solution approach, 3 measurable business goals with targets, and 5 specific success metrics with baselines and targets. Use practitioner language and ensure all metrics are measurable.

### Validation Prompt
Review this Vision Canvas against BABOK best practices and check for: 1) Are problems and solution clearly aligned? 2) Are all goals SMART? 3) Is scope realistic for 6-month timeline? 4) Are key stakeholder perspectives represented? 5) Are success metrics actually measurable? 6) Are assumptions and risks adequately captured? Provide specific gap analysis and improvement recommendations.
