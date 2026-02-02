# Stakeholder Map: Customer Portal Project

## Metadata

| Field | Value |
|-------|-------|
| **ID** | STKH-001 |
| **Type** | stakeholder-map |
| **Title** | Customer Portal Project Stakeholder Map |
| **Owner** | Jane Smith, Lead BA |
| **Status** | approved |
| **Version** | 1.0 |
| **Date** | 2026-01-15T14:00:00Z |

---

## Purpose

### Problem Solved
Unclear stakeholder landscape and communication needs for the Customer Portal initiative, risking misaligned expectations and inadequate engagement

### Objective
Identify all key stakeholders, classify their power and interest levels, and define appropriate engagement strategies for successful portal delivery

---

## Content

### Structured Content

#### Stakeholders

##### High Power, High Interest
- **Sarah Chen, VP Customer Experience**: Champion for customer self-service. Needs weekly progress updates and involvement in major design decisions. Primary decision-maker.
- **Michael Torres, IT Director**: Responsible for technical approval and infrastructure provisioning. Requires technical review sessions and architecture sign-offs.
- **Emma Rodriguez, Customer Support Manager**: Key user representative. Needs to validate solution addresses support pain points. Provide input on FAQs and help content.

##### High Power, Low Interest
- **Robert Kim, CFO**: Budget approval authority. Needs monthly financial reports and ROI updates. Keep informed of cost impacts.
- **Lisa Anderson, CISO**: Security compliance approval required. Review security architecture and data protection approach. Needs quarterly security briefings.

##### Low Power, High Interest
- **Support Team (15 agents)**: End users who will promote portal to customers. Need training and early access for feedback. Champions for customer adoption.
- **Alex Johnson, UX Designer**: Design contributor. Highly engaged in user research and interface design. Needs to be consulted on all UX decisions.
- **Customer Advisory Board (5 members)**: Represent customer perspective. Participate in usability testing and provide feedback on features.

##### Low Power, Low Interest
- **Finance Operations Team**: Invoicing process may change slightly. Keep informed via email updates at key milestones.
- **Legal Team**: Review terms of service. Involve during UAT phase for final approval.

#### RACI Matrix

| Activity | Responsible | Accountable | Consulted | Informed |
|----------|-------------|-------------|-----------|----------|
| Vision Definition | Jane Smith (BA) | Sarah Chen (VP) | Emma Rodriguez | All Stakeholders |
| Requirements Gathering | Jane Smith | Jane Smith | Support Team, Customers | Sarah Chen, Michael Torres |
| Architecture Design | David Lee (Architect) | Michael Torres | Lisa Anderson | Sarah Chen |
| UI/UX Design | Alex Johnson | Sarah Chen | Customer Advisory Board | Emma Rodriguez |
| Development | Dev Team Lead | Michael Torres | David Lee | Sarah Chen, Jane Smith |
| Security Review | Security Team | Lisa Anderson | Michael Torres | Sarah Chen |
| UAT | Support Team | Emma Rodriguez | Customer Advisory Board | All Stakeholders |
| Go-Live Approval | Sarah Chen | Robert Kim | Michael Torres, Lisa Anderson | All Stakeholders |

#### Engagement Strategy
**High Power, High Interest (Manage Closely)**: Weekly steering committee meetings, early involvement in key decisions, regular 1:1s for feedback

**High Power, Low Interest (Keep Satisfied)**: Monthly executive summaries, involve only for critical approvals, respect their time with concise communications

**Low Power, High Interest (Keep Informed)**: Bi-weekly team updates, invite to demos and workshops, create feedback channels

**Low Power, Low Interest (Monitor)**: Quarterly email updates, inform at major milestones only

---

### Key Decisions

#### Decision 1: Establish Customer Advisory Board for ongoing input
- **Rationale:** Direct customer involvement critical for validating features meet real needs and ensuring high adoption. Five volunteer customers from different segments provide diverse perspectives without being unmanageable.
- **Date:** 2026-01-10

#### Decision 2: Weekly steering committee with high power/high interest stakeholders
- **Rationale:** Regular touchpoints ensure alignment, quick resolution of issues, and maintain executive visibility without micro-management.
- **Date:** 2026-01-12

---

### Assumptions
- Support team will have 2-3 hours per week available for portal training and testing
- Customer Advisory Board members will commit to monthly 1-hour sessions
- IT infrastructure team can provision test environments within standard timelines
- Executive stakeholders will maintain engagement throughout 6-month project

---

### Risks

#### Risk 1: Support team resistance if not adequately involved in design
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Include support representatives in all major design reviews, conduct early training sessions, emphasize how portal reduces their workload and enables them to handle complex issues

#### Risk 2: CFO may reduce budget if ROI not clearly communicated
- **Impact:** critical
- **Probability:** low
- **Mitigation:** Monthly financial dashboards showing cost savings trajectory, highlight early wins like reduced call volume, maintain clear business case documentation

---

## Relations

### Informs
- VIS-001
- CTX-001
- UC-001
- TEST-001

### Depends On
- None

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- All stakeholders with decision-making authority identified
- Power/interest classification validated with project sponsor
- RACI matrix has no gaps or conflicts
- Engagement strategy defined for each stakeholder group
- Communication plan approved by all high power stakeholders

### Review Checklist
- Stakeholder map reviewed with project sponsor (Sarah Chen)
- All identified stakeholders notified of their role
- RACI matrix socialized with team and no concerns raised
- Engagement frequencies realistic for team capacity
- No overlooked stakeholder groups

---

## AI

### Generation Prompt
Given the Customer Portal project charter, organizational chart, and interview notes from the project kickoff meeting, generate a comprehensive stakeholder map. Classify each stakeholder using the power/interest grid (high power high interest, high power low interest, low power high interest, low power low interest). For each stakeholder, include: name, role, their stake in the project, key concerns, and recommended engagement approach. Create a RACI matrix for the 8 major project activities: Vision Definition, Requirements Gathering, Architecture Design, UI/UX Design, Development, Security Review, UAT, and Go-Live Approval. Ensure all roles are assigned appropriately with no gaps.

### Validation Prompt
Review this stakeholder map for completeness and effectiveness. Check: 1) Are all key decision-makers identified? 2) Is the power/interest classification realistic? 3) Does the RACI matrix have clear accountability for each activity? 4) Are there any conflicting assignments (multiple Accountable roles)? 5) Is the engagement strategy appropriate for each group and sustainable for the team? 6) Are any critical stakeholder groups missing (security, compliance, finance, operations)? Provide specific recommendations for improvements.
