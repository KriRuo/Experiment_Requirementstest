# Backlog Item: Submit Support Ticket

## Metadata

| Field | Value |
|-------|-------|
| **ID** | BKI-021 |
| **Type** | backlog-item |
| **Title** | Submit Support Ticket |
| **Owner** | Jane Smith, Lead BA |
| **Status** | approved |
| **Version** | 1.0 |
| **Date** | 2026-01-23T11:00:00Z |

---

## Purpose

### Problem Solved
Customers forced to call support for all issues, creating frustration and high support costs

### Objective
Enable customers to submit support tickets through portal with all necessary details for efficient resolution

---

## Content

### Structured Content

#### Item Type
User Story

#### User Story Format
**As a** logged-in customer
**I want to** create and submit a support ticket through the portal
**So that** I can get help with my issue without calling support

#### Description
Customers can access a support ticket form after logging into the portal. They select a category (Billing, Technical, Account), set priority, enter a detailed description (minimum 20 characters), and optionally attach up to 3 files (max 10MB total). The portal validates the form, creates a ticket in Salesforce CRM, and returns a confirmation with ticket number. Customer receives an email confirmation with ticket details and tracking link.

Key requirements:
- Form auto-saves draft every 30 seconds to prevent data loss
- Knowledge base articles suggested based on category selection to encourage self-resolution
- Ticket creation calls Salesforce API to create Case record
- On success, customer sees ticket number (CASE-XXXXXX) and estimated response time
- On CRM API failure, draft saved locally with option to retry
- Email confirmation sent via SendGrid within 2 minutes

#### Business Value
- **Value Score**: High
- **Priority Rationale**: Core MVP feature directly supporting vision goal of 60% call reduction. Support ticket submission is second most common reason customers call (30% of calls). Enabling self-service ticket creation provides immediate value and measurable ROI. Blocks other support-related stories like ticket tracking.

#### Size Estimate
- **Story Points**: 8
- **Estimated Effort**: 3-4 days (1 day UI, 1 day backend API integration, 1 day testing, 0.5 day email integration, 0.5 day error handling)

#### Acceptance Criteria

1. **Given** I am logged into the portal
   **When** I navigate to "Contact Support" section
   **Then** I see a support ticket form with Category, Priority, Subject, Description, and Attach Files fields

2. **Given** I am filling out the support form
   **When** I pause for 30 seconds
   **Then** the form auto-saves a draft to my browser local storage

3. **Given** I have filled all required fields (Category, Description > 20 chars)
   **When** I click "Submit" button
   **Then** the portal creates a ticket in Salesforce and displays a confirmation with ticket number

4. **Given** I successfully submitted a ticket
   **When** the ticket is created
   **Then** I receive an email confirmation within 2 minutes with ticket details and tracking link

5. **Given** the Salesforce API is unavailable
   **When** I try to submit a ticket
   **Then** I see an error message, the draft is saved locally, and I can retry submission

6. **Given** I select a category (e.g., "Login Issue")
   **When** the form loads
   **Then** I see 3-5 relevant knowledge base articles suggested for self-resolution

7. **Given** I try to attach files larger than 10MB total
   **When** I add the files
   **Then** I see an error message and cannot submit until files are under limit

#### Technical Notes
- Use Salesforce REST API v57.0 for ticket creation (POST to /services/data/v57.0/sobjects/Case)
- Implement retry logic with exponential backoff for API failures (3 attempts)
- Store draft tickets in browser localStorage with 24-hour expiration
- Email service integration via SendGrid API using "Support Ticket Confirmation" template
- Knowledge base suggestions via simple keyword matching (category → articles) - no complex NLP required for MVP
- File uploads should be scanned for viruses before attachment (integrate with existing company antivirus service)

#### Dependencies
- **BKI-007 (Secure Login)**: Must be logged in to access support form
- **CTX-001**: Salesforce API integration pattern defined
- **BKI-020 (Knowledge Base Search)**: Knowledge base articles must exist to suggest
- **External**: Salesforce CRM team to provision API service account and configure case routing rules

#### Attachments
- Wireframe: Support_Ticket_Form_v2.fig (Figma link in project wiki)
- API Spec: Salesforce_Case_API.json
- Error Handling Flow: Support_Ticket_Error_Handling.pdf

---

### Key Decisions

#### Decision 1: Auto-save drafts to localStorage instead of server
- **Rationale:** Simpler implementation, no backend storage needed for drafts, works offline. Drafts expire after 24 hours to avoid stale data. Trade-off: drafts don't sync across devices, but acceptable for MVP.
- **Date:** 2026-01-22

#### Decision 2: Limit attachments to 3 files, 10MB total
- **Rationale:** Prevents abuse and excessive storage costs. Analysis shows 95% of current email tickets have ≤2 attachments under 5MB. Salesforce API has 10MB attachment limit per case.
- **Date:** 2026-01-23

---

### Assumptions
- Salesforce API response time is < 2 seconds for case creation under normal load
- Knowledge base has at least 50 articles before this story is implemented
- Customers will primarily use support ticket for non-urgent issues (urgent issues still via phone)
- File virus scanning service can process files in < 3 seconds

---

### Risks

#### Risk 1: Salesforce API may have rate limits that impact user experience
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Confirm rate limits with Salesforce team (expect 100 API calls/user/hour). Implement queueing mechanism if limits are tight. Monitor API usage and alert if approaching limits.

#### Risk 2: Customers may submit vague or incomplete tickets
- **Impact:** medium
- **Probability:** high
- **Mitigation:** Require minimum 20-character description. Provide helpful placeholder text and examples. Surface knowledge base articles to help customers self-diagnose. Support team can request more info via ticket updates.

---

## Relations

### Informs
- BKI-022 (Track Open Tickets)
- AC-001
- TEST-001

### Depends On
- BKI-007 (Secure Login)
- CTX-001
- BKI-020 (Knowledge Base Search)
- VIS-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- Story meets INVEST criteria (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- All 7 acceptance criteria are specific and testable
- Size estimate agreed by development team
- No open technical questions
- Wireframes approved by UX and product owner
- Dependencies identified and tracked

### Review Checklist
- Story reviewed in backlog refinement session with full team
- Acceptance criteria validated with QA team
- Technical approach reviewed with development lead
- Salesforce integration validated with CRM team
- Size estimate is within sprint capacity (8 points out of 25-30)

---

## AI

### Generation Prompt
Given the Customer Portal vision (60% call reduction goal), user story map showing "Submit Support Ticket" as must-have MVP story, context diagram showing Salesforce CRM integration, and BPMN process model for support ticket submission, generate a detailed backlog item. Include: complete user story format with business value rationale, 7 specific acceptance criteria covering happy path, error handling, and validation, size estimate with breakdown, technical notes on Salesforce API integration and error handling, dependencies on login and knowledge base stories, and risks related to API limits and ticket quality. Ensure story meets INVEST criteria and is ready for development.

### Validation Prompt
Review this backlog item for development readiness and quality. Check: 1) Does it meet all INVEST criteria? 2) Are acceptance criteria specific, testable, and complete? 3) Is size estimate realistic for stated effort? 4) Are technical notes sufficient for implementation without blocking questions? 5) Are all dependencies identified? 6) Are risks realistic and adequately mitigated? 7) Is business value clearly articulated? 8) Can this be completed within one sprint? Provide specific recommendations.
