<p align="center">
  <img src="https://www.nustforge.com/api/og?title=ServiPro%20Case%20Study&description=Enterprise%20B2B%20Procurement%20SaaS%20Platform&tag=NUSTFORGE%20Case%20Study&v=servipro-case-study" alt="ServiPro — Enterprise B2B Procurement SaaS Case Study" width="100%" />
</p>

# ServiPro — Enterprise B2B Procurement SaaS Case Study

<p align="center">
  <strong>B2B procurement, tender management, contractor onboarding, bid evaluation, contract tracking, billing, verification, and compliance workflows for UK property management operations.</strong>
</p>

<p align="center">
  Built under <a href="https://www.nustforge.com" target="_blank" rel="noreferrer"><strong>NUSTFORGE</strong></a>
</p>

<p align="center">
  <a href="https://www.servipro.co.uk/" target="_blank" rel="noreferrer"><strong>Visit Live Platform</strong></a>
  ·
  <a href="https://www.nustforge.com/work" target="_blank" rel="noreferrer"><strong>View NUSTFORGE Work</strong></a>
  ·
  <a href="https://github.com/nustforge" target="_blank" rel="noreferrer"><strong>GitHub Organization</strong></a>
</p>

---

## Overview

ServiPro is an enterprise B2B procurement and contractor management platform built for UK property managers, managing agents, and contractor networks.

The platform centralizes the full procurement lifecycle, from building and tender creation to contractor invitations, structured bid submission, contract awarding, compliance visibility, subscription billing, commission invoices, document handling, and audit history.

ServiPro is designed for recurring service contracts and long-term property management workflows, not one-off job posting.

---

## The Business Problem

Property management procurement is often handled through fragmented manual workflows, spreadsheets, emails, disconnected contractor lists, and weak visibility across tender and contract history.

Common operational problems include:

* Fragmented contractor sourcing
* Manual tender creation and tracking
* Limited transparency during bid comparison
* Weak audit trails for compliance-sensitive decisions
* Difficult contractor verification
* Scattered compliance documents
* Limited visibility into awarded contract history
* Risk of off-platform contractor bypassing
* Manual subscription, invoice, and commission administration

ServiPro solves this by turning procurement into a structured digital workflow with role-based access, verified contractor data, controlled tender activity, compliance visibility, and traceable platform actions.

---

## Platform Users

ServiPro is built around three main user roles.

| User Role      | Purpose                                                                                                  |
| -------------- | -------------------------------------------------------------------------------------------------------- |
| Managing Agent | Creates tenders, invites contractors, compares bids, awards contracts, and tracks procurement activity   |
| Contractor     | Views opportunities, submits bids, manages company data, uploads documents, and tracks awarded work      |
| Admin          | Manages users, approvals, verification, subscriptions, invoices, platform activity, and audit visibility |

---

## Core Platform Modules

### Managing Agent Dashboard

Managing agents can manage procurement workflows from tender creation to contract tracking.

* Create and publish tenders
* Manage buildings and service requirements
* Invite verified contractors
* Compare structured bids
* Award contracts
* Track contract status and renewal history
* Review contractor profile and compliance information
* Monitor tender, bid, and contract activity

### Contractor Dashboard

Contractors can access relevant opportunities, submit bids, and maintain business profile information.

* View tender opportunities
* Submit structured bids
* Upload compliance documents
* Maintain company and verification data
* Track submitted bids and awarded contracts
* Manage subscription and invoice records
* Maintain business and compliance information

### Admin Dashboard

Admins can control platform operations, verification, billing, and system visibility.

* Manage managing agents and contractors
* Approve or reject user accounts
* Monitor platform activity
* Manage subscription and billing workflows
* Track commission invoices
* Review verification and compliance information
* Maintain audit visibility across important actions

---

## Procurement Workflow

The platform supports a complete tender-to-contract workflow.

1. Managing agent creates a building and tender
2. Tender is published or shared with selected contractors
3. Contractors review the opportunity
4. Contractors submit structured bids
5. Managing agent evaluates and compares bids
6. Winning contractor is selected
7. Contract is awarded
8. Commission invoice is generated
9. Contract is tracked until renewal, completion, or expiry
10. Audit history is retained for operational visibility

---

## Verification & Compliance Workflow

ServiPro includes verification and compliance-focused workflows to support trusted B2B procurement.

1. Contractor submits company and profile information
2. Company information can be checked against UK business registry data
3. Business intelligence checks can support contractor trust signals
4. Compliance documents are uploaded and reviewed
5. Admin approves or rejects contractor access
6. Verification and compliance activity remains available for audit visibility

---

## Revenue Model

ServiPro uses a hybrid contractor-funded SaaS model.

* Managing agents use the platform free of charge
* Contractors pay for platform access through subscription
* Commission is applied on awarded contracts
* Revenue is aligned with contractor opportunity access and successful contract outcomes

---

## Tech Stack

| Area                     | Technologies                                                                       |
| ------------------------ | ---------------------------------------------------------------------------------- |
| Frontend                 | Next.js, React, TypeScript, Tailwind CSS                                           |
| Backend                  | Node.js, Prisma ORM, PostgreSQL                                                    |
| Authentication & Access  | JWT, role-based access control                                                     |
| File Storage             | AWS S3, signed document access workflows                                           |
| Payments & Billing       | Stripe subscriptions, billing, and invoices                                        |
| Email Workflows          | SendGrid transactional email                                                       |
| Realtime / Notifications | Pusher                                                                             |
| Deployment               | Vercel, production hosting workflows                                               |
| Business Verification    | Companies House / UK business registry workflows, Creditsafe integration direction |

---

## Security, Trust & Compliance Principles

ServiPro is designed for controlled procurement workflows where user roles, contractor legitimacy, document handling, and audit history matter.

Key principles include:

* Strict role-based access control
* Separate workflows for Admin, Managing Agent, and Contractor users
* Secure document storage and controlled file access
* Audit logging for important business actions
* Verification-first contractor onboarding
* Compliance-first procurement model
* Structured tender, bid, and contract history
* No exposure of private credentials, secrets, or sensitive production data in public documentation
* Long-term maintainability through structured database and workflow design

---

## Architecture Focus

ServiPro is structured as a multi-role SaaS platform with separated dashboards, relational data modeling, and workflow-driven backend logic.

Core architecture areas include:

* Multi-role dashboard architecture
* Tender, bid, contract, invoice, subscription, user, document, and audit log modeling
* Building-level procurement workflows
* Contractor invitation and bid submission workflows
* Secure document upload and signed-access flows
* Stripe billing and subscription lifecycle handling
* Contractor verification and company data workflows
* Audit log design for business-critical actions
* API-first workflow implementation
* Scalable backend structure for future feature expansion

---

## Repository Purpose

This repository is maintained as a public case study for the ServiPro platform.

It may include:

* Product overview
* Architecture notes
* Workflow documentation
* Database planning
* Business model breakdowns
* Compliance notes
* Screenshots
* System design references

This repository does not expose private credentials, production secrets, customer data, internal API keys, or sensitive operational records.

---

## Project Status

ServiPro is a production-grade SaaS platform under active development and deployment.

The public repository documents the platform as a case study covering product direction, business workflow planning, architecture decisions, verification workflows, compliance direction, and engineering structure.

---

## Built By NUSTFORGE

ServiPro was built under **NUSTFORGE**, a software engineering studio focused on premium websites, platforms, dashboards, automation systems, and custom SaaS products for modern businesses.

<p align="center">
  <a href="https://www.servipro.co.uk/" target="_blank" rel="noreferrer"><strong>Visit ServiPro</strong></a>
  ·
  <a href="https://www.nustforge.com" target="_blank" rel="noreferrer"><strong>Visit NUSTFORGE</strong></a>
  ·
  <a href="mailto:hello@nustforge.com"><strong>Discuss a Project</strong></a>
</p>
