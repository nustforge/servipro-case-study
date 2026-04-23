# Risk Controls – ServiPro Platform

This document outlines the key risks associated with the ServiPro platform and the controls implemented to mitigate them.

---

## 1. Disintermediation Risk (Bypassing Platform)

### Risk

Managing agents and contractors may attempt to bypass ServiPro after initial introduction.

### Controls

- Non-circumvention contractual clauses
- Platform-based communication and audit tracking
- Commission applied to both new and renewed contracts
- Renewal tracking system linked to platform lifecycle
- Relationship history logs maintained in audit system

---

## 2. Data Integrity & Fraud Risk

### Risk

Contractors may submit false compliance documents or inflated bids.

### Controls

- Mandatory document uploads with verification workflow
- Contractor company validation (UK limited companies only)
- Audit trail for all submissions
- Admin review before approval
- Company health checks integrated into onboarding

---

## 3. Payment & Revenue Risk

### Risk

Failure to collect subscription fees or commission invoices.

### Controls

- Stripe integration for automated subscription billing
- Invoice tracking system with status states (PENDING, PAID, FAILED)
- Automated reminders for overdue payments
- Contract-linked commission enforcement

---

## 4. Compliance & Legal Risk

### Risk

Non-compliance with UK property management regulations.

### Controls

- Contractor verification (insurance, registration checks)
- Category restrictions (only approved service categories)
- Exclusion of utilities and regulated services
- Audit logs for all procurement decisions

---

## 5. Platform Abuse Risk

### Risk

Fake accounts, spam bids, or system misuse.

### Controls

- Role-based access control (Admin, Agent, Contractor)
- Email verification and approval workflow
- Tender invitation-only bidding system option
- Activity monitoring and logs

---

## 6. Operational Risk

### Risk

System downtime or data loss.

### Controls

- Cloud-based architecture (scalable hosting)
- Database backups and migration strategy
- Separation of file storage (AWS S3)
- Error logging and monitoring systems

---

## Summary

ServiPro is designed with enterprise-level controls to ensure trust, compliance, and long-term platform sustainability in a regulated UK property environment.
