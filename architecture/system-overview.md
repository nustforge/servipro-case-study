# ServiPro System Overview

## 🧠 High-Level Architecture

ServiPro is a multi-tenant B2B procurement platform designed for UK property management companies and verified contractors. The system is built around structured tendering, bidding, contract lifecycle management, and commission-based monetisation.

The architecture follows a modular monolith approach with clear domain separation, allowing future scaling into microservices if required.

---

## 🧩 Core System Modules

### 1. Authentication & Role System

- JWT-based authentication
- Role-based access control (RBAC)
  - ADMIN
  - MANAGING_AGENT
  - CONTRACTOR
- Profile separation via `ManagingAgentProfile` and `ContractorProfile`

---

### 2. Tendering System

- Managing Agents create structured tenders linked to buildings
- Tenders include:
  - Category
  - Compliance requirements
  - Deadline
  - Contract duration
- Status flow:
  `DRAFT → PUBLISHED → UNDER_REVIEW → AWARDED / CLOSED`

---

### 3. Bidding System

- Contractors submit bids against published tenders
- Each bid includes:
  - Price (amount)
  - Proposal document
  - Compliance documents
- One contractor = one bid per tender (enforced via constraint)

---

### 4. Contract Lifecycle System

- Automatically created when tender is awarded
- Tracks:
  - Annual value
  - Commission rate
  - Start & end dates
- Lifecycle:
  `ACTIVE → RENEWED → COMPLETED / TERMINATED / EXPIRED`

---

### 5. Commission Engine

- Platform revenue is calculated at contract level
- Commission stored as:
  - percentage rate
  - computed amount
- Invoice generated via `CommissionInvoice`
- Payment tracking:
  `PENDING → PAID → FAILED`

---

### 6. Compliance & Verification Layer

- Contractor verification using:
  - Company registration number
  - Health check (risk scoring)
- Document storage via AWS S3
- Audit-ready compliance tracking per contractor

---

### 7. Notification System

- System-wide event notifications:
  - Tender updates
  - Bid status changes
  - Contract awards
  - Invoice generation
- Stored in database for auditability

---

## 🗄️ Data Architecture Strategy

- PostgreSQL as primary relational database
- Prisma ORM for schema enforcement
- Strong relational integrity with cascading rules
- Indexed fields for:
  - user role
  - tender status
  - contract status
  - deadlines

---

## 🔐 Security Design

- Role-based access control enforced at API layer
- Soft delete strategy for critical entities
- Audit logging for all sensitive actions
- Secure file handling via AWS S3 signed URLs
- No direct payment handling between parties

---

## ⚙️ Scalability Considerations

- Modular domain design allows microservice migration
- Separate logical boundaries for:
  - Tendering
  - Contracts
  - Payments
  - Compliance
- Stateless API design enables horizontal scaling

---

## 🧭 System Philosophy

ServiPro is designed not as a marketplace, but as a **controlled procurement infrastructure system** for regulated property services in the UK.
