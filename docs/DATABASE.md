# Influencerium Database Schema

**Database Design and Migrations**

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Core Tables](#core-tables)
3. [Relationships](#relationships)
4. [Indexes](#indexes)
5. [Migrations](#migrations)

---

## 🗄️ Overview

Influencerium uses PostgreSQL 15.x as the primary database with the following characteristics:

- **Type:** Relational Database
- **DBMS:** PostgreSQL 15.x
- **ORM:** Prisma / TypeORM
- **Backup:** Daily automated backups
- **Replication:** Master-slave replication for high availability

---

## 📊 Core Tables

### Users Table

```sql
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255),
  first_name VARCHAR(100),
  last_name VARCHAR(100),
  avatar_url TEXT,
  bio TEXT,
  user_type ENUM('creator', 'brand', 'admin') NOT NULL,
  is_verified BOOLEAN DEFAULT false,
  is_active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  deleted_at TIMESTAMP
);

CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_user_type ON users(user_type);
```

### Creators Table

```sql
CREATE TABLE creators (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID UNIQUE NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  bio TEXT,
  niche VARCHAR(100),
  follower_count INTEGER DEFAULT 0,
  engagement_rate DECIMAL(5,2),
  verification_status ENUM('pending', 'verified', 'rejected') DEFAULT 'pending',
  rating DECIMAL(3,2),
  total_campaigns INTEGER DEFAULT 0,
  total_earnings DECIMAL(12,2) DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_creators_user_id ON creators(user_id);
CREATE INDEX idx_creators_niche ON creators(niche);
CREATE INDEX idx_creators_verification_status ON creators(verification_status);
```

### Brands Table

```sql
CREATE TABLE brands (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID UNIQUE NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  company_name VARCHAR(255) NOT NULL,
  industry VARCHAR(100),
  website VARCHAR(255),
  description TEXT,
  verification_status ENUM('pending', 'verified', 'rejected') DEFAULT 'pending',
  total_campaigns INTEGER DEFAULT 0,
  total_spent DECIMAL(12,2) DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_brands_user_id ON brands(user_id);
CREATE INDEX idx_brands_verification_status ON brands(verification_status);
```

### Campaigns Table

```sql
CREATE TABLE campaigns (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  brand_id UUID NOT NULL REFERENCES brands(id) ON DELETE CASCADE,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  category VARCHAR(100),
  budget DECIMAL(12,2) NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE NOT NULL,
  status ENUM('draft', 'active', 'paused', 'completed', 'cancelled') DEFAULT 'draft',
  target_audience_age_min INTEGER,
  target_audience_age_max INTEGER,
  target_audience_gender VARCHAR(50),
  target_audience_location VARCHAR(255),
  deliverables_count INTEGER,
  deliverables_description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_campaigns_brand_id ON campaigns(brand_id);
CREATE INDEX idx_campaigns_status ON campaigns(status);
CREATE INDEX idx_campaigns_category ON campaigns(category);
CREATE INDEX idx_campaigns_start_date ON campaigns(start_date);
```

### Applications Table

```sql
CREATE TABLE applications (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  campaign_id UUID NOT NULL REFERENCES campaigns(id) ON DELETE CASCADE,
  creator_id UUID NOT NULL REFERENCES creators(id) ON DELETE CASCADE,
  status ENUM('pending', 'approved', 'rejected', 'completed') DEFAULT 'pending',
  applied_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  approved_at TIMESTAMP,
  completed_at TIMESTAMP,
  payment_amount DECIMAL(12,2),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_applications_campaign_id ON applications(campaign_id);
CREATE INDEX idx_applications_creator_id ON applications(creator_id);
CREATE INDEX idx_applications_status ON applications(status);
CREATE UNIQUE INDEX idx_applications_unique ON applications(campaign_id, creator_id);
```

### Payments Table

```sql
CREATE TABLE payments (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  application_id UUID NOT NULL REFERENCES applications(id) ON DELETE CASCADE,
  amount DECIMAL(12,2) NOT NULL,
  status ENUM('pending', 'processing', 'completed', 'failed', 'refunded') DEFAULT 'pending',
  payment_method VARCHAR(50),
  transaction_id VARCHAR(255),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_payments_application_id ON payments(application_id);
CREATE INDEX idx_payments_status ON payments(status);
```

### Messages Table

```sql
CREATE TABLE messages (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  sender_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  recipient_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  campaign_id UUID REFERENCES campaigns(id) ON DELETE SET NULL,
  content TEXT NOT NULL,
  is_read BOOLEAN DEFAULT false,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_messages_sender_id ON messages(sender_id);
CREATE INDEX idx_messages_recipient_id ON messages(recipient_id);
CREATE INDEX idx_messages_campaign_id ON messages(campaign_id);
CREATE INDEX idx_messages_created_at ON messages(created_at);
```

### Portfolio Table

```sql
CREATE TABLE portfolio (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  creator_id UUID NOT NULL REFERENCES creators(id) ON DELETE CASCADE,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  image_url TEXT,
  video_url TEXT,
  link VARCHAR(255),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_portfolio_creator_id ON portfolio(creator_id);
```

### Payment Methods Table

```sql
CREATE TABLE payment_methods (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  type VARCHAR(50) NOT NULL,
  account_number VARCHAR(255),
  routing_number VARCHAR(255),
  is_default BOOLEAN DEFAULT false,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_payment_methods_user_id ON payment_methods(user_id);
```

### Social Media Links Table

```sql
CREATE TABLE social_media_links (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  platform VARCHAR(50) NOT NULL,
  url VARCHAR(255) NOT NULL,
  follower_count INTEGER,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_social_media_links_user_id ON social_media_links(user_id);
CREATE INDEX idx_social_media_links_platform ON social_media_links(platform);
```

---

## 🔗 Relationships

### User Relationships
- User → Creator (1:1)
- User → Brand (1:1)
- User → Messages (1:N) - as sender
- User → Messages (1:N) - as recipient
- User → Payment Methods (1:N)
- User → Social Media Links (1:N)

### Creator Relationships
- Creator → User (1:1)
- Creator → Applications (1:N)
- Creator → Portfolio (1:N)

### Brand Relationships
- Brand → User (1:1)
- Brand → Campaigns (1:N)

### Campaign Relationships
- Campaign → Brand (N:1)
- Campaign → Applications (1:N)
- Campaign → Messages (1:N)

### Application Relationships
- Application → Campaign (N:1)
- Application → Creator (N:1)
- Application → Payments (1:N)

---

## 📑 Indexes

### Performance Indexes

```sql
-- User lookups
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_user_type ON users(user_type);

-- Creator searches
CREATE INDEX idx_creators_niche ON creators(niche);
CREATE INDEX idx_creators_verification_status ON creators(verification_status);

-- Campaign filtering
CREATE INDEX idx_campaigns_status ON campaigns(status);
CREATE INDEX idx_campaigns_category ON campaigns(category);
CREATE INDEX idx_campaigns_start_date ON campaigns(start_date);

-- Application tracking
CREATE INDEX idx_applications_status ON applications(status);

-- Message queries
CREATE INDEX idx_messages_created_at ON messages(created_at);

-- Composite indexes for common queries
CREATE INDEX idx_campaigns_brand_status ON campaigns(brand_id, status);
CREATE INDEX idx_applications_campaign_status ON applications(campaign_id, status);
```

---

## 🔄 Migrations

### Migration Structure

```
migrations/
├── 001_create_users_table.sql
├── 002_create_creators_table.sql
├── 003_create_brands_table.sql
├── 004_create_campaigns_table.sql
├── 005_create_applications_table.sql
├── 006_create_payments_table.sql
├── 007_create_messages_table.sql
├── 008_create_portfolio_table.sql
├── 009_create_payment_methods_table.sql
└── 010_create_social_media_links_table.sql
```

### Running Migrations

```bash
# Run all pending migrations
npm run db:migrate

# Rollback last migration
npm run db:rollback

# Reset database (development only)
npm run db:reset

# Seed database with sample data
npm run db:seed
```

---

## 📊 Database Statistics

### Estimated Table Sizes (at scale)

| Table | Rows | Size |
|-------|------|------|
| users | 100K | 50MB |
| creators | 50K | 25MB |
| brands | 10K | 5MB |
| campaigns | 50K | 30MB |
| applications | 500K | 200MB |
| payments | 500K | 150MB |
| messages | 5M | 1GB |
| portfolio | 100K | 500MB |

---

## 🔐 Security

### Data Protection
- Passwords hashed with bcrypt
- Sensitive data encrypted at rest
- PII protected with encryption
- Regular backups (daily)

### Access Control
- Row-level security (RLS) for multi-tenancy
- User isolation by user_id
- Brand isolation by brand_id
- Creator isolation by creator_id

---

## 📞 Support

For database questions:
- **GitHub:** https://github.com/influencerium/influencerium
- **Email:** support@influencerium.com

---

**Last Updated:** December 24, 2025  
**Version:** 1.0.0  
**Status:** ✅ Complete
