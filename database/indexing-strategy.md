# Database Indexing Strategy – ServiPro

This document explains the indexing strategy used in ServiPro to ensure high-performance queries at scale.

---

## 1. User Table Indexing

### Indexed Fields

- email (unique lookup)
- role (filter dashboards)
- status (approval flow)
- displayId (public reference)

### Purpose

Fast authentication, role-based access, and user filtering.

---

## 2. Tender System Indexing

### Indexed Fields

- managingAgentId
- status
- deadline

### Purpose

- Fast dashboard loading
- Filtering active vs closed tenders
- Time-sensitive queries for expiry handling

---

## 3. Bid System Indexing

### Indexed Fields

- contractorId
- tenderId

### Purpose

- Quick bid retrieval per contractor
- Efficient tender comparison views

---

## 4. Contract Indexing

### Indexed Fields

- contractorId
- managingAgentId
- status

### Purpose

- Contract lifecycle tracking
- Dashboard performance optimization
- Renewal queries

---

## 5. Notification System Indexing

### Indexed Fields

- userId
- role

### Purpose

- Real-time notification delivery
- Role-based system alerts

---

## 6. Audit Log Indexing

### Indexed Fields

- entityType
- entityId
- performedBy

### Purpose

- Fast audit trail reconstruction
- Compliance reporting

---

## Summary

Indexes are designed around **dashboard speed, auditability, and high-frequency queries** across the platform.
