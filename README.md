# ServiPro — Enterprise B2B Procurement SaaS Case Study

<p align="center">
  <strong>B2B procurement, tender management, contractor onboarding, contract tracking, billing, verification, and compliance workflows for UK property management operations.</strong>
</p>

<p align="center">
  Built under <a href="https://www.nustforge.com"><strong>NUSTFORGE</strong></a> ·
  <a href="https://github.com/nustforge">GitHub Organization</a>
</p>

---

## 🏢 Overview

ServiPro is an enterprise B2B procurement and tender management platform designed for UK property managers, managing agents, and contractor networks.

The platform digitizes the full lifecycle of building service procurement, including tender creation, contractor invitations, structured bid submission, bid comparison, contract awarding, compliance tracking, contractor verification, commission billing, subscription management, invoices, and audit history.

ServiPro is designed for long-term contract management and recurring business workflows — not one-off job posting.

---

## 🎯 Problem Statement

Property management companies often manage procurement through fragmented manual processes, spreadsheets, email chains, and disconnected contractor lists.

Common operational problems include:

- Fragmented contractor sourcing
- Limited transparency during bid comparison
- Manual tender and contract tracking
- Weak audit trails for compliance
- Difficult contractor verification
- Limited visibility into awarded contract history
- Risk of contractor bypassing and off-platform deals
- Manual invoice and subscription administration
- Scattered compliance documents and renewal records

ServiPro solves this by centralizing procurement into a controlled digital ecosystem with role-based workflows, structured data, verification checks, compliance visibility, and traceable business activity.

---

## 🧩 Core Platform Modules

### 1. Managing Agent System

Managing agents can manage procurement workflows from tender creation to contract tracking.

- Create and publish tenders
- Invite verified contractors
- Compare structured bids
- Award contracts
- Track contract lifecycle and renewals
- Maintain operational audit logs
- Monitor tender history and contractor activity
- Review compliance and contractor profile information

### 2. Contractor System

Contractors can access business opportunities, submit bids, and maintain compliance records.

- Access tender opportunities
- Submit structured bids
- Upload compliance documents
- Manage company profile and verification data
- Track awarded contracts
- Manage subscription and invoice records
- Maintain business and compliance information

### 3. Admin System

Platform administrators can manage users, platform activity, revenue workflows, verification, and compliance oversight.

- Manage managing agents and contractors
- Approve or reject accounts
- Monitor subscriptions and invoices
- Track commission billing
- Review system analytics
- Maintain audit visibility across platform actions
- Oversee company verification and compliance workflows

---

## 🔄 Business Workflow

### Tender Lifecycle

1. Managing agent creates a tender
2. Contractors are invited or matched
3. Contractors submit structured bids
4. Managing agent evaluates and compares bids
5. Contract is awarded
6. Commission invoice is generated
7. Contract is tracked until expiry or renewal
8. Audit history is retained for operational visibility

### Verification & Compliance Flow

1. Contractor submits company and profile information
2. Company information is checked against UK business registry data
3. Creditsafe business intelligence checks support contractor trust signals
4. Compliance documents are uploaded and reviewed
5. Admin approves or rejects contractor access
6. Verification and compliance activity is retained for audit visibility

### Platform Flow

Managing Agent → Tender → Contractor Invitation → Bid Submission → Evaluation → Contract Award → Billing → Audit Trail

---

## 💰 Revenue Model

ServiPro uses a hybrid contractor-funded SaaS model.

- Monthly contractor subscription for platform access
- Commission on awarded contracts
- Managing agents use the platform free of charge

This model aligns platform revenue with contractor opportunity access and successful contract outcomes.

---

## 🛠 Tech Stack

- Next.js
- TypeScript
- PostgreSQL
- Prisma ORM
- AWS S3 for document storage
- Stripe for subscriptions, billing, and invoices
- SendGrid for transactional email workflows
- Companies House / UK business registry data workflows
- Creditsafe API integration for business verification and contractor trust checks

---

## 🔐 Verification, Trust & Compliance

ServiPro is designed for trusted B2B procurement workflows where contractor legitimacy, compliance documents, and audit history matter.

Key verification and compliance areas include:

- UK LTD contractor verification
- Company lookup and validation using UK business registry data
- Creditsafe business intelligence checks for contractor trust signals
- Compliance document upload and review workflows
- Role-based access control across Admin, Managing Agent, and Contractor users
- Full audit trail for important platform actions
- Secure document handling through cloud storage
- No direct handling of client-side property payments
- Commission protection through non-circumvention rules
- Compliance-first procurement workflow design
- Structured data model for long-term maintainability

---

## 🔐 Security, Compliance & Platform Principles

ServiPro is designed around controlled access, verification, and traceable operational workflows.

Key principles include:

- Strict role-based access control
- Clear separation between Admin, Managing Agent, and Contractor workflows
- Secure document storage and controlled file access
- Audit logging for important business actions
- Verification-first contractor onboarding
- Compliance-first procurement model
- No exposure of private credentials or sensitive operational data in public documentation
- Long-term maintainability through structured database and workflow design

---

## 🏗 Architecture Focus

The platform is designed as a multi-role SaaS system with separated operational flows for each user type.

Core architectural areas include:

- Multi-role dashboard architecture
- Relational database modeling for tenders, bids, contracts, invoices, subscriptions, users, compliance documents, and audit logs
- Document upload and signed-access workflows
- Stripe billing and subscription lifecycle handling
- Contractor verification and company data workflows
- Audit log design for business-critical actions
- API-first workflow implementation
- Scalable backend structure for future feature expansion

---

## 📂 Repository Contents

This repository documents the ServiPro platform as a public case study.

It may include:

- Architecture notes
- Workflow documentation
- Database planning
- Business model breakdowns
- Compliance notes
- Screenshots
- System design references

This repository does not expose private credentials, production secrets, customer data, internal API keys, or sensitive operational records.

---

## 📌 Status

ServiPro is a production-grade system under active development and deployment.

The public repository is maintained as a case study to document system design, business workflow planning, architecture decisions, verification workflows, compliance direction, and engineering structure.

---

## 🏢 Built By

Built under **NUSTFORGE** — an enterprise SaaS and systems engineering studio focused on production-grade business software.

Website: https://www.nustforge.com  
GitHub: https://github.com/nustforge
