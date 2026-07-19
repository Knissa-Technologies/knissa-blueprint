# 🌐 API Specification

> **Knissa REST API v1.0**

---

# Overview

The Knissa API follows REST principles and provides secure access to all platform resources.

All responses are returned in JSON format.

Base URL:

```
/api/v1
```

---

# Authentication

Authentication uses JWT Bearer Tokens.

Example:

```
Authorization: Bearer <token>
```

---

# Authentication Endpoints

## Register

POST /auth/register

Creates a new account.

---

## Login

POST /auth/login

Returns:

- Access Token
- Refresh Token

---

## Refresh Token

POST /auth/refresh

Generates a new Access Token.

---

## Logout

POST /auth/logout

Invalidates the current session.

---

# User Endpoints

GET /users/me

Returns the authenticated user's profile.

---

PUT /users/me

Updates profile information.

---

# Wallet Endpoints

GET /wallet

Returns wallet information.

---

GET /wallet/balance

Returns current balance.

---

# Transaction Endpoints

POST /transactions

Creates a money transfer.

---

GET /transactions

Returns transaction history.

---

GET /transactions/{id}

Returns transaction details.

---

# Notification Endpoints

GET /notifications

Returns all notifications.

---

PUT /notifications/{id}/read

Marks notification as read.

---

# HTTP Status Codes

- 200 OK
- 201 Created
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 409 Conflict
- 500 Internal Server Error

---

# Response Format

Success

```json
{
  "success": true,
  "data": {}
}
```

Error

```json
{
  "success": false,
  "message": "Error description"
}
```

---

# API Versioning

Current Version:

```
/api/v1
```

Future versions:

```
/api/v2
```

---

# Security

- HTTPS only
- JWT Authentication
- Refresh Tokens
- Rate Limiting
- Input Validation
- Request Logging
