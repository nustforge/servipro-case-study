# Invoice Flow – ServiPro

## 🧠 Overview

The Invoice Flow defines how ServiPro generates, tracks, and manages financial transactions related to:

- Contractor subscriptions (SaaS revenue)
- Commission invoices (success-based revenue)
- Payment status tracking and reconciliation

This system ensures transparent, auditable, and structured revenue collection.

---

## 💰 1. Revenue Sources

ServiPro operates a dual-revenue model:

### A) Subscription Revenue

- Monthly contractor membership fee
- Fixed pricing per plan
- Recurring billing cycle

### B) Commission Revenue

- Percentage of awarded contract value
- Triggered after successful tender award
- One-time per contract + renewals

---

## 🧾 2. Invoice Generation Triggers

Invoices are automatically generated when:

### Subscription Invoice:

- Contractor subscription is created
- Monthly billing cycle resets

### Commission Invoice:

- Contract is created (post tender award)
- Commission amount is calculated

---

## 📦 3. Invoice Structure

Each invoice contains:

- Unique invoice number
- Related entity (Subscription / Contract)
- Amount (Decimal precision)
- Due date
- Status tracking
- Optional PDF document
- Payment metadata

---

## 🔄 4. Invoice Lifecycle

### Status Flow:

**PENDING → PAID → FAILED**

### Behavior:

#### PENDING

- Invoice generated but not paid
- Visible in contractor dashboard

#### PAID

- Payment successfully confirmed
- Subscription or commission marked as settled

#### FAILED

- Payment attempt unsuccessful
- Retry mechanisms may be triggered

---

## 💳 5. Payment Processing Layer

ServiPro integrates external payment systems (e.g. Stripe).

### Responsibilities:

- Payment collection
- Subscription management
- Webhook handling
- Payment confirmation syncing

### System Principle:

ServiPro does NOT hold funds between parties — it only tracks invoices and payment states.

---

## 📊 6. Subscription Billing Flow

### Monthly Cycle:

1. Subscription active
2. Billing date reached
3. Invoice generated
4. Payment attempted
5. Status updated

### Failure Handling:

- Retry logic (external system)
- Account status may be flagged

---

## 🏗️ 7. Commission Billing Flow

### Trigger:

- Contract created after tender award

### Steps:

1. Commission calculated
2. Invoice generated (`CommissionInvoice`)
3. Contractor notified
4. Payment tracked

---

## 🔔 8. Notification Integration

Invoices trigger system notifications:

- New invoice issued
- Payment due reminders
- Payment successful confirmation
- Failed payment alerts

---

## 📁 9. Document Management

Invoices may include:

- PDF exports
- Hosted invoice links
- Payment instructions

Stored securely and accessed via signed URLs.

---

## 🧾 10. Audit Tracking

Every invoice action is logged:

- Creation
- Payment attempt
- Status changes

Ensures:

- Financial traceability
- Compliance reporting
- Dispute resolution support

---

## 🧠 System Insight

The invoice system ensures:

- Predictable SaaS revenue (subscriptions)
- Performance-based revenue (commissions)
- Fully auditable financial flow

---

## ⚙️ Key Design Principle

> “Every financial event must be traceable, verifiable, and tied to a real system action.”
>
