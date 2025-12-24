# Influencerium 🚀

> A creator-brand collaboration platform connecting influencers with brands for campaigns, contests, and exclusive deals.

[![Status](https://img.shields.io/badge/Status-In%20Development-blue)](https://github.com/yourusername/influencerium)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](./LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-20.x-brightgreen)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18.x-61DAFB?logo=react)](https://react.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15.x-336791?logo=postgresql)](https://www.postgresql.org/)

## 📖 Quick Links

- 📋 **[Full Project Overview](./INFLUENCERIUM_PROJECT_OVERVIEW.md)** - Comprehensive documentation with features, roadmap, and architecture
- 🏗️ **[Architecture Documentation](./docs/ARCHITECTURE.md)** - System design and technical details
- 📚 **[API Documentation](./docs/API.md)** - Complete API reference
- 🗄️ **[Database Schema](./docs/DATABASE.md)** - Database design and migrations
- 🚀 **[Getting Started](./docs/GETTING_STARTED.md)** - Local development setup
- 🤝 **[Contributing Guide](./CONTRIBUTING.md)** - How to contribute

## 🎯 What is Influencerium?

Influencerium is a modern platform that bridges the gap between content creators and brands. It enables:

- **Creators** to discover brand partnerships, monetize their influence, and grow their audience
- **Brands** to reach targeted audiences, launch campaigns, and measure ROI through authentic partnerships

## ✨ Key Features

### Phase 1: MVP (Current)
- ✅ User authentication (Email, Google, Instagram OAuth)
- ✅ Creator & Brand profiles with verification
- ✅ Campaign creation and discovery
- ✅ Application & approval workflow
- ✅ Direct messaging system
- ✅ Payment processing & earnings tracking
- ✅ Real-time notifications
- ✅ Analytics dashboard

### Phase 2: Enhanced (Q2 2026)
- 📊 Advanced analytics & reporting
- 🤖 AI-powered creator recommendations
- 👥 Team collaboration tools
- 💳 Advanced payment options

### Phase 3: Expansion (Q3-Q4 2026)
- 📱 Native mobile apps (iOS & Android)
- 🌐 Multi-language & multi-currency support
- 🔗 Third-party integrations
- 🤖 AI automation features

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React 18, Redux Toolkit, Tailwind CSS |
| **Backend** | Node.js, Express.js, TypeScript |
| **Database** | PostgreSQL, Redis |
| **Authentication** | JWT, OAuth 2.0 |
| **Payments** | Stripe, PayPal |
| **Storage** | AWS S3 |
| **Deployment** | Docker, AWS/DigitalOcean |

## 🚀 Quick Start

### Prerequisites
- Node.js 20.x+
- PostgreSQL 15.x+
- Redis 7.x+
- Docker & Docker Compose

### Setup

```bash
# Clone repository
git clone https://github.com/yourusername/influencerium.git
cd influencerium

# Install dependencies
npm install

# Setup environment
cp .env.example .env.local

# Start services
docker-compose up -d

# Run migrations
npm run db:migrate

# Start development
npm run dev
```

Visit `http://localhost:3000` to see the app.

## 📚 Documentation

### For Developers
- [Getting Started Guide](./docs/GETTING_STARTED.md)
- [Architecture Overview](./docs/ARCHITECTURE.md)
- [API Documentation](./docs/API.md)
- [Database Schema](./docs/DATABASE.md)
- [Development Workflow](./docs/DEVELOPMENT.md)

### For Project Managers
- [Full Project Overview](./INFLUENCERIUM_PROJECT_OVERVIEW.md)
- [Development Roadmap](./INFLUENCERIUM_PROJECT_OVERVIEW.md#-development-roadmap)
- [Timeline & Milestones](./INFLUENCERIUM_PROJECT_OVERVIEW.md#-timeline--milestones)

### For Designers
- [Design System](./docs/DESIGN_SYSTEM.md)
- [UI Components](./docs/UI_COMPONENTS.md)
- [Wireframes](./docs/WIREFRAMES.md)

## 📊 Project Status

### Current Phase: MVP Development (Q1 2026)

| Week | Focus | Status |
|------|-------|--------|
| 1-2 | Project Setup & Infrastructure | 🔄 In Progress |
| 3-4 | Authentication & User Management | 🔄 In Progress |
| 5-6 | Creator Features | ⏳ Upcoming |
| 7-8 | Brand Features | ⏳ Upcoming |
| 9-10 | Campaign Management | ⏳ Upcoming |
| 11-12 | Campaign Management (Part 2) | ⏳ Upcoming |
| 13-14 | Messaging & Notifications | ⏳ Upcoming |
| 15-16 | Payments & Testing | ⏳ Upcoming |

**Expected MVP Launch:** March 31, 2026

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for:
- Code of conduct
- Development guidelines
- Pull request process
- Commit message conventions

## 📋 Project Structure

```
influencerium/
├── backend/                    # Node.js/Express API
│   ├── src/
│   │   ├── services/          # Business logic
│   │   ├── controllers/       # Route handlers
│   │   ├── models/            # Database models
│   │   ├── middleware/        # Express middleware
│   │   ├── routes/            # API routes
│   │   └── utils/             # Utilities
│   ├── migrations/            # Database migrations
│   ├── tests/                 # Test files
│   └── package.json
│
├── frontend/                   # React web app
│   ├── src/
│   │   ├── components/        # React components
│   │   ├── pages/             # Page components
│   │   ├── services/          # API services
│   │   ├── store/             # Redux store
│   │   ├── styles/            # CSS/Tailwind
│   │   └── utils/             # Utilities
│   ├── public/                # Static files
│   └── package.json
│
├── docs/                       # Documentation
│   ├── ARCHITECTURE.md
│   ├── API.md
│   ├── DATABASE.md
│   ├── GETTING_STARTED.md
│   └── DEVELOPMENT.md
│
├── docker-compose.yml         # Docker services
├── .env.example               # Environment template
├── CONTRIBUTING.md            # Contribution guidelines
├── LICENSE                    # MIT License
└── README.md                  # This file
```

## 🔒 Security

- HTTPS/TLS encryption
- JWT token authentication
- OAuth 2.0 social login
- Password hashing (bcrypt)
- Rate limiting & DDoS protection
- SQL injection prevention
- XSS & CSRF protection
- Regular security audits

## 📞 Support

- 📧 **Email:** support@influencerium.com
- 💬 **Discord:** [Join Community](https://discord.gg/influencerium)
- 🐛 **Issues:** [GitHub Issues](https://github.com/yourusername/influencerium/issues)
- 📖 **Docs:** [docs.influencerium.com](https://docs.influencerium.com)

## 📄 License

This project is licensed under the Apache License 2.0 - see [LICENSE](./LICENSE) file for details.

**Key benefits of Apache 2.0:**
- ✅ Explicit patent grant and protection
- ✅ Patent retaliation clause
- ✅ Clear terms for commercial use
- ✅ Professional and enterprise-friendly
- ✅ Better legal protection than MIT
## 🙏 Acknowledgments

Built with ❤️ by the Influencerium Team

---

**Last Updated:** December 23, 2025  
**Version:** 1.0.0 (MVP Planning)  
**Status:** 🚀 In Active Development
