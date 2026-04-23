# ServiPro – Data Flow Architecture

## 🔄 Overview

This document explains how data moves through the ServiPro platform from **user action → backend processing → database → system response**.

The system is built around a structured lifecycle:

> Tender → Invitation → Bid → Evaluation → Contract → Invoice

---

## 🧩 1. User Authentication Flow

### Flow:

1. User logs in (email + password)
2. JWT token is generated
3. Role is attached (ADMIN / MANAGING_AGENT / CONTRACTOR)
4. Frontend routes user to correct dashboard

### Data involved:

- `User`
- `ManagingAgentProfile`
- `ContractorProfile`

---

## 🏗 2. Tender Creation Flow (Managing Agent)

### Flow:

1. Agent creates a tender
2. System validates building + category
3. Tender saved as `DRAFT`
4. Once published → status changes to `PUBLISHED`
5. Contractors are invited

### Data flow:

- `Tender`
- `Building`
- `TenderInvitation`

---

## 📩 3. Contractor Invitation Flow

### Flow:

1. System selects eligible contractors
2. Invitations created per contractor
3. Contractors receive notification
4. Status tracked: INVITED → VIEWED → BID_SUBMITTED

### Data flow:

- `TenderInvitation`
- `Notification`

---

## 📊 4. Bid Submission Flow

### Flow:

1. Contractor opens tender
2. Submits bid amount + proposal
3. Uploads compliance documents
4. Bid is locked after submission

### Data flow:

- `Bid`
- `BidComplianceDocument`

### Constraints:

- One bid per contractor per tender (unique constraint enforced)

---

## ⚖️ 5. Evaluation & Award Flow

### Flow:

1. Managing agent reviews bids
2. Compares pricing + compliance
3. Selects winning bid
4. System generates contract automatically

### Data flow:

- `Bid.status`
- `Tender.status → AWARDED`
- `Contract`

---

## 📄 6. Contract Lifecycle Flow

### Flow:

1. Contract is created from winning bid
2. Commission is calculated
3. Start & end dates are set
4. Renewal date is tracked

### Data flow:

- `Contract`
- `CommissionInvoice`

---

## 💰 7. Invoice & Payment Flow

### Flow:

1. System generates commission invoice
2. Invoice sent to contractor
3. Payment tracked externally (Stripe optional)
4. Status updated: PENDING → PAID → FAILED

### Data flow:

- `Invoice`
- `CommissionInvoice`
- `ContractorSubscription`

---

## 🔔 8. Notification Flow

### Flow:

1. System triggers event (bid, tender, contract)
2. Notification created
3. Stored in DB
4. Read/unread tracked per user

### Data flow:

- `Notification`
- `NotificationRead`

---

## 📂 9. File Upload Flow (AWS S3)

### Flow:

1. User uploads document
2. File sent to backend
3. Stored in AWS S3 bucket
4. Signed URL generated for access

### Data flow:

- `ContractorDocument`
- `BidComplianceDocument`
- `Tender.documentUrl`

---

## 📊 10. Audit Logging Flow

### Flow:

1. Any critical action triggers audit event
2. System logs:
   - entity type
   - entity ID
   - action
   - user
3. Stored permanently (immutable record)

### Data flow:

- `AuditLog`

---

## 🧠 Key Design Principle

> Every important action in ServiPro is traceable, auditable, and reversible only via system logic — never manually edited.

This ensures:

- Transparency
- Compliance
- Trust between agents and contractors

---

## 🔚 Summary

ServiPro data flow is designed around:

- Strong relational consistency (PostgreSQL)
- Event-driven business logic
- Fully traceable procurement lifecycle
- Role-separated access control
