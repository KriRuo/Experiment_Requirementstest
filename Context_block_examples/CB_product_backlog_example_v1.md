# Product Backlog: Customer Portal

## Metadata

| Field | Value |
|-------|-------|
| **ID** | BKL-001 |
| **Type** | product-backlog |
| **Title** | Customer Portal Product Backlog |
| **Owner** | Jane Smith, Lead BA / Product Owner |
| **Status** | approved |
| **Version** | 3.0 |
| **Date** | 2026-01-25T14:00:00Z |

---

## Purpose

### Problem Solved
Need centralized, prioritized list of all Customer Portal work to enable iterative delivery and sprint planning

### Objective
Maintain groomed backlog of epics and stories prioritized by business value, ready for development team to pull into sprints

---

## Content

### Structured Content

#### Backlog Summary
- **Total Items**: 47
- **Epic Count**: 6
- **Story Count**: 41
- **Ready for Sprint**: 12

#### Prioritized Backlog Items

| Priority | ID | Type | Title | Business Value | Size | Status | Sprint |
|----------|-----|------|-------|----------------|------|--------|--------|
| 1 | BKI-001 | Epic | User Authentication & Registration | High | 21 | In Progress | Sprint 1-2 |
| 2 | BKI-005 | Story | Customer Account Registration | High | 5 | In Progress | Sprint 1 |
| 3 | BKI-006 | Story | Email Verification Flow | High | 3 | Ready | Sprint 1 |
| 4 | BKI-007 | Story | Secure Login | High | 5 | Ready | Sprint 2 |
| 5 | BKI-008 | Story | Password Reset Flow | High | 5 | Ready | Sprint 2 |
| 6 | BKI-009 | Story | Session Management & Timeout | Medium | 3 | Grooming | Sprint 2 |
| 7 | BKI-002 | Epic | Account Information Display | High | 13 | Not Started | Sprint 3-4 |
| 8 | BKI-010 | Story | Account Dashboard View | High | 8 | Grooming | Sprint 3 |
| 9 | BKI-011 | Story | Payment History Display | High | 5 | Grooming | Sprint 3 |
| 10 | BKI-003 | Epic | Document Management | High | 13 | Not Started | Sprint 4-5 |
| 11 | BKI-015 | Story | Invoice List View | High | 5 | Grooming | Sprint 4 |
| 12 | BKI-016 | Story | Download Invoice PDF | High | 5 | Grooming | Sprint 4 |
| 13 | BKI-017 | Story | Download Account Statements | Medium | 3 | Grooming | Sprint 5 |
| 14 | BKI-004 | Epic | Support Ticket Management | High | 21 | Not Started | Sprint 5-7 |
| 15 | BKI-020 | Story | Knowledge Base Search | Medium | 5 | Grooming | Sprint 5 |
| 16 | BKI-021 | Story | Submit Support Ticket | High | 8 | Not Started | Sprint 6 |
| 17 | BKI-022 | Story | Track Open Tickets | High | 5 | Not Started | Sprint 6 |
| 18 | BKI-023 | Story | View Ticket History | Medium | 3 | Not Started | Sprint 7 |
| 19 | BKI-012 | Story | Profile Management | High | 8 | Not Started | Sprint 7-8 |
| 20 | BKI-013 | Story | Update Contact Information | High | 5 | Not Started | Sprint 7 |
| 21 | BKI-014 | Story | Change Password | High | 3 | Not Started | Sprint 8 |
| 22 | BKI-030 | Epic | Security Enhancements (V2) | Medium | 13 | Backlog | V2 |
| 23 | BKI-031 | Story | Multi-Factor Authentication | Medium | 8 | Backlog | V2 |
| 24 | BKI-040 | Epic | Enhanced Features (V3) | Low | 13 | Backlog | V3 |

#### Epics

##### Epic: User Authentication & Registration (BKI-001)
Complete authentication system integrated with Azure AD B2C enabling customers to register, log in, and manage access securely

**Stories in this Epic**:
- BKI-005: Customer Account Registration
- BKI-006: Email Verification Flow
- BKI-007: Secure Login
- BKI-008: Password Reset Flow
- BKI-009: Session Management & Timeout

**Epic Acceptance Criteria**:
- Customers can self-register with account number and email
- Email verification required before first login
- Login via username/password through Azure AD B2C
- Password reset flow functional via email link
- Sessions timeout after 30 minutes of inactivity

##### Epic: Account Information Display (BKI-002)
Customers can view their account summary, balance, status, and payment history

**Stories in this Epic**:
- BKI-010: Account Dashboard View
- BKI-011: Payment History Display

**Epic Acceptance Criteria**:
- Dashboard shows current balance, account status, last payment
- Payment history displays all payments from past 24 months
- Data synced from CRM within 15 minutes
- Performance: Dashboard loads in < 2 seconds

##### Epic: Document Management (BKI-003)
Customers can view and download invoices and account statements

**Stories in this Epic**:
- BKI-015: Invoice List View
- BKI-016: Download Invoice PDF
- BKI-017: Download Account Statements

**Epic Acceptance Criteria**:
- Invoice list displays all invoices from past 12 months
- PDFs downloadable via secure time-limited URLs
- Documents stored in Azure Blob, accessed via SAS tokens
- Download works on mobile and desktop browsers

##### Epic: Support Ticket Management (BKI-004)
Customers can search knowledge base, create support tickets, and track ticket status

**Stories in this Epic**:
- BKI-020: Knowledge Base Search
- BKI-021: Submit Support Ticket
- BKI-022: Track Open Tickets
- BKI-023: View Ticket History

**Epic Acceptance Criteria**:
- Knowledge base has 100+ articles searchable by keyword
- Support ticket creates case record in Salesforce CRM
- Customer receives ticket number and confirmation email
- Customer can view status of all open tickets
- Ticket creation succeeds >99% of the time

##### Epic: Profile Management (BKI-012)
Customers can update their profile information and security settings

**Stories in this Epic**:
- BKI-013: Update Contact Information
- BKI-014: Change Password

**Epic Acceptance Criteria**:
- Customers can update email, phone, mailing address
- Changes sync to CRM within 5 minutes
- Password change requires current password verification
- Email notification sent when profile updated

##### Epic: Security Enhancements (BKI-030) - V2
Enhanced security features including MFA

**Stories in this Epic**:
- BKI-031: Multi-Factor Authentication

**Epic Acceptance Criteria**:
- Customers can enable SMS or authenticator app MFA
- MFA required for sensitive operations (profile update, document download)
- MFA configuration stored securely in Azure AD B2C

#### Backlog Grooming Notes
- **2026-01-22**: Broke Epic BKI-001 into 5 stories. Estimated as 21 points total. Moved BKI-005, BKI-006, BKI-007 to "Ready" status.
- **2026-01-25**: Reprioritized Knowledge Base Search (BKI-020) above Submit Ticket to encourage self-resolution. Added NFR requirements to Epic BKI-002.

#### Definition of Ready
- Story follows "As a... I want... So that..." format
- Acceptance criteria defined (minimum 3, in Given-When-Then format where applicable)
- Story points estimated by team with consensus
- Dependencies identified and linked
- No blocking questions or unknowns
- Wireframes attached if UI-related
- Technical approach discussed and feasible

---

### Key Decisions

#### Decision 1: Sprint duration of 2 weeks
- **Rationale:** Team velocity unknown initially. Two-week sprints provide good balance of planning overhead vs flexibility. Re-evaluate after Sprint 3.
- **Date:** 2026-01-15

#### Decision 2: Include knowledge base in MVP despite content creation effort
- **Rationale:** Content team committed to 100 articles. Even 15% deflection rate provides immediate value. Search functionality reusable for future features.
- **Date:** 2026-01-20

---

### Assumptions
- Team velocity will stabilize around 25-30 story points per sprint after Sprint 2
- CRM and Billing API integration stories estimated conservatively, may come in faster
- Product owner available for daily questions and weekly backlog refinement
- No major scope additions during MVP (6 months, 12 sprints)

---

### Risks

#### Risk 1: Velocity may be lower than estimated, endangering MVP timeline
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Track velocity closely. After Sprint 3, if velocity is < 20 points, descope lower priority stories (Knowledge Base, Download Statements). Maintain buffer of "Should-have" stories that can be deferred to V2.

#### Risk 2: External dependencies (CRM/Billing APIs) may cause delays
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Technical spikes completed in Sprint 1 to validate API capabilities. Maintain close communication with CRM and Billing teams. Identify workarounds or caching strategies if API performance inadequate.

---

## Relations

### Informs
- REL-001
- TEST-001
- DOR-001

### Depends On
- VIS-001
- USM-001
- STKH-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- All MVP stories (Must-have priority) meet Definition of Ready
- Top 12 stories estimated and ready for Sprint 1-2 planning
- Backlog groomed weekly with product owner
- All epics have clear acceptance criteria
- Dependencies mapped and no circular dependencies

### Review Checklist
- Backlog reviewed weekly in refinement sessions
- Product owner approves all prioritization changes
- Development team comfortable with top stories
- No stories in "Ready" status with open questions
- Epics appropriately sized (can be completed in 2-4 sprints)

---

## AI

### Generation Prompt
Given the Customer Portal user story map with MVP scope defined, vision document, and 6-month timeline across 12 two-week sprints, generate a prioritized product backlog. Create 6 epics covering: Authentication, Account Display, Documents, Support, Profile Management, and V2 Security. Break MVP epics into user stories sized appropriately (3-8 story points). Prioritize stories by business value and dependencies. Assign first 12 stories to Sprint 1-8 planning. For each story provide: ID, type, title, business value (High/Med/Low), estimated size, and status (Ready/Grooming/Not Started/Backlog). Ensure top stories meet Definition of Ready criteria.

### Validation Prompt
Review this product backlog for quality and realism. Check: 1) Are epics appropriately sized and focused? 2) Are story estimates realistic (3-8 points, none too large)? 3) Is prioritization logical based on dependencies and business value? 4) Can estimated 25-30 points/sprint velocity deliver MVP in 12 sprints? 5) Are enough stories in "Ready" status for next 2 sprints? 6) Do stories meet Definition of Ready criteria? 7) Is there a healthy mix of functional and technical stories? Provide specific recommendations.
