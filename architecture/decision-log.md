# 🧠 Architecture Decision Log (ADL) – ServiPro

This document records key technical and architectural decisions made during the design and development of the ServiPro platform. It helps maintain transparency, traceability, and long-term maintainability.

---

## 1. Multi-Tenant Architecture Choice

### Decision

Adopted a **single database, multi-tenant architecture** using `salon_id / user role separation pattern (adapted for property management domains)`.

### Reason

- Supports scaling across multiple managing agents
- Reduces infrastructure complexity vs multi-database model
- Easier reporting and global admin oversight

### Trade-offs

- Requires strict row-level access control
- Increased risk of data leakage if queries are not properly scoped

---

## 2. Role-Based Access Control (RBAC)

### Decision

Implemented strict RBAC using three primary roles:

- ADMIN
- MANAGING_AGENT
- CONTRACTOR

### Reason

- Clear separation of platform responsibilities
- Simplifies permission logic across dashboards
- Aligns with real-world business workflow

### Trade-offs

- Slight complexity in middleware authorization logic
- Requires consistent enforcement across API routes

---

## 3. Prisma + PostgreSQL Adoption

### Decision

Used **Prisma ORM with PostgreSQL** as the primary database layer.

### Reason

- Strong type safety for large schema (50+ models)
- Easy migration handling
- Excellent developer experience with TypeScript
- Supports relational integrity for complex tender flows

### Trade-offs

- Slight performance overhead compared to raw SQL in extreme cases
- Requires careful indexing strategy for scaling

---

**Tender → Bid → Awarded Contract → Commission Tracking → Renewal**

### Decision

Designed a strict lifecycle:

### Reason

- Mirrors real UK property procurement workflows
- Ensures auditability and compliance tracking
- Enables structured financial tracking (commission model)

### Trade-offs

- More relational complexity
- Requires careful state management

---

## 5. Commission-Based Revenue Model Enforcement

### Decision

Platform does NOT handle client-to-contractor payments.

### Reason

- Reduces regulatory/payment handling burden
- Keeps platform focused on SaaS + marketplace layer
- Ensures scalable revenue via:
  - Subscription fees
  - Commission on contracts

### Trade-offs

- Requires strong enforcement of non-circumvention rules
- Dependency on legal contract enforcement

---

## 6. Audit Log System

### Decision

Implemented full system-wide audit logging via `AuditLog` model.

### Reason

- Required for compliance in property management sector
- Provides transparency for managing agents
- Tracks all critical actions (tenders, bids, contracts)

### Trade-offs

- Additional storage overhead
- Requires performance-aware indexing

---

## 7. File Storage via AWS S3

### Decision

All documents stored in **AWS S3 (not database blobs)**.

### Reason

- Scalable file storage
- Secure signed URLs for access control
- Supports compliance documentation at scale

### Trade-offs

- External dependency on AWS
- Requires proper IAM configuration

---

## 8. Notification System Design

### Decision

Hybrid notification system:

- Database stored notifications
- Optional real-time updates via Pusher

### Reason

- Ensures persistence + real-time UX
- Allows offline notification history

### Trade-offs

- Dual system complexity
- Requires sync handling between DB and real-time layer

---

## 9. Contractor Verification Model

### Decision

Only UK Limited Companies allowed (no sole traders).

### Reason

- Ensures professional-grade contractors
- Reduces risk for managing agents
- Aligns with UK property compliance expectations

### Trade-offs

- Reduced contractor supply pool
- Requires verification workflows (Company House checks)

---

## 10. Subscription + Commission Hybrid Billing

### Decision

Two-layer billing system:

- Monthly subscription (access fee)
- Commission per awarded contract

### Reason

- Stable recurring revenue
- Performance-based earnings model
- Scales with contractor success

### Trade-offs

- Requires invoice orchestration system
- More complex financial tracking

---

## 📌 Summary

ServiPro architecture prioritizes:

- Compliance
- Auditability
- Long-term scalability
- Real-world property management workflows

Every decision is aligned with UK property industry requirements and enterprise-grade SaaS expectations.
