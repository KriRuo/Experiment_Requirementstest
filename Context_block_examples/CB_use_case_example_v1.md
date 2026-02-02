# Use Case: Customer Views Account Balance

## Metadata

| Field | Value |
|-------|-------|
| **ID** | UC-001 |
| **Type** | use-case |
| **Title** | Customer Views Account Balance and Payment History |
| **Owner** | Jane Smith, Lead BA |
| **Status** | approved |
| **Version** | 1.0 |
| **Date** | 2026-01-24T10:00:00Z |

---

## Purpose

### Problem Solved
Customers must call support to check their account balance and payment history, wasting time and increasing support costs

### Objective
Document the complete interaction flow for customers to view their account information through the portal

---

## Content

### Structured Content

#### Use Case Name
Customer Views Account Balance and Payment History

#### Actors

##### Primary Actor
**Registered Customer**
- **Role**: Individual with an active customer account who has registered for portal access
- **Goal**: Quickly view current account balance and verify recent payments without calling support

##### Secondary Actors
- **CRM System (Salesforce)**: Provides authoritative account balance and status data
- **Billing System (SAP)**: Provides payment transaction history
- **Customer Portal Backend**: Orchestrates data retrieval and caching

#### Preconditions
- Customer has completed registration and email verification
- Customer account exists in CRM and is in active status (not suspended or closed)
- Customer has logged into the portal successfully (authenticated session valid)
- CRM and Billing system APIs are operational

#### Trigger
Customer clicks on "My Account" or "Dashboard" link from portal navigation menu after logging in

#### Main Success Scenario

1. Customer selects "My Account" from the navigation menu
2. Portal backend retrieves customer ID from authenticated session token
3. Portal backend queries CRM API for account summary (balance, status, account number)
4. Portal backend queries Billing API for payment history (last 12 months)
5. Portal backend caches retrieved data with 15-minute TTL to reduce API load
6. System renders Account Dashboard page with account summary section at top
7. System displays current balance prominently with color coding (green if current, red if overdue)
8. System displays account status (Active/Past Due/Suspended) with status icon
9. System displays payment history table with columns: Date, Amount, Payment Method, Reference Number
10. System sorts payment history by date descending (most recent first)
11. Customer views balance and confirms recent payment is reflected
12. Use case ends successfully

#### Alternative Flows

##### Alternative Flow 1: Customer Filters Payment History
- **Condition**: Customer wants to view payments for a specific date range
- **Steps**:
  1. At step 11, customer clicks "Filter" button above payment history table
  2. System displays date range picker (From Date, To Date)
  3. Customer selects date range (e.g., last 3 months)
  4. System filters payment history table to show only payments within selected range
  5. System updates table display
  6. Return to step 11 of main scenario

##### Alternative Flow 2: No Payment History Available
- **Condition**: Customer account has no payments in the last 12 months (new account)
- **Steps**:
  1. At step 4, Billing API returns empty payment list
  2. At step 9, system displays message "No payment history available" in payment history section
  3. System suggests customer to contact billing if they believe this is an error
  4. Use case ends

##### Alternative Flow 3: Customer Views Older Payments
- **Condition**: Customer wants to see payments older than 12 months
- **Steps**:
  1. At step 11, customer clicks "View All History" link below payment table
  2. System navigates to Payment History Details page
  3. System queries Billing API for all payments (past 24 months)
  4. System displays paginated payment history (20 records per page)
  5. Customer can navigate through pages
  6. Use case ends

#### Exception Flows

##### Exception 1: CRM API Timeout or Failure
**Condition**: CRM system is unavailable or responds with error
- **Steps**:
  1. At step 3, CRM API call times out (> 5 seconds) or returns 500 error
  2. System logs error to Application Insights
  3. System displays cached balance if available (with "Last updated" timestamp)
  4. If no cached data, system displays message "Unable to load account information. Please try again later."
  5. System provides "Retry" button
  6. Customer clicks Retry, use case resumes at step 2
  7. If retry fails after 3 attempts, use case ends with error message suggesting customer contact support

##### Exception 2: Billing API Timeout or Failure
**Condition**: Billing system is unavailable or responds with error
- **Steps**:
  1. At step 4, Billing API call times out or returns error
  2. System logs error
  3. System displays cached payment history if available (with "Last updated" timestamp)
  4. If no cached data, system displays message "Payment history temporarily unavailable" in payment section
  5. System still displays account balance (from CRM) if that call succeeded
  6. Use case continues with partial data

##### Exception 3: Session Expired
**Condition**: Customer session has expired during data loading
- **Steps**:
  1. At step 2, portal detects session token is expired
  2. System redirects customer to login page
  3. System displays message "Your session has expired. Please log in again."
  4. Customer logs in
  5. Use case resumes at step 1

##### Exception 4: Account Suspended
**Condition**: Customer account is suspended due to non-payment
- **Steps**:
  1. At step 3, CRM returns account status "Suspended"
  2. System displays account balance and status normally
  3. System displays prominent alert message: "Your account is suspended due to non-payment. Please contact billing to resolve."
  4. System disables certain portal features (e.g., cannot update profile, cannot download documents)
  5. Customer can still view information and submit support tickets
  6. Use case continues with restrictions

#### Postconditions

##### Success Postconditions
- Customer has viewed their current account balance
- Customer has confirmed recent payments are reflected
- Account access is logged in audit trail
- Data is cached for 15 minutes to improve performance for subsequent views

##### Failure Postconditions
- Customer may have viewed stale cached data with timestamp indicating last refresh
- Error is logged to Application Insights for monitoring
- Customer may need to call support if data is unavailable

#### Business Rules
- **BR-001**: Account balance is displayed with 2 decimal places in local currency format
- **BR-002**: Payment history displays last 12 months by default, older records accessible via "View All"
- **BR-003**: Cached data has 15-minute TTL to balance freshness vs API load
- **BR-004**: Balance displayed as red if account is past due (> 30 days overdue)
- **BR-005**: Suspended accounts can view data but have restricted update capabilities

#### Special Requirements
- **Performance**: Dashboard must load in < 2 seconds under normal conditions
- **Performance**: CRM API timeout set to 5 seconds, Billing API timeout set to 5 seconds
- **Security**: Account data transmission must use TLS 1.3
- **Security**: Cached data encrypted at rest
- **Usability**: Dashboard must be mobile-responsive (works on 320px width screens)
- **Accessibility**: Dashboard meets WCAG 2.1 Level AA standards

---

### Key Decisions

#### Decision 1: Cache account data for 15 minutes
- **Rationale:** Balances freshness needs vs API load and performance. Account balance rarely changes within 15 minutes. CRM team concerned about API load if portal queries on every page view. Cache reduces load by 90%+ while maintaining acceptable data freshness.
- **Date:** 2026-01-23

#### Decision 2: Display partial data if one API fails
- **Rationale:** Better user experience to show what's available than fail completely. Account balance (CRM) and payment history (Billing) are independent. Customer gets some value even if one system is down.
- **Date:** 2026-01-24

---

### Assumptions
- Customer has stable internet connection (3G or better)
- CRM and Billing APIs are available 99.5% of the time during business hours
- Payment processing in Billing system completes within 24 hours so portal data is reasonably current
- Customers primarily care about recent payments (last 12 months sufficient for 95% of needs)

---

### Risks

#### Risk 1: Cached data may be stale if payment processed recently
- **Impact:** medium
- **Probability:** medium
- **Mitigation:** Display "Last updated" timestamp with cached data. Provide "Refresh" button for customers to force cache clear. Educate customers that payment processing takes 24 hours.

#### Risk 2: CRM or Billing API performance may degrade under portal load
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Implement caching with 15-minute TTL. Conduct load testing at 2x expected peak load. Establish API performance SLAs with CRM and Billing teams. Implement circuit breaker pattern to fail fast.

---

## Relations

### Informs
- BKI-010
- AC-001
- TEST-001
- NFR-001

### Depends On
- VIS-001
- CTX-001
- BKI-007

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- Main success scenario is complete from trigger to end
- All known alternative flows documented
- All exception conditions handled with clear error messages
- Business rules clearly stated and verifiable
- Performance and security requirements specified
- Validated with actual customer (usability test)

### Review Checklist
- Use case reviewed with customer support team (represent customer perspective)
- Technical feasibility confirmed with development and architecture teams
- CRM and Billing integration patterns validated
- Error handling covers all realistic failure scenarios
- Business rules aligned with company policies

---

## AI

### Generation Prompt
Given the Customer Portal vision, context diagram showing CRM and Billing system integrations, and user story "Customer Views Account Balance," generate a detailed use case specification. Include: primary actor (customer) and secondary actors (CRM, Billing systems), preconditions (authenticated session, active account), complete main success scenario (12+ steps from navigation to viewing data), at least 3 alternative flows (filter payments, no history, view older), 4 exception flows (CRM failure, Billing failure, session expired, account suspended) with graceful degradation, business rules for data formatting and caching, and special requirements for performance (< 2 sec load), security (TLS 1.3), and usability (mobile-responsive). Ensure all flows return to main scenario or end appropriately.

### Validation Prompt
Review this use case for completeness and realism. Check: 1) Is main success scenario detailed enough for implementation? 2) Do alternative flows cover common variations? 3) Are exception flows realistic and properly handled? 4) Are business rules clear and testable? 5) Are special requirements specific and measurable? 6) Are preconditions and postconditions complete? 7) Does error handling provide good user experience? 8) Are there any missing scenarios based on typical account viewing workflows? Provide specific recommendations.
