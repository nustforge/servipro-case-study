# Tender Lifecycle – ServiPro

## 🧠 Overview

The Tender Lifecycle is the core operational flow of ServiPro. It defines how managing agents create structured procurement opportunities and how contractors participate through a controlled bidding system.

This workflow ensures transparency, compliance, and traceability across all procurement activity.

---

## 🏗️ 1. Tender Creation (Draft Stage)

A Managing Agent initiates a tender.

### Inputs:

- Title
- Description
- Service category
- Building reference
- Contract duration
- Compliance requirements

### System Action:

- Tender is stored with status: `DRAFT`
- No contractors can access it yet
- Audit log entry is created

---

## 📢 2. Tender Publication

Once ready, the managing agent publishes the tender.

### System Actions:

- Status changes: `DRAFT → PUBLISHED`
- Contractors become eligible for invitations
- Notifications are triggered
- Optional contractor selection for invitation list

---

## 📩 3. Contractor Invitation Phase

Managing agent can:

- Invite selected contractors
- Or allow open access (depending on configuration)

### Invitation States:

- INVITED
- VIEWED
- DECLINED
- BID_SUBMITTED

Each invitation is tracked individually.

---

## 📊 4. Bid Submission Phase

Contractors submit structured bids.

### Bid Includes:

- Financial offer (annual value)
- Proposal text
- Supporting documents (insurance, certifications)
- Optional notes

### System Rules:

- One bid per contractor per tender
- All bids are timestamped and immutable after submission

---

## 🔍 5. Evaluation Phase (Under Review)

Managing agent reviews submitted bids.

### System State:

- Tender status: `UNDER_REVIEW`

### Actions:

- Compare bids
- Review compliance documents
- Evaluate pricing vs service quality
- Audit all decision activity

---

## 🏆 6. Award Phase

A winning contractor is selected.

### System Actions:

- Tender status: `AWARDED`
- Contract is automatically generated
- Winning bid is linked to contract
- All other bids marked as rejected (implicit or explicit)

---

## 📜 7. Contract Generation

A contract is created immediately after award.

### Contract Includes:

- Contractor ID
- Managing Agent ID
- Annual value
- Commission rate
- Start & end dates

This becomes the legally binding operational record.

---

## 💳 8. Commission Activation

Once contract is active:

- Commission is calculated
- `commissionAmount = annualValue × commissionRate`
- Commission invoice is generated

ServiPro revenue is triggered at this stage.

---

## 🔄 9. Ongoing Lifecycle Tracking

During contract duration:

- Contract remains `ACTIVE`
- Renewal dates tracked
- Performance data can be added
- Ratings may be submitted

---

## 🔁 10. Renewal Flow

At contract end:

### Options:

- Renew contract → `RENEWED`
- Close contract → `COMPLETED`
- Terminate early → `TERMINATED`

Renewals trigger:

- New commission cycle
- New invoice generation

---

## 🧾 11. Audit & Compliance Tracking

Every stage generates audit logs:

- Tender creation
- Bid submissions
- Evaluation decisions
- Contract awards

This ensures:

- Full regulatory traceability
- Dispute resolution support
- Internal governance compliance

---

## 🧠 System Design Insight

This workflow ensures:

- Controlled procurement lifecycle
- No uncontrolled contractor access
- Transparent decision-making
- Revenue only upon successful outcomes
- Fully auditable decision chain

---

## ⚙️ Key Design Principle

> “No contract exists without traceable tender history and audited decision flow.”
>
