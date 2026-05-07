# ONEKEEP: Industrial Service Marketplace

[![Node.js](https://img.shields.io/badge/Node.js-v14%2B-green?logo=node.js)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-4.x-000000?logo=express)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Latest-13aa52?logo=mongodb)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active%20Development-brightgreen)](https://github.com)

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Development](#development)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

---

## 📌 About

A comprehensive, enterprise-grade service management platform built with modern web technologies. This full-stack application provides a complete solution for managing services, orders, payments, worker profiles, and customer interactions. The platform is designed to streamline operations, enhance customer experience, and provide real-time tracking and notifications.

**Key Use Cases:**
- Multi-service marketplace management
- Scheduled service delivery and tracking
- Payment processing and invoicing
- Customer support and communication
- Worker management and performance tracking

---

## 📁 Project Structure

```
service-management-platform/
│
├── backend/                          # Express.js REST API Server
│   ├── controllers/                 # Business logic & request handlers
│   │   ├── auth.controller.js      # Authentication operations
│   │   ├── order.controller.js     # Order processing
│   │   ├── payment.controller.js   # Payment handling
│   │   ├── worker.controller.js    # Worker management
│   │   └── ...
│   │
│   ├── models/                      # MongoDB schemas & data models
│   │   ├── User.js
│   │   ├── Order.js
│   │   ├── Payment.js
│   │   ├── WorkerProfile.js
│   │   └── ...
│   │
│   ├── routes/                      # API endpoint definitions
│   │   ├── auth.routes.js
│   │   ├── order.routes.js
│   │   ├── payment.routes.js
│   │   └── ...
│   │
│   ├── middlewares/                 # Express middleware functions
│   │   ├── auth.middleware.js      # JWT verification
│   │   ├── role.middleware.js      # Role-based access control
│   │   ├── error.middleware.js     # Centralized error handling
│   │   └── validate.middleware.js  # Request validation
│   │
│   ├── config/                      # Configuration modules
│   │   ├── db.js                   # MongoDB connection
│   │   ├── cloudinary.js           # Image upload config
│   │   ├── razorpay.js             # Payment gateway setup
│   │   └── mailer.js               # Email service config
│   │
│   ├── utils/                       # Utility functions
│   │   ├── ApiError.js             # Custom error class
│   │   ├── ApiResponse.js          # Standardized response format
│   │   ├── asyncHandler.js         # Async route wrapper
│   │   └── ...
│   │
│   ├── scripts/                     # Database seeding & utilities
│   │   ├── seed.js
│   │   └── seedAdmin.js
│   │
│   ├── app.js                       # Express app configuration
│   ├── server.js                    # Server entry point
│   └── package.json                 # Dependencies & scripts
│
└── frontend/                         # Vanilla JavaScript Frontend
    ├── index.html                   # Main HTML document
    │
    ├── js/
    │   ├── main.js                  # Application entry point
    │   │
    │   ├── core/                    # Core modules
    │   │   ├── api.js              # HTTP client & API calls
    │   │   ├── auth.js             # Authentication logic
    │   │   ├── router.js           # Client-side routing
    │   │   ├── config.js           # Configuration
    │   │   └── map.js              # Geolocation services
    │   │
    │   ├── components/              # Reusable UI components
    │   │   ├── navbar.js
    │   │   ├── modal.js
    │   │   ├── table.js
    │   │   ├── form.js
    │   │   └── ...
    │   │
    │   ├── modules/                 # Feature modules
    │   ├── pages/                   # Page-specific logic
    │   └── utils/                   # Utility functions
    │
    └── assets/                      # Static assets
        └── images/
```

---

## 🛠 Tech Stack

### Backend Architecture
| Component | Technology | Purpose |
|-----------|-----------|---------|
| Runtime | Node.js | Server-side JavaScript execution |
| Framework | Express.js | RESTful API framework |
| Database | MongoDB | NoSQL document database |
| Authentication | JWT | Stateless authentication tokens |
| File Storage | Cloudinary | Cloud-based image management |
| Payments | Razorpay | Payment gateway integration |
| Email | SMTP | Transactional email service |
| Upload Handling | Multer | File upload middleware |
| Middleware | Custom | Request validation and error handling |

### Frontend Stack
| Component | Technology |
|-----------|-----------|
| Markup | HTML5 |
| Scripting | Vanilla JavaScript (ES6+) |
| Routing | Custom Router |
| Maps | Integrated Geolocation |
| API Client | Custom HTTP Module |
| UI Components | Custom Component Library |

---

## ✨ Features

### Core Features
- **🔐 Secure Authentication** - JWT-based authentication with role-based access control (RBAC)
- **🛒 Order Management** - Complete order lifecycle from creation to delivery and tracking
- **💳 Payment Processing** - Seamless integration with Razorpay for secure payments
- **👷 Worker Management** - Comprehensive worker profiles and performance tracking
- **📋 Service Categories** - Flexible service templates and categorization system
- **🔄 AMC Plans** - Annual Maintenance Contract management and billing
- **💬 Real-time Chat** - Integrated messaging between users and support teams
- **🔔 Notifications** - Real-time notification system for order updates and messages
- **📍 GPS Tracking** - Live tracking of service delivery with audit logs
- **⭐ Review System** - Customer ratings and reviews for quality assurance
- **🎫 Support Tickets** - Ticketing system for customer support management
- **📊 Admin Dashboard** - Comprehensive analytics and system administration tools
- **☁️ Cloud Storage** - Cloudinary integration for scalable image management
- **✉️ Email Service** - Automated email notifications and communications

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

| Requirement | Version | Purpose |
|------------|---------|---------|
| **Node.js** | v14.0.0+ | JavaScript runtime |
| **npm** or **yarn** | Latest | Package manager |
| **MongoDB** | v4.4.0+ | Database (local or Atlas) |
| **Git** | Latest | Version control |

### External Services (Required for Full Functionality)
- **Cloudinary Account** - [Sign up here](https://cloudinary.com/users/register/free) for image hosting
- **Razorpay Account** - [Sign up here](https://razorpay.com/) for payment processing
- **Email Service** - SMTP credentials (Gmail, SendGrid, etc.)

### Verification
```bash
# Check Node.js
node --version

# Check npm
npm --version

# Check MongoDB
mongod --version
```

---

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/service-management-platform.git
cd service-management-platform
```

### Step 2: Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Create environment configuration
cp .env.example .env
```

### Step 3: Frontend Setup

```bash
cd ../frontend

# No npm dependencies needed for vanilla JavaScript frontend
# Ensure proper HTTP server for serving static files
```

### Step 4: Database Setup

```bash
# Navigate back to backend
cd ../backend

# Seed initial data (ensure MongoDB is running)
npm run seed

# Optional: Seed admin user
npm run seed:admin
```

### Step 5: Start the Application

#### Terminal 1 - Backend Server
```bash
cd backend
npm start
# or for development with auto-reload
npm run dev
```

#### Terminal 2 - Frontend Server
```bash
cd frontend
# Option 1: Using Python
python -m http.server 3000

# Option 2: Using Node.js http-server
npx http-server -p 3000

# Option 3: Using VS Code Live Server Extension
# Right-click index.html > Open with Live Server
```

The application will be accessible at:
- **Backend API**: `http://localhost:5000`
- **Frontend**: `http://localhost:3000`

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the `backend` directory with the following variables:

```bash
# ============ SERVER CONFIGURATION ============
NODE_ENV=development
PORT=5000

# ============ DATABASE CONFIGURATION ============
MONGODB_URI=mongodb://localhost:27017/service_platform
# OR for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/dbname
DB_NAME=service_platform

# ============ AUTHENTICATION ============
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRY=7d

# ============ CLOUDINARY (Image Storage) ============
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# ============ RAZORPAY (Payment Gateway) ============
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
RAZORPAY_WEBHOOK_SECRET=your_webhook_secret

# ============ EMAIL CONFIGURATION ============
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
SMTP_FROM=noreply@yourcompany.com

# ============ CORS & FRONTEND ============
FRONTEND_URL=http://localhost:3000
ALLOWED_ORIGINS=http://localhost:3000,http://localhost:3001

# ============ OPTIONAL ============
LOG_LEVEL=debug
UPLOAD_LIMIT=50mb
```

### Configuration Files

| File | Purpose |
|------|---------|
| `backend/config/db.js` | MongoDB connection setup |
| `backend/config/cloudinary.js` | Image hosting configuration |
| `backend/config/razorpay.js` | Payment gateway setup |
| `backend/config/mailer.js` | Email service configuration |
| `frontend/js/core/config.js` | API and frontend configuration |

---

## 🔌 API Reference

The API follows RESTful conventions with comprehensive endpoint coverage.

### Authentication Endpoints
```
POST   /api/auth/register          # User registration
POST   /api/auth/login             # User login
POST   /api/auth/refresh-token     # Refresh JWT token
POST   /api/auth/logout            # User logout
POST   /api/auth/forgot-password   # Initiate password reset
```

### Order Management
```
GET    /api/orders                 # List all orders
POST   /api/orders                 # Create new order
GET    /api/orders/:id             # Get order details
PATCH  /api/orders/:id             # Update order status
DELETE /api/orders/:id             # Cancel order
GET    /api/orders/:id/tracking    # Get real-time tracking
```

### Payment Processing
```
POST   /api/payments               # Create payment order
POST   /api/payments/verify        # Verify payment
GET    /api/payments/history       # Payment history
GET    /api/payments/:id           # Payment details
```

### Services & Categories
```
GET    /api/services               # List all services
POST   /api/services               # Create service
GET    /api/categories             # List categories
POST   /api/categories             # Create category
GET    /api/subcategories          # List subcategories
```

### Worker Management
```
GET    /api/workers                # List workers
POST   /api/workers                # Register worker
GET    /api/workers/:id            # Worker profile
PATCH  /api/workers/:id            # Update profile
GET    /api/workers/:id/performance # Performance metrics
```

### Additional Endpoints
- **Notifications**: `/api/notifications/*`
- **Chat/Messaging**: `/api/chat/*`
- **Support Tickets**: `/api/support/*`
- **Reviews**: `/api/reviews/*`
- **AMC Plans**: `/api/amc/*`
- **Admin**: `/api/admin/*`

For detailed API documentation with request/response examples, see [API_DOCUMENTATION.md](./API_DOCUMENTATION.md)

---

## 🔐 Authentication & Authorization

### JWT-Based Authentication

The application uses JSON Web Tokens (JWT) for secure, stateless authentication:

1. **Login**: User credentials are validated; JWT token is issued
2. **Token Storage**: Store token in localStorage on the client
3. **Protected Routes**: Include token in Authorization header: `Bearer <token>`
4. **Token Validation**: Server validates token on protected routes
5. **Token Refresh**: Use refresh token endpoint to get new access token

### Role-Based Access Control (RBAC)

Four primary roles with hierarchical permissions:

```
┌─────────────────────────────────────────────────────────┐
│                       ADMIN                             │
│  Full system access, user management, analytics         │
├─────────────────────────────────────────────────────────┤
│                    ORGANIZATION                          │
│  Manage services, workers, orders, support tickets      │
├─────────────────────────────────────────────────────────┤
│                      WORKER                              │
│  Accept jobs, update status, communicate with users     │
├─────────────────────────────────────────────────────────┤
│                       USER                               │
│  Create orders, view tracking, manage profile           │
└─────────────────────────────────────────────────────────┘
```

### Protected Route Example

```javascript
router.get('/api/orders', authenticate, authorize(['admin', 'organization', 'user']), controller);
```

---

## 📤 File Uploads

### Supported Formats
- **Images**: JPG, PNG, GIF, WebP (Max 5MB)
- **Documents**: PDF, DOC, DOCX (Max 10MB)

### Upload Process
1. File selected and validated on frontend
2. Sent to backend via multipart/form-data
3. Processed through Multer middleware
4. Uploaded to Cloudinary
5. URL stored in database

### Configuration
```javascript
// backend/config/cloudinary.js
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

---

## 🧪 Testing

### Test Files
- `backend/test_order.js` - Order functionality tests
- `backend/test_reqs.js` - Requirement & validation tests

### Running Tests
```bash
cd backend
npm test

# Run specific test file
npm test -- test_order.js
```

### Testing Tools
- Jest (if configured) or custom test runner
- Manual API testing with Postman/Insomnia

---

## 🚢 Deployment

### Production Checklist

- [ ] Update `NODE_ENV=production`
- [ ] Use strong `JWT_SECRET`
- [ ] Configure MongoDB Atlas connection
- [ ] Set up Cloudinary CDN
- [ ] Configure Razorpay production keys
- [ ] Set up email service (SendGrid/AWS SES)
- [ ] Enable HTTPS
- [ ] Configure CORS for production domain
- [ ] Set up database backups
- [ ] Enable rate limiting
- [ ] Configure logging & monitoring

### Deployment Platforms

**Recommended Options:**
- **Heroku** - Easy deployment with Git push
- **AWS EC2** - Full control over infrastructure
- **DigitalOcean** - Affordable VPS hosting
- **Railway** - Modern platform with MongoDB support
- **Vercel** (Frontend only) - Fast static hosting
- **Netlify** (Frontend only) - JAMstack deployment

### Environment Setup for Production

```bash
# Production .env
NODE_ENV=production
PORT=80
MONGODB_URI=mongodb+srv://prod_user:prod_pass@prod-cluster.mongodb.net/service_platform
JWT_SECRET=your_very_long_random_secret_key_with_special_chars_123!@#
FRONTEND_URL=https://yourdomain.com
```

---

## 🐛 Troubleshooting

### Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| **MongoDB Connection Error** | Ensure MongoDB is running (`mongod`), check connection string, verify firewall rules |
| **Port Already in Use** | Change PORT in `.env` or kill process: `lsof -ti:5000 \| xargs kill -9` |
| **JWT Authentication Failed** | Verify JWT_SECRET is set, check token format in Authorization header |
| **Cloudinary Upload Fails** | Verify API credentials, check file size limits, ensure cloud is active |
| **Payment Gateway Error** | Verify Razorpay keys, check webhook configuration, ensure test mode is correct |
| **CORS Error** | Add frontend URL to ALLOWED_ORIGINS in `.env`, configure CORS middleware |
| **Email Not Sending** | Verify SMTP credentials, check firewall port 587, enable "Less secure apps" if using Gmail |
| **Frontend Not Loading** | Ensure HTTP server is running, check FRONTEND_URL matches actual URL |

### Debug Mode

Enable detailed logging:
```bash
# .env
LOG_LEVEL=debug
```

### Logs Location
- **Backend**: Console output or `logs/` directory
- **Frontend**: Browser DevTools Console (F12)

---

## 📚 Development

### Code Structure Standards

**File Naming:**
- Controllers: `*.controller.js`
- Models: `*.js` (PascalCase)
- Routes: `*.routes.js`
- Middlewares: `*.middleware.js`
- Utilities: `*.js` (descriptive names)

**Code Style:**
- Use ESLint for consistency
- Follow async/await patterns
- Implement error handling with try-catch
- Use meaningful variable names
- Add JSDoc comments for functions

### Running in Development

```bash
# Backend with auto-reload
npm run dev

# Frontend with live server
python -m http.server 3000

# Run both simultaneously
npm run dev:all
```

### Database Migrations

```bash
# Seed development data
npm run seed

# Seed admin user
npm run seed:admin

# Reset database
npm run db:reset
```

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

### Process
1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Guidelines
- Follow existing code style
- Add comments for complex logic
- Test your changes thoroughly
- Update documentation if needed
- Don't commit sensitive information

### Commit Message Format
```
[FEATURE/FIX/DOCS]: Brief description

Detailed explanation of changes made...
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support & Contact

For support, feature requests, or bug reports:

- **Email**: support@yourcompany.com
- **Issues**: [GitHub Issues](https://github.com/yourusername/repo/issues)
- **Documentation**: [Full Docs](./docs/README.md)
- **FAQ**: [Frequently Asked Questions](./FAQ.md)

---

## 🙏 Acknowledgments

- [Express.js](https://expressjs.com/) - Web framework
- [MongoDB](https://www.mongodb.com/) - Database
- [Cloudinary](https://cloudinary.com/) - Image management
- [Razorpay](https://razorpay.com/) - Payment processing
- All contributors and supporters

---

**Made with ❤️ by the Development Team**

Last updated: May 2026 | Version: 1.0.0
