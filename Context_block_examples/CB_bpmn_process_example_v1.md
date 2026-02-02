# BPMN Process Model: Customer Support Ticket Submission

## Metadata

| Field | Value |
|-------|-------|
| **ID** | PROC-001 |
| **Type** | bpmn-process |
| **Title** | Customer Portal Support Ticket Submission Process |
| **Owner** | Emma Rodriguez, Customer Support Manager |
| **Status** | approved |
| **Version** | 1.0 |
| **Date** | 2026-01-20T11:00:00Z |

---

## Purpose

### Problem Solved
Manual phone-based support ticket creation is time-consuming, error-prone, and provides no self-service option for customers

### Objective
Document the to-be process for customers to submit support tickets through the portal, ensuring efficiency and proper ticket routing

---

## Content

### Structured Content

#### Process Overview
End-to-end process for customer to create and submit a support request through the Customer Portal, from initial problem identification to ticket confirmation and routing to appropriate support team

#### Process Type
To-Be (Future State)

#### Scope
- **Start Trigger**: Customer identifies an issue and decides to request support
- **End Outcome**: Support ticket created in CRM and assigned to appropriate queue, customer receives confirmation

#### Swim Lanes / Roles
- **Customer**: Initiates support request, provides problem details, receives confirmation
- **Customer Portal**: Validates input, displays forms, stores draft submissions
- **CRM System (Salesforce)**: Creates ticket record, applies routing rules, sends to queue
- **Support Team**: Receives ticket assignment (out of scope - happens after process ends)

#### Process Flow

##### Activities/Tasks
1. **Customer Accesses Support Section** (Customer)
   - Customer navigates to "Contact Support" section in portal after logging in
   
2. **Portal Displays Ticket Form** (Portal)
   - System presents categorized support request form with required fields

3. **Customer Searches Knowledge Base** (Customer)
   - Customer optionally searches FAQs and knowledge articles for self-resolution
   
4. **Customer Fills Ticket Form** (Customer)
   - Customer selects category (Billing, Technical, Account), priority, enters description and optional attachments
   - Portal auto-saves draft every 30 seconds

5. **Portal Validates Input** (Portal)
   - System checks required fields complete, description > 20 characters, attachments < 10MB

6. **Customer Submits Request** (Customer)
   - Customer clicks "Submit" button

7. **Portal Creates Ticket in CRM** (Portal)
   - System calls Salesforce API to create case record with customer ID, category, priority, description, attachments

8. **CRM Routes Ticket** (CRM)
   - Salesforce workflow applies routing rules based on category and priority, assigns to appropriate queue

9. **CRM Sends Confirmation** (CRM)
   - System generates ticket number (CASE-XXXXXX) and returns to portal

10. **Portal Displays Confirmation** (Portal)
    - Portal shows success message with ticket number and estimated response time

11. **Portal Sends Email Confirmation** (Portal)
    - Portal triggers SendGrid to email ticket details and tracking link to customer

##### Gateways/Decision Points
- **Gateway 1: Found Solution in Knowledge Base?**
  - **Yes** → Customer closes portal, process ends (ticket not created)
  - **No** → Customer proceeds to fill ticket form

- **Gateway 2: Form Valid?**
  - **Yes** → Proceed to submit to CRM
  - **No** → Display validation errors, return to form entry

- **Gateway 3: CRM API Success?**
  - **Yes** → Display confirmation
  - **No** → Display error message, save draft locally, offer to retry

##### Events
- **Start Event**: Customer clicks "Contact Support" in portal
- **Intermediate Event (Timer)**: Auto-save timer triggers every 30 seconds during form entry
- **End Event (Success)**: Customer receives ticket number and confirmation email
- **End Event (Self-Resolved)**: Customer finds answer in knowledge base and exits without ticket
- **End Event (Error)**: CRM unavailable, draft saved for later submission

#### Data Objects
- **Ticket Draft**: Stored in portal database during form completion (category, priority, description, attachments)
- **Support Ticket (Case)**: Created in CRM with customer ID, contact info, issue details, timestamp
- **Ticket Confirmation**: Includes ticket number, submission timestamp, estimated response time
- **Email Confirmation**: Customer email with ticket details and tracking URL

#### Business Rules
- All customers must be authenticated to submit tickets (no guest access)
- Maximum 3 attachments per ticket, 10MB total size limit
- Priority automatically elevated to "High" if customer account has premium support plan
- Billing-related tickets with keywords "payment failed" or "overcharge" auto-route to billing specialists
- Technical tickets related to "login" or "password" auto-suggest password reset before ticket creation

#### Process Metrics
- **Average Time to Submit**: Target < 3 minutes from form access to confirmation
- **Knowledge Base Deflection Rate**: Target 20% of customers resolve without ticket
- **API Success Rate**: Target > 99.5% successful CRM submissions
- **Customer Satisfaction**: Post-submission survey target > 4.2/5

---

### Key Decisions

#### Decision 1: Auto-save drafts to reduce data loss
- **Rationale:** Customers may get interrupted or navigate away from form. Auto-save prevents frustration of re-entering information. Draft stored in portal database, not CRM, to avoid creating incomplete tickets.
- **Date:** 2026-01-18

#### Decision 2: Present knowledge base search before ticket form
- **Rationale:** Encourage self-resolution before creating tickets. Even 20% deflection rate saves significant support costs. Knowledge base search is non-intrusive and optional.
- **Date:** 2026-01-19

#### Decision 3: Handle CRM API failures gracefully with local draft storage
- **Rationale:** CRM may occasionally be unavailable. Rather than losing customer input, save draft locally and allow retry or automatic retry when CRM returns. Prevents customer frustration and data loss.
- **Date:** 2026-01-19

---

### Assumptions
- Customers have stable internet connection during ticket submission
- CRM API response time is < 2 seconds for ticket creation
- Email delivery occurs within 2 minutes of ticket submission
- Knowledge base has at least 50 high-quality articles before portal launch

---

### Risks

#### Risk 1: Knowledge base may not deflect enough tickets if content is inadequate
- **Impact:** medium
- **Probability:** medium
- **Mitigation:** Content team to publish 100+ articles covering top 80% of support call reasons before launch. Analyze ticket data monthly to identify content gaps. Measure deflection rate and iterate on knowledge base.

#### Risk 2: CRM routing rules may send tickets to wrong queues
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Thoroughly test routing rules with all category/priority combinations before launch. Support managers review routing logic. Monitor misrouted tickets in first month and adjust rules.

---

## Relations

### Informs
- UC-001
- AC-001
- TEST-001
- NFR-001

### Depends On
- VIS-001
- CTX-001
- STKH-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- All process steps from start to end documented
- All swim lanes (roles) clearly defined
- All decision points have clear criteria and branches
- Exception flows (error conditions) documented
- Process metrics defined with target values
- Validated by process owner (Support Manager)

### Review Checklist
- Reviewed with support team and no concerns raised
- Process tested in workshop with 3 support agents and 2 customers
- BPMN notation follows company standards
- All system interactions validated with development team
- Exception handling adequate for common failure scenarios

---

## AI

### Generation Prompt
Given the Customer Portal vision, context diagram showing CRM integration, and interview notes from customer support manager about current phone-based ticket creation process, generate a detailed BPMN process model for the to-be support ticket submission process through the portal. Include: swim lanes for Customer, Portal, CRM, and Support Team; all activities from customer identifying problem to receiving ticket confirmation; decision gateways for knowledge base search, form validation, and API success; exception flows for CRM unavailable; and data objects like ticket draft, support ticket, and email confirmation. Define process metrics for efficiency and quality.

### Validation Prompt
Review this BPMN process model for completeness and practicality. Check: 1) Are all happy path steps clearly sequenced? 2) Are exception flows realistic and adequately handled? 3) Do decision gateways have clear criteria? 4) Are swim lanes correctly assigned (no steps in wrong swim lane)? 5) Are there any missing steps (e.g., customer receives tracking number)? 6) Are business rules sensible and complete? 7) Are process metrics SMART and achievable? 8) Can this process realistically be completed in the target time? Provide specific recommendations.
