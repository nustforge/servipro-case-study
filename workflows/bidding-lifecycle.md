# Bidding Lifecycle – ServiPro

## 🧠 Overview

The Bidding Lifecycle defines how contractors engage with published tenders, submit structured proposals, and compete in a controlled procurement environment.

This system ensures fairness, compliance, and full traceability of all contractor submissions.

---

## 🔓 1. Bid Access Activation

Contractors gain access to bidding opportunities only when:

- Tender is in `PUBLISHED` state
- Contractor is:
  - Invited OR
  - Eligible under platform rules

System enforces:

- Role-based access control (CONTRACTOR only)
- Invitation validation via `TenderInvitation`

---

## 📄 2. Bid Creation

A contractor creates a bid against a specific tender.

### Bid Inputs:

- Proposed annual contract value
- Technical proposal description
- Optional supporting documentation

### System Rules:

- One bid per contractor per tender
- Duplicate prevention enforced at database level
- Bid stored with status: `PENDING`

---

## 📎 3. Compliance Document Attachment

Contractors upload compliance evidence:

- Insurance certificates
- Company registration proof
- Certifications (ISO, safety, etc.)

### Storage:

- Files uploaded via AWS S3
- Metadata stored in `BidComplianceDocument`

---

## ⏱️ 4. Submission Lock

Once submitted:

- Bid becomes immutable (except admin overrides)
- Timestamp recorded
- Audit log generated

This ensures:

- No post-submission manipulation
- Legal-grade audit integrity

---

## 🔍 5. Evaluation Window

Managing agents review all bids.

### Key Evaluation Factors:

- Pricing competitiveness
- Compliance completeness
- Contractor history
- Risk profile (via health checks)

System supports:

- Side-by-side bid comparison
- Document verification
- Audit trail per decision

---

## 🧠 6. Bid Scoring (Implicit System Logic)

Although not explicitly stored, evaluation is based on:

- Price (weight-based consideration)
- Compliance completeness
- Contractor reliability score
- Past contract performance (ratings)

---

## 🏆 7. Bid Outcome Decision

Each bid transitions into one of:

- ACCEPTED
- REJECTED
- WITHDRAWN

### System Effects:

- Accepted bid triggers contract creation
- Rejected bids remain archived for audit
- All decisions logged in `AuditLog`

---

## 🔗 8. Contract Trigger (Downstream Effect)

If bid is accepted:

- Contract is automatically generated
- Tender status transitions to `AWARDED`
- Commission calculation is triggered

---

## 📊 9. Post-Bid Analytics

System tracks:

- Bid frequency per contractor
- Win/loss ratio
- Average pricing trends
- Category performance

This enables:

- Contractor performance scoring
- Agent decision insights
- Platform-level analytics

---

## 🧾 10. Audit Integrity Layer

Every bid action is logged:

- Creation
- Submission
- Review
- Decision outcome

Ensures:

- Regulatory compliance
- Dispute resolution capability
- Full procurement transparency

---

## 🧠 Design Principle

> “Every bid is a legally traceable financial proposal, not just a form submission.”

---

## ⚙️ Key System Constraint

- No hidden bids
- No post-submission edits
- No contractor visibility into competitor bids
- Full agent-controlled evaluation flow
