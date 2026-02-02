# Context Diagram: Customer Portal System

## Metadata

| Field | Value |
|-------|-------|
| **ID** | CTX-001 |
| **Type** | context-diagram |
| **Title** | Customer Portal System Context |
| **Owner** | David Lee, Solutions Architect |
| **Status** | approved |
| **Version** | 1.0 |
| **Date** | 2026-01-18T09:00:00Z |

---

## Purpose

### Problem Solved
Unclear system boundaries and integration points for the Customer Portal, creating risk of scope creep and integration challenges

### Objective
Clearly define what is part of the Customer Portal system, what external systems it integrates with, and all data flows across boundaries

---

## Content

### Structured Content

#### System Under Consideration
**Customer Portal**: A responsive web application enabling customers to self-serve account information, update profiles, download documents, and submit support requests

#### System Boundary

**In Scope**:
- Public-facing web application (responsive design)
- Customer authentication and authorization
- Account dashboard and profile management
- Document viewing and download functionality
- Support ticket submission interface
- Portal backend API layer
- Portal database for session and preference data

**Out of Scope**:
- Customer Relationship Management (CRM) system - external
- Billing system - external
- Email delivery system - external
- Identity Provider (Azure AD B2C) - external managed service
- Content Delivery Network - external managed service

#### External Actors

##### Users/Personas
- **Registered Customers**: Primary users who log in to view account information, update profile, download documents, and submit support requests. Access via web browser on desktop or mobile devices.
- **Guest Users**: Anonymous visitors who can only access portal landing page and registration/password reset flows before being redirected to login.
- **Customer Support Agents**: Access portal through admin interface to view customer portal usage for troubleshooting (future phase - not in MVP).

##### External Systems
- **CRM System (Salesforce)**: Authoritative source for customer master data, account information, and support ticket management. Portal reads customer data and writes support tickets to CRM.
- **Billing System (SAP)**: Source of invoice data, payment history, and account balance. Portal reads billing information for display; no write operations.
- **Email Service (SendGrid)**: Handles transactional emails triggered by portal events (password reset, ticket confirmation, document ready notifications).

##### External Services
- **Azure AD B2C**: Identity provider managing customer authentication, password policies, MFA, and session management. Portal delegates all authentication to this service.
- **Azure Blob Storage**: Stores invoice PDFs and account statements. Portal retrieves signed URLs for secure document access.
- **Application Insights**: Monitoring and logging service receiving telemetry, performance metrics, and error logs from portal application.

#### Data Flows

| From | To | Data | Protocol/Method |
|------|-----|------|-----------------|
| Customer Browser | Customer Portal | Login credentials, profile updates, support request | HTTPS/REST API |
| Customer Portal | Azure AD B2C | Authentication request | OAuth 2.0/OpenID Connect |
| Azure AD B2C | Customer Portal | JWT access token | OAuth 2.0/OpenID Connect |
| Customer Portal | CRM (Salesforce) | Customer ID, support ticket details | HTTPS/REST API (Salesforce API) |
| CRM (Salesforce) | Customer Portal | Customer profile, contact details, ticket status | HTTPS/REST API (Salesforce API) |
| Customer Portal | Billing System (SAP) | Customer ID, date range query | HTTPS/OData API |
| Billing System (SAP) | Customer Portal | Invoice list, payment history, balance | HTTPS/OData API |
| Customer Portal | Azure Blob Storage | Document ID | HTTPS/REST (SAS token request) |
| Azure Blob Storage | Customer Portal | Signed URL | HTTPS/REST |
| Customer Portal | Email Service (SendGrid) | Email template, recipient, variables | HTTPS/REST API |
| Customer Portal | Application Insights | Logs, metrics, traces, exceptions | HTTPS (App Insights SDK) |

#### Interfaces

**Authentication Interface (OAuth 2.0/OIDC)**:
- Purpose: Delegate authentication to Azure AD B2C
- Technology: OAuth 2.0 Authorization Code Flow with PKCE
- Security: TLS 1.3, token validation, token refresh handling

**CRM Integration (Salesforce API)**:
- Purpose: Read customer data and write support tickets
- Technology: Salesforce REST API v57.0
- Security: OAuth 2.0 service account, IP allowlisting, field-level encryption for sensitive data
- Rate Limits: 100 API calls per customer session

**Billing Integration (SAP OData API)**:
- Purpose: Read-only access to billing information
- Technology: OData v4 over HTTPS
- Security: Client certificate authentication, read-only service account
- Data Refresh: Cached for 15 minutes to reduce load

**Document Storage (Azure Blob)**:
- Purpose: Secure document retrieval
- Technology: Azure Storage REST API with SAS tokens
- Security: Time-limited SAS tokens (30 minutes), HTTPS only, no direct blob access
- Performance: CDN integration for faster downloads

**Email Service (SendGrid)**:
- Purpose: Send transactional emails
- Technology: SendGrid Web API v3
- Security: API key authentication, IP allowlisting
- Templates: Predefined templates for password reset, ticket confirmation, document notifications

---

### Key Decisions

#### Decision 1: Use Azure AD B2C instead of building custom authentication
- **Rationale:** Reduces development time and security risk. Azure AD B2C provides enterprise-grade security, MFA support, password policies, and is already used by other company applications. Lower total cost of ownership compared to building and maintaining custom authentication.
- **Date:** 2026-01-15

#### Decision 2: Read-only integration with Billing system
- **Rationale:** Writing to billing system introduces data integrity risks and requires complex approval workflows. Portal scope is information access, not transaction processing. Future enhancement if needed.
- **Date:** 2026-01-16

#### Decision 3: Use signed URLs for document access instead of streaming through portal
- **Rationale:** Reduces portal server load, leverages Azure Blob Storage's built-in security and performance. SAS tokens provide time-limited access control without portal being in the data path.
- **Date:** 2026-01-17

---

### Assumptions
- CRM and Billing APIs can handle 100 concurrent requests during peak hours
- Azure AD B2C SLA of 99.9% uptime is acceptable
- Document files in blob storage are already PDF format (no conversion needed)
- Email delivery latency of up to 2 minutes is acceptable

---

### Risks

#### Risk 1: CRM API performance degradation under portal load
- **Impact:** critical
- **Probability:** medium
- **Mitigation:** Implement caching layer for frequently accessed customer data (15-minute TTL), implement circuit breaker pattern for API resilience, conduct load testing with 2x expected peak load, establish SLA with CRM team

#### Risk 2: Azure AD B2C service outage prevents all customer access
- **Impact:** critical
- **Probability:** low
- **Mitigation:** Azure AD B2C has 99.9% SLA. Implement graceful error handling with clear messaging. No mitigation for complete outage as authentication is external dependency. Monitor Azure status page proactively.

#### Risk 3: Billing system API may not support required query patterns efficiently
- **Impact:** high
- **Probability:** medium
- **Mitigation:** Conduct technical spike with billing team to validate API capabilities. If pagination or filtering is limited, implement workarounds or consider building a read replica for portal use.

---

## Relations

### Informs
- DM-001
- NFR-001
- UC-001
- TEST-001
- PROTO-001

### Depends On
- VIS-001
- STKH-001

### Conflicts With
- None

---

## Quality

### Acceptance Criteria
- All external systems identified and confirmed with owners
- All data flows documented with protocols and security mechanisms
- System boundary clearly differentiates in-scope vs external
- Integration points validated as technically feasible
- All external system owners reviewed and approved their interface specifications

### Review Checklist
- Reviewed and approved by Solutions Architect
- Integration approach validated with CRM, Billing, and Security teams
- All authentication flows follow company security standards
- Data flows comply with privacy and compliance requirements (GDPR)
- No missing external systems or actors

---

## AI

### Generation Prompt
Given the Customer Portal vision document, system requirements, and existing enterprise architecture documentation, generate a comprehensive context diagram. Identify: 1) The system under consideration (Customer Portal) and its boundaries, 2) All external actors (users and systems) that interact with the portal, 3) All data flows between the portal and external entities including data exchanged and protocols used, 4) Integration patterns for authentication (Azure AD B2C), CRM integration (Salesforce), billing system integration (SAP), document storage (Azure Blob), and email service (SendGrid). Ensure all interfaces specify technology, security mechanisms, and any rate limits or constraints.

### Validation Prompt
Review this context diagram for completeness and accuracy. Check: 1) Are all external systems that the portal depends on identified? 2) Are data flows bidirectional where appropriate (read and write)? 3) Are integration protocols and technologies realistic and consistent with company standards? 4) Are security mechanisms specified for each interface? 5) Are there any overlooked actors (administrators, external auditors)? 6) Is the system boundary clear and defendable? 7) Are performance and reliability concerns adequately captured for each integration point? Provide specific recommendations.
