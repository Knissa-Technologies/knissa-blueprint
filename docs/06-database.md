# 🗄️ Database Design

> **Knissa Database Design v1.0**

---

# Overview

The Knissa database is designed to support a secure, scalable and maintainable financial platform.

The first version focuses on the core entities required for the MVP.

---

# Database Technology

Database Engine:

- MySQL 8

ORM:

- Prisma ORM

---

# Main Entities

## Users

Stores user information.

Fields:

- id
- firstName
- lastName
- email
- passwordHash
- phone
- status
- createdAt
- updatedAt

---

## Wallets

Each user owns one wallet.

Fields:

- id
- userId
- balance
- currency
- status
- createdAt

Relationship:

User (1) → (1) Wallet

---

## Transactions

Stores all financial operations.

Fields:

- id
- senderWalletId
- receiverWalletId
- amount
- currency
- status
- description
- createdAt

Relationship:

Wallet (1) → (N) Transactions

---

## Notifications

Stores user notifications.

Fields:

- id
- userId
- title
- message
- read
- createdAt

---

## Roles

Defines user permissions.

Examples:

- USER
- ADMIN
- SUPPORT

---

## Sessions

Stores active login sessions.

Fields:

- id
- userId
- refreshToken
- expiresAt
- device
- ipAddress

---

# Entity Relationships

Users
│
└── Wallet
      │
      ├── Transactions
      │
      └── Notifications

Users
└── Sessions

Users
└── Roles

---

# Database Principles

- Normalized structure
- Referential integrity
- Soft deletes when appropriate
- Audit fields
- UUID primary keys

---

# Future Tables

- Merchant
- Payment Links
- QR Codes
- Exchange Rates
- Cards
- Bank Accounts
- Audit Logs
