# ServiPro Database Schema Explained

## 🧠 Overview

The ServiPro database is built using **PostgreSQL with Prisma ORM**, designed to support a complex multi-tenant B2B procurement system.

It handles:

- Users with role-based access
- Tendering and bidding workflows
- Contract lifecycle management
- Commission-based invoicing
- Compliance tracking and audit logs

The schema is heavily relational with strict constraints to ensure data integrity across regulated procurement workflows.

---

## 👤 User System (Core Identity Layer)

### `User`

Central identity table for all platform actors.

Supports:

- ADMIN
- MANAGING_AGENT
- CONTRACTOR

Key Features:

- UUID-based identity
- Soft deletion (`isDeleted`)
- Status lifecycle (`PENDING → APPROVED → REJECTED`)
- Stripe customer integration
- Audit log relations

🔗 Relations:

- ContractorProfile (1–1)
- ManagingAgentProfile (1–1)
- Contracts (as contractor or agent)
- Bids
- Notifications
- Audit logs

---

## 🏢 Managing Agents

### `ManagingAgentProfile`

Stores company-level details for property managers.

Includes:

- Company registration number
- Director details
- Contact information
- Address data

Purpose:
Represents property management firms who create tenders and award contracts.

---

## 🏗️ Contractors

### `ContractorProfile`

Stores verified contractor companies.

Includes:

- Company registration number
- Director details
- Service categories (`companySpecification`)
- Compliance acceptance flag

Constraint:
Only UK limited companies are accepted (enforced at application layer).

---

## 🏢 Buildings

### `Building`

Represents physical properties under management.

Used for:

- Linking tenders to real assets
- Structuring procurement per building

Relationships:

- Belongs to Managing Agent
- Has many Tenders

---

## 📢 Tender System

### `Tender`

Core procurement entity.

Contains:

- Title & description
- Category (service type)
- Deadline & duration
- Compliance requirements (JSON)
- Status lifecycle

Statuses:

- DRAFT
- PUBLISHED
- UNDER_REVIEW
- AWARDED
- CLOSED
- EXPIRED

Relationships:

- Belongs to Managing Agent
- Linked to Building
- Has many Bids
- Generates Contract upon award

---

### `TenderInvitation`

Controls contractor access to tenders.

Features:

- Private invitations
- Status tracking (INVITED, VIEWED, DECLINED, BID_SUBMITTED)
- Unique constraint per contractor/tender

---

## 💰 Bidding System

### `Bid`

Represents contractor proposals.

Includes:

- Amount (Decimal precision)
- Proposal text
- Document uploads
- Status tracking

Constraint:
One bid per contractor per tender.

---

### `BidComplianceDocument`

Stores compliance documents per bid:

- Insurance certificates
- Certifications
- Uploaded files via S3

---

## 📜 Contract System

### `Contract`

Created automatically after tender award.

Tracks:

- Annual contract value
- Commission rate & amount
- Lifecycle dates
- Status (ACTIVE, COMPLETED, TERMINATED, etc.)

Relationships:

- Links Contractor + Managing Agent + Tender

---

## 💳 Commission & Payments

### `CommissionInvoice`

Core revenue tracking entity.

Includes:

- Invoice number
- Commission amount
- Payment status
- PDF invoice storage

Flow:

1. Contract created
2. Commission calculated
3. Invoice generated
4. Payment tracked

---

## 📦 Subscription System

### `ContractorSubscription`

Handles monthly SaaS billing.

Includes:

- Monthly fee
- Stripe subscription ID
- Status lifecycle

---

### `Invoice`

Tracks recurring subscription billing.

---

## 🔔 Notifications System

### `Notification`

System-wide event messaging:

- Tender updates
- Bid actions
- Contract events
- Billing alerts

### `NotificationRead`

Tracks user-level read status for audit clarity.

---

## 📊 Audit System

### `AuditLog`

Critical compliance layer.

Tracks:

- All sensitive entity actions
- Who performed action
- Metadata snapshots
- Tender-linked logs

Purpose:
Ensures full regulatory audit trail for procurement processes.

---

## 🛡️ Compliance & Risk Layer

### `CompanyHealthCheck`

Automated risk profiling:

- Insolvency checks
- Company status validation
- Risk scoring

### `CompanyHealthAlert`

Flags compliance issues:

- Address issues
- Overdue filings
- Insolvency risks

---

## 🧠 Design Philosophy

- Strong relational integrity (no orphan critical records)
- Audit-first architecture
- Separation of identity vs business profiles
- Commission-driven financial model
- Compliance-native data design

---

## ⚙️ Key Design Decisions

- UUID primary keys for security & scalability
- Decimal used for all financial fields
- JSON fields only for flexible compliance data
- Strict unique constraints to prevent duplicate bids/invoices
- Cascading deletes only where business-safe
