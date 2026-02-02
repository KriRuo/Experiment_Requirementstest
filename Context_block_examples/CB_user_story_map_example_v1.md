# User Story Map: Customer Portal MVP

## Metadata

| Field | Value |
|-------|-------|
| **ID** | USM-001 |
| **Type** | user-story-map |
| **Title** | Customer Portal User Story Map |
| **Owner** | Jane Smith, Lead BA |
| **Status** | approved |
| **Version** | 2.0 |
| **Date** | 2026-01-22T10:00:00Z |

---

## Purpose

### Problem Solved
Unclear product scope and difficulty prioritizing features for Customer Portal releases

### Objective
Visualize complete customer journey through portal and identify MVP vs future release scope

---

## Content

### Structured Content

#### User Backbone (High-Level Activities)
1. Discover Portal
2. Register/Login
3. View Account Information
4. Manage Profile
5. Access Documents
6. Get Support

#### User Tasks and Stories

##### Activity: Discover Portal

###### User Tasks
- Learn portal exists
- Understand portal benefits
- Access portal URL

###### User Stories

**Story 1**: Marketing Landing Page
- **As a** prospective portal user
- **I want to** see a landing page explaining portal features
- **So that** I understand what I can do before registering
- **Priority**: Should-have
- **Release**: MVP

##### Activity: Register/Login

###### User Tasks
- Create account
- Verify email
- Login with credentials
- Reset forgotten password
- Enable MFA

###### User Stories

**Story 1**: Account Registration
- **As a** new customer
- **I want to** register for portal access using my account number and email
- **So that** I can start self-serving
- **Priority**: Must-have
- **Release**: MVP

**Story 2**: Email Verification
- **As a** newly registered user
- **I want to** verify my email address through a confirmation link
- **So that** my account is secure
- **Priority**: Must-have
- **Release**: MVP

**Story 3**: Secure Login
- **As a** registered customer
- **I want to** log in with username and password
- **So that** I can access my account information
- **Priority**: Must-have
- **Release**: MVP

**Story 4**: Password Reset
- **As a** customer who forgot password
- **I want to** reset my password via email link
- **So that** I can regain access to my account
- **Priority**: Must-have
- **Release**: MVP

**Story 5**: Multi-Factor Authentication
- **As a** security-conscious customer
- **I want to** enable MFA on my account
- **So that** my data is protected from unauthorized access
- **Priority**: Should-have
- **Release**: V2

##### Activity: View Account Information

###### User Tasks
- See account summary
- View current balance
- Check payment history
- Review account status

###### User Stories

**Story 1**: Account Dashboard
- **As a** logged-in customer
- **I want to** see dashboard with account summary (balance, status, recent activity)
- **So that** I quickly understand my account health
- **Priority**: Must-have
- **Release**: MVP

**Story 2**: Payment History
- **As a** customer
- **I want to** view list of all payments with dates and amounts
- **So that** I can verify payments were processed
- **Priority**: Must-have
- **Release**: MVP

**Story 3**: Account Activity Feed
- **As a** customer
- **I want to** see chronological feed of recent account activity
- **So that** I stay informed of changes
- **Priority**: Could-have
- **Release**: V3

##### Activity: Manage Profile

###### User Tasks
- Update contact information
- Change communication preferences
- Update password

###### User Stories

**Story 1**: Update Contact Info
- **As a** customer
- **I want to** update my email address, phone number, and mailing address
- **So that** company can reach me via correct channels
- **Priority**: Must-have
- **Release**: MVP

**Story 2**: Communication Preferences
- **As a** customer
- **I want to** opt in/out of marketing emails and SMS
- **So that** I control how company contacts me
- **Priority**: Should-have
- **Release**: V2

**Story 3**: Change Password
- **As a** logged-in customer
- **I want to** change my password from within portal
- **So that** I can maintain account security
- **Priority**: Must-have
- **Release**: MVP

##### Activity: Access Documents

###### User Tasks
- View invoice list
- Download invoices
- Download statements
- Search documents by date

###### User Stories

**Story 1**: Invoice List
- **As a** customer
- **I want to** see list of all my invoices with dates and amounts
- **So that** I can find specific invoices to download
- **Priority**: Must-have
- **Release**: MVP

**Story 2**: Download Invoice PDF
- **As a** customer
- **I want to** download invoice as PDF
- **So that** I can save it for my records
- **Priority**: Must-have
- **Release**: MVP

**Story 3**: Download Statement
- **As a** customer
- **I want to** download monthly account statements
- **So that** I have official records for accounting
- **Priority**: Should-have
- **Release**: MVP

**Story 4**: Search Documents
- **As a** customer
- **I want to** filter documents by date range and type
- **So that** I quickly find what I need
- **Priority**: Could-have
- **Release**: V2

##### Activity: Get Support

###### User Tasks
- Browse FAQs
- Submit support ticket
- Track ticket status
- View ticket history

###### User Stories

**Story 1**: Knowledge Base Search
- **As a** customer with a question
- **I want to** search knowledge base articles and FAQs
- **So that** I can self-resolve common issues
- **Priority**: Should-have
- **Release**: MVP

**Story 2**: Submit Support Ticket
- **As a** customer needing help
- **I want to** create support ticket with category, priority, and description
- **So that** support team can assist me
- **Priority**: Must-have
- **Release**: MVP

**Story 3**: Track Ticket Status
- **As a** customer who submitted ticket
- **I want to** view status of my open tickets
- **So that** I know when to expect resolution
- **Priority**: Must-have
- **Release**: MVP

**Story 4**: Ticket History
- **As a** customer
- **I want to** view all my past tickets and their resolutions
- **So that** I can reference previous issues
- **Priority**: Could-have
- **Release**: V2

#### Release Slices

##### MVP (Release 1) - Month 6
- Account Registration (USM-001-2-1)
- Email Verification (USM-001-2-2)
- Secure Login (USM-001-2-3)
- Password Reset (USM-001-2-4)
- Account Dashboard (USM-001-3-1)
- Payment History (USM-001-3-2)
- Update Contact Info (USM-001-4-1)
- Change Password (USM-001-4-3)
- Invoice List (USM-001-5-1)
- Download Invoice PDF (USM-001-5-2)
- Download Statement (USM-001-5-3)
- Knowledge Base Search (USM-001-6-1)
- Submit Support Ticket (USM-001-6-2)
- Track Ticket Status (USM-001-6-3)

**MVP Value**: Core self-service capabilities that reduce 60% of support calls

##### Release 2 - Month 9
- Multi-Factor Authentication (USM-001-2-5)
- Communication Preferences (USM-001-4-2)
- Search Documents (USM-001-5-4)
- Ticket History (USM-001-6-4)

**V2 Value**: Enhanced security and improved user experience based on MVP feedback

##### Release 3 - Month 12
- Marketing Landing Page (USM-001-1-1)
- Account Activity Feed (USM-001-3-3)

**V3 Value**: Increased portal awareness and deeper engagement features

#### Dependencies
- **Email Verification** depends on **Account Registration**: Can't verify until account exists
- **Secure Login** depends on **Email Verification**: Account must be verified before allowing login
- **All Activity 3-6 stories** depend on **Secure Login**: Must be authenticated to access any portal features
- **Track Ticket Status** depends on **Submit Support Ticket**: Need tickets to track
- **Download Invoice PDF** depends on **Invoice List**: Need to display list before downloads

---

### Key Decisions

#### Decision 1: Include knowledge base search in MVP
- **Rationale:** Even if deflection rate is 15-20%, this provides immediate ROI and reduces ticket volume from day one. Content team committing to 100 articles before launch makes this viable.
- **Date:** 2026-01-20

#### Decision 2: MFA deferred to V2
- **Rationale:** Azure AD B2C provides basic security. MFA adds complexity for user adoption. MVP focuses on proving core value. Security review confirmed MFA not required for launch with current data sensitivity.
- **Date:** 2026-01-21

---

### Assumptions
- Customers comfortable with self-registration process (minimal support needed)
- Most customers access portal from desktop initially (mobile optimization can come post-MVP)
- Support team can handle ticket volume during portal adoption ramp-up

---

### Risks

#### Risk 1: MVP scope may be too large for 6-month delivery
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Backlog is prioritized clearly. If timeline pressure, deprioritize Download Statement and Knowledge Base Search from MVP without breaking core value proposition.

#### Risk 2: Customers may not discover portal without marketing
- **Impact:** medium
- **Probability:** high
- **Mitigation:** Support team to mention portal on every call. Email campaign to all customers at launch. Add portal link to invoices. Track adoption weekly and adjust marketing if needed.

---

## Relations

### Informs
- BKL-001
- REL-001
- AC-001

### Depends On
- VIS-001
- STKH-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- All major user activities identified and sequenced logically
- MVP scope clearly defined and agreed by product owner
- All stories follow good user story format (As a... I want... So that...)
- Dependencies between stories identified
- Release slicing validated against 6-month MVP timeline

### Review Checklist
- Story map workshop conducted with product owner, support team, and 2 customers
- MVP stories can deliver target 60% call reduction
- No critical user journeys missing from map
- Story priorities align with vision and business goals
- Dependencies are realistic and don't create bottlenecks

---

## AI

### Generation Prompt
Given the Customer Portal vision document stating goal to reduce support calls by 60%, interview transcripts from 5 customers about their pain points, and support call data showing top customer inquiries, generate a comprehensive user story map. Organize around the user backbone of: Discover Portal, Register/Login, View Account Information, Manage Profile, Access Documents, and Get Support. For each activity, break down into user tasks and write user stories in "As a... I want... So that..." format. Prioritize using Must-have, Should-have, Could-have. Slice into 3 releases with MVP delivering core self-service within 6 months. Identify dependencies between stories.

### Validation Prompt
Review this user story map for completeness and effective prioritization. Check: 1) Does MVP scope deliver stated vision of 60% call reduction? 2) Are all critical user journeys represented? 3) Do stories follow good format with clear business value? 4) Are priorities realistic (not everything is "Must-have")? 5) Is MVP scope achievable in 6 months? 6) Are there any missing activities or tasks based on typical customer portal functionality? 7) Are dependencies correct and complete? Provide specific recommendations for improvements.
