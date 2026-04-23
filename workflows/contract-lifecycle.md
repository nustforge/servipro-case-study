# Contract Lifecycle – ServiPro

## 🧠 Overview

The Contract Lifecycle is the final and most critical stage of the ServiPro procurement system.

It defines how awarded tenders are converted into legally binding service contracts, how revenue is generated, and how ongoing performance is tracked.

---

## 🏆 1. Contract Creation Trigger

A contract is automatically created when:

- A bid is marked as `ACCEPTED`
- The tender status becomes `AWARDED`

### System Action:

- Contract entity is generated
- Linked to:
  - Tender
  - Contractor
  - Managing Agent

---

## 📄 2. Contract Initialization

Each contract stores:

- Annual contract value
- Start & end dates
- Commission rate
- Commission amount (calculated)
- Status = `ACTIVE`

### Formula:

Commission is calculated as:

- commissionAmount = annualValue × commissionRate

---

## 🔁 3. Active Contract Phase

During active execution:

### System Tracks:

- Contract status
- Renewal date
- Performance ratings
- Compliance updates
- Audit logs

### Business Reality:

This is the revenue-generating phase for contractors and the platform.

---

## 💳 4. Commission Lifecycle

Once contract is active:

### ServiPro Revenue Model:

- Commission is locked at creation
- Invoice is generated via `CommissionInvoice`
- Payment is tracked independently

### Invoice States:

- PENDING
- PAID
- FAILED

---

## 📊 5. Performance Tracking

During contract duration:

System collects:

- Contractor ratings
- Agent feedback
- Compliance updates
- Document changes

This data is used for:

- Contractor reputation scoring
- Future tender eligibility
- Risk assessment

---

## 🔔 6. Renewal Process

Before contract end:

System triggers renewal evaluation.

### Options:

#### ✅ Renew

- Contract status → `RENEWED`
- New contract cycle begins
- New commission applied

#### ❌ End Contract

- Status → `COMPLETED`
- No further obligations

#### ⚠️ Early Termination

- Status → `TERMINATED`
- Logged in audit system

---

## 📦 7. Contract Closure

When contract ends:

System ensures:

- Final audit log entry
- Performance summary stored
- Invoice finalization
- Data archived (read-only state)

---

## 🧾 8. Audit & Legal Traceability

Every contract has full lifecycle tracking:

- Award origin (Tender → Bid)
- Financial breakdown
- Decision history
- Amendment logs

This ensures legal defensibility in disputes.

---

## 🧠 9. System Design Insight

The contract system is the **financial backbone** of ServiPro:

- Tender = opportunity
- Bid = proposal
- Contract = revenue engine

---

## ⚙️ Key Design Principle

> “Every contract must be traceable back to a verifiable procurement decision chain.”

---

## 🔐 Compliance Note

Contracts are designed to meet UK property procurement expectations:

- Transparent award process
- Documented decision history
- Audit-ready financial tracking
