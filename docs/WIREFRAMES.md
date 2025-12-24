# Influencerium Wireframes

**UI/UX Wireframes and User Flows**

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Authentication Flows](#authentication-flows)
3. [Creator User Flows](#creator-user-flows)
4. [Brand User Flows](#brand-user-flows)
5. [Campaign Flows](#campaign-flows)
6. [Messaging Flows](#messaging-flows)
7. [Payment Flows](#payment-flows)

---

## 🎯 Overview

Wireframes provide a visual representation of the user interface and user flows for the Influencerium platform. These wireframes guide the development of both web and mobile applications.

### Wireframe Principles

- **User-Centric** - Designed around user needs
- **Clear Navigation** - Intuitive user flows
- **Responsive** - Work on all devices
- **Accessible** - Inclusive design
- **Consistent** - Follow design system

---

## 🔐 Authentication Flows

### Login Flow

```
┌─────────────────────────────────────┐
│         Login Page                  │
├─────────────────────────────────────┤
│                                     │
│  Email: [________________]          │
│  Password: [________________]       │
│                                     │
│  [Login Button]                     │
│  [Forgot Password Link]             │
│  [Sign Up Link]                     │
│                                     │
│  OR                                 │
│                                     │
│  [Login with Google]                │
│  [Login with Instagram]             │
│                                     │
└─────────────────────────────────────┘
         ↓ (Success)
┌─────────────────────────────────────┐
│      Dashboard Page                 │
└─────────────────────────────────────┘
```

### Registration Flow

```
┌─────────────────────────────────────┐
│      Registration Page              │
├─────────────────────────────────────┤
│                                     │
│  Email: [________________]          │
│  Password: [________________]       │
│  Confirm: [________________]        │
│                                     │
│  User Type:                         │
│  ○ Creator  ○ Brand                 │
│                                     │
│  [Create Account]                   │
│  [Already have account? Login]      │
│                                     │
└─────────────────────────────────────┘
         ↓ (Success)
┌─────────────────────────────────────┐
│   Email Verification Page           │
├─────────────────────────────────────┤
│  Verify your email to continue      │
│  [Resend Email]                     │
└─────────────────────────────────────┘
```

---

## 👤 Creator User Flows

### Creator Dashboard

```
┌──────────────────────────────────────────────────────┐
│  Navbar: Logo | Search | Messages | Profile | Logout │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Sidebar:                    Main Content:           │
│  ├─ Dashboard               ┌──────────────────────┐ │
│  ├─ Campaigns               │ Welcome Back, John!  │ │
│  ├─ Applications            │                      │ │
│  ├─ Earnings                │ Quick Stats:         │ │
│  ├─ Portfolio               │ • Active: 3          │ │
│  ├─ Messages                │ • Earnings: $5,000   │ │
│  └─ Settings                │ • Followers: 50K     │ │
│                             │                      │ │
│                             │ Recent Campaigns:    │ │
│                             │ [Campaign Card 1]    │ │
│                             │ [Campaign Card 2]    │ │
│                             │ [Campaign Card 3]    │ │
│                             └──────────────────────┘ │
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Campaign Discovery

```
┌──────────────────────────────────────────────────────┐
│  Navbar                                              │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Filters:                    Campaign List:          │
│  ├─ Category                 ┌──────────────────────┐│
│  ├─ Budget Range             │ Campaign 1           ││
│  ├─ Timeline                 │ Budget: $5,000       ││
│  └─ [Apply Filters]          │ Timeline: 30 days    ││
│                              │ [View] [Apply]       ││
│                              └──────────────────────┘│
│                              ┌──────────────────────┐│
│                              │ Campaign 2           ││
│                              │ Budget: $3,000       ││
│                              │ Timeline: 14 days    ││
│                              │ [View] [Apply]       ││
│                              └──────────────────────┘│
│                              ┌──────────────────────┐│
│                              │ Campaign 3           ││
│                              │ Budget: $7,500       ││
│                              │ Timeline: 45 days    ││
│                              │ [View] [Apply]       ││
│                              └──────────────────────┘│
│                                                      │
│                              [< Prev] [1] [2] [Next >]
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Creator Profile

```
┌──────────────────────────────────────────────────────┐
│  Navbar                                              │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌────────────────────────────────────────────────┐ │
│  │ [Avatar] John Doe                              │ │
│  │ ⭐ 4.8 (50 reviews)                            │ │
│  │ Technology | 50K Followers                     │ │
│  │ [Edit Profile] [Share]                         │ │
│  └────────────────────────────────────────────────┘ │
│                                                      │
│  Bio:                                                │
│  "Passionate about tech and innovation..."          │
│                                                      │
│  Social Media:                                       │
│  Instagram: @johndoe (50K)                          │
│  TikTok: @johndoe (30K)                             │
│  YouTube: John Doe (100K)                           │
│                                                      │
│  Portfolio:                                          │
│  [Portfolio Item 1] [Portfolio Item 2]              │
│  [Portfolio Item 3] [Portfolio Item 4]              │
│                                                      │
│  Statistics:                                         │
│  • Total Campaigns: 15                              │
│  • Completed: 14                                    │
│  • Total Earnings: $25,000                          │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## 🏢 Brand User Flows

### Brand Dashboard

```
┌──────────────────────────────────────────────────────┐
│  Navbar: Logo | Search | Messages | Profile | Logout │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Sidebar:                    Main Content:           │
│  ├─ Dashboard               ┌──────────────────────┐ │
│  ├─ Campaigns               │ Welcome, Acme Corp!  │ │
│  ├─ Creators                │                      │ │
│  ├─ Analytics               │ Quick Stats:         │ │
│  ├─ Team                    │ • Active: 2          │ │
│  ├─ Messages                │ • Budget Used: 60%   │ │
│  └─ Settings                │ • ROI: 3.2x          │ │
│                             │                      │ │
│                             │ Active Campaigns:    │ │
│                             │ [Campaign Card 1]    │ │
│                             │ [Campaign Card 2]    │ │
│                             └──────────────────────┘ │
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Creator Discovery

```
┌──────────────────────────────────────────────────────┐
│  Navbar                                              │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Filters:                    Creator List:           │
│  ├─ Niche                    ┌──────────────────────┐│
│  ├─ Followers                │ Creator 1            ││
│  ├─ Engagement               │ Tech | 50K followers ││
│  ├─ Location                 │ ⭐ 4.8               ││
│  └─ [Apply Filters]          │ [View] [Contact]     ││
│                              └──────────────────────┘│
│                              ┌──────────────────────┐│
│                              │ Creator 2            ││
│                              │ Fashion | 30K        ││
│                              │ ⭐ 4.5               ││
│                              │ [View] [Contact]     ││
│                              └──────────────────────┘│
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## 📢 Campaign Flows

### Create Campaign

```
┌──────────────────────────────────────────────────────┐
│  Create Campaign                                     │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Step 1: Basic Information                          │
│  ├─ Campaign Title: [________________]              │
│  ├─ Description: [________________]                 │
│  ├─ Category: [Dropdown]                           │
│  └─ [Next]                                          │
│                                                      │
│  Step 2: Budget & Timeline                          │
│  ├─ Budget: $[________________]                     │
│  ├─ Start Date: [Date Picker]                      │
│  ├─ End Date: [Date Picker]                        │
│  └─ [Next]                                          │
│                                                      │
│  Step 3: Target Audience                            │
│  ├─ Age Range: [__] - [__]                         │
│  ├─ Gender: [Dropdown]                             │
│  ├─ Location: [________________]                    │
│  └─ [Next]                                          │
│                                                      │
│  Step 4: Requirements                               │
│  ├─ Deliverables: [________________]               │
│  ├─ Guidelines: [________________]                  │
│  └─ [Create Campaign]                              │
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Campaign Details

```
┌──────────────────────────────────────────────────────┐
│  Campaign: "Summer Tech Campaign"                    │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Status: Active                                      │
│  Budget: $10,000                                     │
│  Timeline: 30 days                                   │
│                                                      │
│  Tabs: [Overview] [Applications] [Analytics]        │
│                                                      │
│  Applications:                                       │
│  ┌──────────────────────────────────────────────┐  │
│  │ Creator 1 - Pending                          │  │
│  │ Rate: $500 | [Approve] [Reject]              │  │
│  └──────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────┐  │
│  │ Creator 2 - Approved                         │  │
│  │ Rate: $750 | [View Details]                  │  │
│  └──────────────────────────────────────────────┘  │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## 💬 Messaging Flows

### Messaging Interface

```
┌──────────────────────────────────────────────────────┐
│  Messages                                            │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Conversations:          Chat:                       │
│  ┌──────────────────┐   ┌──────────────────────────┐│
│  │ John Doe         │   │ John Doe                 ││
│  │ Last: 2 min ago  │   │ Campaign: Summer Tech    ││
│  │ [Unread: 3]      │   │                          ││
│  └──────────────────┘   │ [Message 1]              ││
│  ┌──────────────────┐   │ [Message 2]              ││
│  │ Jane Smith       │   │ [Message 3]              ││
│  │ Last: 1 hour ago │   │                          ││
│  └──────────────────┘   │ [Your Message]           ││
│  ┌──────────────────┐   │                          ││
│  │ Acme Corp        │   │ [Type message...]        ││
│  │ Last: 3 hours ago│   │ [Send]                   ││
│  └──────────────────┘   └──────────────────────────┘│
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## 💳 Payment Flows

### Earnings Dashboard

```
┌──────────────────────────────────────────────────────┐
│  Earnings                                            │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Total Earnings: $25,000                             │
│  Available: $5,000                                   │
│  Pending: $2,000                                     │
│                                                      │
│  [Withdraw] [View History]                           │
│                                                      │
│  Recent Transactions:                                │
│  ┌──────────────────────────────────────────────┐  │
│  │ Campaign 1 - Completed                       │  │
│  │ Amount: $1,000 | Date: Dec 20, 2025          │  │
│  │ Status: Paid                                 │  │
│  └──────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────┐  │
│  │ Campaign 2 - Completed                       │  │
│  │ Amount: $750 | Date: Dec 15, 2025            │  │
│  │ Status: Paid                                 │  │
│  └──────────────────────────────────────────────┘  │
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Withdrawal Flow

```
┌──────────────────────────────────────────────────────┐
│  Request Withdrawal                                  │
├──────────────────────────────────────────────────────┤
│                                                      │
│  Available Balance: $5,000                           │
│                                                      │
│  Amount: $[________________]                         │
│                                                      │
│  Payment Method:                                     │
│  ○ Bank Transfer                                     │
│  ○ PayPal                                            │
│  ○ Stripe                                            │
│                                                      │
│  [Request Withdrawal]                               │
│                                                      │
│  Processing time: 3-5 business days                 │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## 📱 Mobile Wireframes

### Mobile Navigation

```
┌─────────────────┐
│ ☰ | Logo | 👤   │
├─────────────────┤
│                 │
│  Main Content   │
│                 │
│                 │
├─────────────────┤
│ 🏠 📢 💬 👤 ⚙️  │
└─────────────────┘
```

### Mobile Campaign Card

```
┌─────────────────┐
│ Campaign Title  │
├─────────────────┤
│ Budget: $5,000  │
│ Timeline: 30d   │
│ Status: Active  │
│                 │
│ [View] [Apply]  │
└─────────────────┘
```

---

## 📞 Support

For wireframe questions:
- **GitHub:** https://github.com/influencerium/influencerium
- **Email:** support@influencerium.com

---

**Last Updated:** December 24, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete
