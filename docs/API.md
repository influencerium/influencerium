# Influencerium API Documentation

**Complete API Reference for Influencerium Platform**

---

## 📋 Table of Contents

1. [Base URL](#base-url)
2. [Authentication](#authentication)
3. [Response Format](#response-format)
4. [Core Endpoints](#core-endpoints)
5. [Error Handling](#error-handling)
6. [Rate Limiting](#rate-limiting)

---

## 🌐 Base URL

```
Development: http://localhost:3000/api/v1
Production: https://api.influencerium.com/api/v1
```

---

## 🔐 Authentication

All API requests require a Bearer token in the Authorization header:

```
Authorization: Bearer <jwt_token>
```

### Get Token

**POST** `/auth/login`

```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIs...",
    "refreshToken": "eyJhbGciOiJIUzI1NiIs...",
    "user": {
      "id": "uuid",
      "email": "user@example.com",
      "userType": "creator"
    }
  }
}
```

---

## 📤 Response Format

### Success Response

```json
{
  "success": true,
  "data": { /* response data */ },
  "message": "Operation successful"
}
```

### Error Response

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Error description",
    "details": { /* additional details */ }
  }
}
```

---

## 🔌 Core Endpoints

### Authentication Endpoints

#### Register User
**POST** `/auth/register`

```json
{
  "email": "user@example.com",
  "password": "password123",
  "firstName": "John",
  "lastName": "Doe",
  "userType": "creator"
}
```

#### Login
**POST** `/auth/login`

#### Logout
**POST** `/auth/logout`

#### Refresh Token
**POST** `/auth/refresh-token`

#### Forgot Password
**POST** `/auth/forgot-password`

```json
{
  "email": "user@example.com"
}
```

#### Reset Password
**POST** `/auth/reset-password`

```json
{
  "token": "reset_token",
  "newPassword": "newpassword123"
}
```

#### OAuth Callbacks
- **GET** `/auth/oauth/google/callback`
- **GET** `/auth/oauth/instagram/callback`
- **GET** `/auth/oauth/tiktok/callback`
- **GET** `/auth/oauth/linkedin/callback`

---

### User Endpoints

#### Get Current User Profile
**GET** `/users/profile`

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "uuid",
    "email": "user@example.com",
    "firstName": "John",
    "lastName": "Doe",
    "avatar": "https://...",
    "bio": "User bio",
    "userType": "creator"
  }
}
```

#### Update User Profile
**PUT** `/users/profile`

```json
{
  "firstName": "John",
  "lastName": "Doe",
  "bio": "Updated bio",
  "avatar": "image_url"
}
```

#### Get User by ID
**GET** `/users/:id`

#### Delete Account
**DELETE** `/users/account`

---

### Creator Endpoints

#### Get All Creators
**GET** `/creators`

**Query Parameters:**
- `page` - Page number (default: 1)
- `limit` - Items per page (default: 20)
- `niche` - Filter by niche
- `minFollowers` - Minimum followers
- `maxFollowers` - Maximum followers

#### Get Creator Profile
**GET** `/creators/:id`

#### Update Creator Profile
**PUT** `/creators/:id`

```json
{
  "bio": "Creator bio",
  "niche": "Technology",
  "website": "https://example.com"
}
```

#### Get Creator's Campaigns
**GET** `/creators/:id/campaigns`

#### Get Creator's Earnings
**GET** `/creators/:id/earnings`

#### Get Creator's Portfolio
**GET** `/creators/:id/portfolio`

---

### Brand Endpoints

#### Get All Brands
**GET** `/brands`

#### Get Brand Profile
**GET** `/brands/:id`

#### Update Brand Profile
**PUT** `/brands/:id`

```json
{
  "companyName": "Company Name",
  "industry": "Technology",
  "website": "https://example.com"
}
```

#### Get Brand's Campaigns
**GET** `/brands/:id/campaigns`

#### Get Brand Analytics
**GET** `/brands/:id/analytics`

---

### Campaign Endpoints

#### Get All Campaigns
**GET** `/campaigns`

**Query Parameters:**
- `page` - Page number
- `limit` - Items per page
- `category` - Filter by category
- `minBudget` - Minimum budget
- `maxBudget` - Maximum budget
- `status` - Filter by status

#### Create Campaign
**POST** `/campaigns`

```json
{
  "title": "Campaign Title",
  "description": "Campaign description",
  "category": "Technology",
  "budget": 5000,
  "startDate": "2026-01-15",
  "endDate": "2026-02-15",
  "targetAudience": {
    "ageMin": 18,
    "ageMax": 35,
    "gender": "all",
    "location": "USA"
  }
}
```

#### Get Campaign Details
**GET** `/campaigns/:id`

#### Update Campaign
**PUT** `/campaigns/:id`

#### Delete Campaign
**DELETE** `/campaigns/:id`

#### Get Campaign Applications
**GET** `/campaigns/:id/applications`

#### Apply to Campaign
**POST** `/campaigns/:id/apply`

```json
{
  "coverLetter": "Why I'm interested...",
  "proposedRate": 1000
}
```

---

### Application Endpoints

#### Get User's Applications
**GET** `/applications`

#### Get Application Details
**GET** `/applications/:id`

#### Update Application Status
**PUT** `/applications/:id/status`

```json
{
  "status": "approved"
}
```

#### Approve Application
**POST** `/applications/:id/approve`

#### Reject Application
**POST** `/applications/:id/reject`

```json
{
  "reason": "Rejection reason"
}
```

---

### Messaging Endpoints

#### Get Conversations
**GET** `/messages`

#### Get Conversation Messages
**GET** `/messages/:conversationId`

#### Send Message
**POST** `/messages`

```json
{
  "recipientId": "uuid",
  "content": "Message content",
  "campaignId": "uuid" (optional)
}
```

#### Edit Message
**PUT** `/messages/:id`

```json
{
  "content": "Updated content"
}
```

#### Delete Message
**DELETE** `/messages/:id`

---

### Payment Endpoints

#### Get Earnings Summary
**GET** `/payments/earnings`

#### Get Payment History
**GET** `/payments/history`

#### Request Withdrawal
**POST** `/payments/withdraw`

```json
{
  "amount": 1000,
  "paymentMethodId": "uuid"
}
```

#### Get Payment Methods
**GET** `/payments/methods`

#### Add Payment Method
**POST** `/payments/methods`

```json
{
  "type": "bank_transfer",
  "accountNumber": "123456789",
  "routingNumber": "987654321"
}
```

---

### Analytics Endpoints

#### Get Dashboard Analytics
**GET** `/analytics/dashboard`

#### Get Campaign Analytics
**GET** `/analytics/campaigns/:id`

#### Get Creator Analytics
**GET** `/analytics/creators/:id`

#### Get Brand Analytics
**GET** `/analytics/brands/:id`

---

## ❌ Error Handling

### Common Error Codes

| Code | Status | Description |
|------|--------|-------------|
| `INVALID_CREDENTIALS` | 401 | Invalid email or password |
| `UNAUTHORIZED` | 401 | Missing or invalid token |
| `FORBIDDEN` | 403 | Insufficient permissions |
| `NOT_FOUND` | 404 | Resource not found |
| `VALIDATION_ERROR` | 400 | Invalid input data |
| `CONFLICT` | 409 | Resource already exists |
| `RATE_LIMIT_EXCEEDED` | 429 | Too many requests |
| `INTERNAL_ERROR` | 500 | Server error |

### Error Response Example

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input data",
    "details": {
      "email": "Invalid email format",
      "password": "Password must be at least 8 characters"
    }
  }
}
```

---

## ⏱️ Rate Limiting

### Rate Limits

- **Authenticated Users:** 1000 requests per hour
- **Unauthenticated Users:** 100 requests per hour
- **Login Endpoint:** 5 requests per 15 minutes

### Rate Limit Headers

```
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 999
X-RateLimit-Reset: 1640000000
```

---

## 📞 Support

For API questions or issues:
- **GitHub:** https://github.com/influencerium/influencerium
- **Email:** support@influencerium.com
- **Documentation:** See INFLUENCERIUM_PROJECT_OVERVIEW.md

---

**Last Updated:** December 24, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete
