# Getting Started with Influencerium

This guide will help you set up the Influencerium project for local development.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 20.x or higher ([Download](https://nodejs.org/))
- **npm** 10.x or higher (comes with Node.js)
- **PostgreSQL** 15.x or higher ([Download](https://www.postgresql.org/download/))
- **Redis** 7.x or higher ([Download](https://redis.io/download))
- **Docker** & **Docker Compose** (optional, for containerized setup)
- **Git** ([Download](https://git-scm.com/))

## Quick Start (Docker)

The easiest way to get started is using Docker Compose:

```bash
# Clone the repository
git clone https://github.com/yourusername/influencerium.git
cd influencerium

# Start services (PostgreSQL, Redis)
docker-compose up -d

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env.local

# Run database migrations
npm run db:migrate

# Start development server
npm run dev
```

Visit `http://localhost:3000` to see the application.

## Manual Setup (Without Docker)

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/influencerium.git
cd influencerium
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Setup PostgreSQL

```bash
# Create database
createdb influencerium

# Create test database
createdb influencerium_test
```

### 4. Setup Redis

```bash
# Start Redis server
redis-server
```

### 5. Environment Variables

```bash
# Copy example environment file
cp .env.example .env.local

# Edit .env.local with your configuration
nano .env.local
```

### 6. Database Migrations

```bash
# Run migrations
npm run db:migrate

# Seed database (optional)
npm run db:seed
```

### 7. Start Development Server

```bash
# Start backend
npm run dev:backend

# In another terminal, start frontend
cd frontend
npm run dev
```

## Environment Variables

Create a `.env.local` file in the root directory:

```env
# Database
DATABASE_URL=postgresql://user:password@localhost:5432/influencerium
DATABASE_TEST_URL=postgresql://user:password@localhost:5432/influencerium_test

# Redis
REDIS_URL=redis://localhost:6379

# JWT
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRY=7d

# OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
INSTAGRAM_CLIENT_ID=your_instagram_client_id
INSTAGRAM_CLIENT_SECRET=your_instagram_client_secret

# Stripe
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

# Email
SENDGRID_API_KEY=your_sendgrid_api_key

# AWS S3
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_S3_BUCKET=your_s3_bucket_name
AWS_REGION=us-east-1

# App
NODE_ENV=development
PORT=3000
FRONTEND_URL=http://localhost:3001
```

## Project Structure

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
├── docker-compose.yml         # Docker services
├── .env.example               # Environment template
└── README.md                  # Project README
```

## Available Commands

### Backend

```bash
# Start development server
npm run dev:backend

# Build for production
npm run build:backend

# Run tests
npm run test

# Run tests with coverage
npm run test:coverage

# Lint code
npm run lint

# Format code
npm run format

# Database migrations
npm run db:migrate
npm run db:rollback
npm run db:seed
```

### Frontend

```bash
cd frontend

# Start development server
npm run dev

# Build for production
npm run build

# Run tests
npm run test

# Lint code
npm run lint

# Format code
npm run format
```

## Database Setup

### Create Tables

```bash
npm run db:migrate
```

### Seed Sample Data

```bash
npm run db:seed
```

### Reset Database

```bash
npm run db:reset
```

## Testing

### Run All Tests

```bash
npm run test
```

### Run Tests in Watch Mode

```bash
npm run test:watch
```

### Run Tests with Coverage

```bash
npm run test:coverage
```

### Run Specific Test File

```bash
npm run test -- path/to/test.spec.ts
```

## Debugging

### Backend Debugging

```bash
# Start with Node debugger
node --inspect-brk ./dist/index.js

# Open Chrome DevTools: chrome://inspect
```

### Frontend Debugging

Use React DevTools browser extension:
- [Chrome Extension](https://chrome.google.com/webstore/detail/react-developer-tools/)
- [Firefox Extension](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)

## Common Issues

### Port Already in Use

```bash
# Find process using port 3000
lsof -i :3000

# Kill process
kill -9 <PID>
```

### Database Connection Error

```bash
# Check PostgreSQL is running
psql -U postgres

# Check Redis is running
redis-cli ping
```

### Module Not Found

```bash
# Clear node_modules and reinstall
rm -rf node_modules
npm install
```

### Environment Variables Not Loading

```bash
# Ensure .env.local exists in root directory
# Restart development server
npm run dev
```

## Next Steps

1. Read the [Architecture Documentation](./ARCHITECTURE.md)
2. Review the [API Documentation](./API.md)
3. Check the [Database Schema](./DATABASE.md)
4. Start implementing features from [FEATURES_CHECKLIST.md](../FEATURES_CHECKLIST.md)

## Need Help?

- 📖 [Full Documentation](../INFLUENCERIUM_PROJECT_OVERVIEW.md)
- 🐛 [GitHub Issues](https://github.com/yourusername/influencerium/issues)
- 💬 [Discord Community](https://discord.gg/influencerium)
- 📧 [Email Support](mailto:support@influencerium.com)

---

**Last Updated:** December 23, 2025
