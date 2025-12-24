# College Utility Hub - Complete Project Documentation

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Architecture](#project-architecture)
- [Database Schema](#database-schema)
- [API Documentation](#api-documentation)
- [Frontend Components](#frontend-components)
- [Setup & Installation](#setup--installation)
- [Environment Variables](#environment-variables)
- [Scripts](#scripts)
- [Deployment](#deployment)
- [Security Features](#security-features)

---

## 🎯 Project Overview

**College Utility Hub** is a comprehensive full-stack web application designed to centralize and streamline college utilities. It provides an integrated platform for managing notices, events, lost & found items, and feedback with role-based access control.

### Purpose
- Centralized communication platform for college announcements
- Event management and tracking
- Lost & found items reporting and recovery system
- Anonymous and named feedback collection
- Administrative control and moderation

---

## ✨ Features

### For Students
- ✅ **Notice Board**: View categorized college announcements and notifications
- ✅ **Event Management**: Browse upcoming college events with details
- ✅ **Lost & Found**: Report lost/found items with images and descriptions
- ✅ **Feedback System**: Submit anonymous or named feedback to administration
- ✅ **Personal Dashboard**: View statistics and recent activities
- ✅ **Profile Management**: Update personal information

### For Administrators
- ✅ **Notice Management**: Create, edit, and delete notices with categories
- ✅ **Event Management**: Manage college events and track RSVPs
- ✅ **Lost & Found Moderation**: Approve/reject submitted items
- ✅ **Feedback Review**: View and resolve student feedback
- ✅ **Admin Management**: Add/remove administrators
- ✅ **Statistics Dashboard**: View comprehensive analytics

---

## 🛠 Technology Stack

### Backend Technologies

| Technology | Version | Purpose |
|------------|---------|---------|
| **Node.js** | v18+ | Runtime environment |
| **Express.js** | ^4.18.2 | Web application framework |
| **MongoDB** | ^8.0.3 | NoSQL database |
| **Mongoose** | ^8.0.3 | MongoDB ODM |
| **JWT** | ^9.0.2 | Authentication & authorization |
| **bcryptjs** | ^2.4.3 | Password hashing |
| **express-validator** | ^7.0.1 | Request validation |
| **cors** | ^2.8.5 | Cross-origin resource sharing |
| **dotenv** | ^16.3.1 | Environment variable management |
| **morgan** | ^1.10.0 | HTTP request logger |
| **nodemon** | ^3.0.2 | Development auto-restart (dev) |

### Frontend Technologies

| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | ^18.2.0 | UI framework |
| **Vite** | ^4.2.1 | Build tool & dev server |
| **React Router DOM** | ^6.21.0 | Client-side routing |
| **Tailwind CSS** | ^3.3.6 | Utility-first CSS framework |
| **Axios** | ^1.6.2 | HTTP client |
| **React Hook Form** | ^7.49.0 | Form handling |
| **Zod** | ^3.22.4 | Schema validation |
| **Framer Motion** | ^12.23.26 | Animation library |
| **date-fns** | ^2.30.0 | Date manipulation |

### UI Component Libraries

| Library | Purpose |
|---------|---------|
| **shadcn/ui** | Pre-built accessible components |
| **Radix UI** | Headless UI primitives |
| **Lucide React** | Icon library |
| **Sonner** | Toast notifications |

---

## 🏗 Project Architecture

### Folder Structure

```
college-utility-hub/
│
├── backend/                          # Backend API Server
│   ├── config/                       # Configuration files
│   │   ├── admins.json              # Admin credentials
│   │   ├── admins.example.json      # Admin template
│   │   └── db.js                    # MongoDB connection
│   │
│   ├── controllers/                  # Request handlers
│   │   ├── authController.js        # Authentication logic
│   │   ├── eventController.js       # Event CRUD operations
│   │   ├── feedbackController.js    # Feedback handling
│   │   ├── lostFoundController.js   # Lost & found logic
│   │   ├── noticeController.js      # Notice management
│   │   └── statsController.js       # Statistics aggregation
│   │
│   ├── middleware/                   # Custom middleware
│   │   ├── auth.js                  # JWT verification
│   │   └── errorHandler.js          # Error handling
│   │
│   ├── models/                       # Mongoose schemas
│   │   ├── Event.js                 # Event model
│   │   ├── Feedback.js              # Feedback model
│   │   ├── LostAndFound.js          # Lost & found model
│   │   ├── Notice.js                # Notice model
│   │   └── User.js                  # User model
│   │
│   ├── routes/                       # API routes
│   │   ├── auth.js                  # Authentication routes
│   │   ├── events.js                # Event routes
│   │   ├── feedback.js              # Feedback routes
│   │   ├── lostfound.js             # Lost & found routes
│   │   ├── notices.js               # Notice routes
│   │   └── stats.js                 # Statistics routes
│   │
│   ├── utils/                        # Utility functions
│   │   └── seeder.js                # Database seeder
│   │
│   ├── server.js                     # Express server entry point
│   ├── package.json                  # Backend dependencies
│   ├── vercel.json                   # Vercel deployment config
│   └── README.md                     # Backend documentation
│
└── frontend/                         # React Frontend Application
    ├── public/                       # Static assets
    │
    ├── src/                          # Source code
    │   ├── components/               # React components
    │   │   ├── common/              # Shared components
    │   │   │   ├── LoadingSkeleton.jsx
    │   │   │   └── ProtectedRoute.jsx
    │   │   │
    │   │   ├── layout/              # Layout components
    │   │   │   ├── DashboardLayout.jsx
    │   │   │   ├── Footer.jsx
    │   │   │   ├── Navbar.jsx
    │   │   │   └── Sidebar.jsx
    │   │   │
    │   │   └── ui/                  # UI components (shadcn)
    │   │       ├── alert-dialog.jsx
    │   │       ├── avatar.jsx
    │   │       ├── badge.jsx
    │   │       ├── button.jsx
    │   │       ├── card.jsx
    │   │       ├── checkbox.jsx
    │   │       ├── dialog.jsx
    │   │       ├── dropdown-menu.jsx
    │   │       ├── input.jsx
    │   │       ├── label.jsx
    │   │       ├── select.jsx
    │   │       ├── separator.jsx
    │   │       ├── skeleton.jsx
    │   │       ├── table.jsx
    │   │       ├── tabs.jsx
    │   │       └── textarea.jsx
    │   │
    │   ├── context/                  # React Context providers
    │   │   ├── AuthContext.jsx      # Authentication state
    │   │   └── ThemeContext.jsx     # Theme management
    │   │
    │   ├── lib/                      # Utilities and configurations
    │   │   ├── api.js               # Axios instance & interceptors
    │   │   └── utils.js             # Helper functions
    │   │
    │   ├── pages/                    # Page components
    │   │   ├── Home.jsx             # Landing page
    │   │   ├── Login.jsx            # Login page
    │   │   ├── Register.jsx         # Registration page
    │   │   │
    │   │   ├── admin/               # Admin pages
    │   │   │   ├── Dashboard.jsx
    │   │   │   ├── ManageAdmins.jsx
    │   │   │   ├── ManageEvents.jsx
    │   │   │   ├── ManageNotices.jsx
    │   │   │   ├── ModerateLostFound.jsx
    │   │   │   └── ViewFeedback.jsx
    │   │   │
    │   │   └── student/             # Student pages
    │   │       ├── Dashboard.jsx
    │   │       ├── Events.jsx
    │   │       ├── Feedback.jsx
    │   │       ├── LostFound.jsx
    │   │       └── Notices.jsx
    │   │
    │   ├── App.jsx                   # Main app component with routes
    │   ├── main.jsx                  # React entry point
    │   └── index.css                 # Global styles
    │
    ├── index.html                    # HTML template
    ├── package.json                  # Frontend dependencies
    ├── vite.config.js               # Vite configuration
    ├── tailwind.config.js           # Tailwind configuration
    ├── postcss.config.js            # PostCSS configuration
    ├── jsconfig.json                # JavaScript configuration
    └── README.md                     # Frontend documentation
```

---

## 🗄 Database Schema

### User Model
```javascript
{
  name: String (required),
  email: String (required, unique),
  password: String (required, hashed),
  role: String (enum: ['student', 'admin'], default: 'student'),
  department: String,
  year: String,
  rollNumber: String,
  createdAt: Date,
  updatedAt: Date
}
```

### Notice Model
```javascript
{
  title: String (required),
  content: String (required),
  category: String (enum: ['academic', 'event', 'exam', 'important', 'general']),
  priority: String (enum: ['low', 'medium', 'high']),
  postedBy: ObjectId (ref: 'User'),
  expiresAt: Date,
  isActive: Boolean (default: true),
  createdAt: Date,
  updatedAt: Date
}
```

### Event Model
```javascript
{
  title: String (required),
  description: String (required),
  category: String (enum: ['academic', 'cultural', 'sports', 'technical', 'other']),
  startDate: Date (required),
  endDate: Date,
  location: String,
  organizer: String,
  registrationLink: String,
  maxParticipants: Number,
  createdBy: ObjectId (ref: 'User'),
  isActive: Boolean (default: true),
  createdAt: Date,
  updatedAt: Date
}
```

### LostAndFound Model
```javascript
{
  type: String (enum: ['lost', 'found'], required),
  itemName: String (required),
  description: String (required),
  category: String (enum: ['electronics', 'documents', 'accessories', 'books', 'other']),
  location: String (required),
  date: Date (required),
  contactInfo: String,
  imageUrl: String,
  status: String (enum: ['pending', 'approved', 'rejected'], default: 'pending'),
  isResolved: Boolean (default: false),
  postedBy: ObjectId (ref: 'User'),
  createdAt: Date,
  updatedAt: Date
}
```

### Feedback Model
```javascript
{
  subject: String (required),
  message: String (required),
  category: String (enum: ['general', 'academic', 'infrastructure', 'faculty', 'other']),
  isAnonymous: Boolean (default: false),
  submittedBy: ObjectId (ref: 'User'),
  status: String (enum: ['pending', 'in-review', 'resolved'], default: 'pending'),
  adminNotes: String,
  createdAt: Date,
  updatedAt: Date
}
```

---

## 📡 API Documentation

### Base URL
```
Development: http://localhost:5000/api
Production: https://your-backend-url.vercel.app/api
```

### Authentication Endpoints

#### Register Student
```http
POST /api/auth/register
Content-Type: application/json

Request Body:
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "department": "Computer Science",
  "year": "Third Year",
  "rollNumber": "CS2021001"
}

Response: 200 OK
{
  "success": true,
  "token": "jwt_token_here",
  "user": {
    "id": "user_id",
    "name": "John Doe",
    "email": "john@example.com",
    "role": "student"
  }
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

Request Body:
{
  "email": "admin@college.com",
  "password": "admin123"
}

Response: 200 OK
{
  "success": true,
  "token": "jwt_token_here",
  "user": {
    "id": "user_id",
    "name": "Admin",
    "email": "admin@college.com",
    "role": "admin"
  }
}
```

#### Get Current User
```http
GET /api/auth/me
Authorization: Bearer <token>

Response: 200 OK
{
  "success": true,
  "user": {
    "id": "user_id",
    "name": "John Doe",
    "email": "john@example.com",
    "role": "student"
  }
}
```

### Notice Endpoints

#### Get All Notices
```http
GET /api/notices
Query Parameters:
  - category: string (optional)
  - priority: string (optional)
  - page: number (default: 1)
  - limit: number (default: 10)

Response: 200 OK
{
  "success": true,
  "count": 10,
  "data": [...]
}
```

#### Create Notice (Admin Only)
```http
POST /api/notices
Authorization: Bearer <admin_token>
Content-Type: application/json

Request Body:
{
  "title": "Mid-term Exams Schedule",
  "content": "Exams will begin from...",
  "category": "exam",
  "priority": "high",
  "expiresAt": "2025-12-31"
}

Response: 201 Created
```

#### Update Notice (Admin Only)
```http
PUT /api/notices/:id
Authorization: Bearer <admin_token>
```

#### Delete Notice (Admin Only)
```http
DELETE /api/notices/:id
Authorization: Bearer <admin_token>
```

### Event Endpoints

#### Get All Events
```http
GET /api/events
Query Parameters:
  - category: string (optional)
  - upcoming: boolean (optional)
```

#### Get Upcoming Events
```http
GET /api/events/upcoming
```

#### Create Event (Admin Only)
```http
POST /api/events
Authorization: Bearer <admin_token>
Content-Type: application/json

Request Body:
{
  "title": "Tech Fest 2025",
  "description": "Annual technical festival",
  "category": "technical",
  "startDate": "2025-03-15",
  "endDate": "2025-03-17",
  "location": "Main Auditorium",
  "organizer": "Tech Club",
  "maxParticipants": 500
}
```

#### Update Event (Admin Only)
```http
PUT /api/events/:id
Authorization: Bearer <admin_token>
```

#### Delete Event (Admin Only)
```http
DELETE /api/events/:id
Authorization: Bearer <admin_token>
```

### Lost & Found Endpoints

#### Get Approved Posts
```http
GET /api/lostfound
Query Parameters:
  - type: string (lost/found)
  - category: string
  - status: string
```

#### Get User's Posts
```http
GET /api/lostfound/my-posts
Authorization: Bearer <token>
```

#### Create Post
```http
POST /api/lostfound
Authorization: Bearer <token>
Content-Type: application/json

Request Body:
{
  "type": "lost",
  "itemName": "iPhone 13",
  "description": "Black iPhone with blue case",
  "category": "electronics",
  "location": "Library",
  "date": "2025-12-20",
  "contactInfo": "9876543210"
}
```

#### Approve Post (Admin Only)
```http
PATCH /api/lostfound/:id/approve
Authorization: Bearer <admin_token>
```

#### Reject Post (Admin Only)
```http
PATCH /api/lostfound/:id/reject
Authorization: Bearer <admin_token>
```

### Feedback Endpoints

#### Get All Feedback (Admin Only)
```http
GET /api/feedback
Authorization: Bearer <admin_token>
Query Parameters:
  - category: string
  - status: string
```

#### Submit Feedback
```http
POST /api/feedback
Authorization: Bearer <token>
Content-Type: application/json

Request Body:
{
  "subject": "Library Timing",
  "message": "Please extend library hours",
  "category": "infrastructure",
  "isAnonymous": false
}
```

#### Mark as Resolved (Admin Only)
```http
PATCH /api/feedback/:id/resolve
Authorization: Bearer <admin_token>
```

### Statistics Endpoints

#### Get Dashboard Stats
```http
GET /api/stats/dashboard
Authorization: Bearer <token>

Response: 200 OK
{
  "success": true,
  "stats": {
    "totalUsers": 150,
    "totalNotices": 25,
    "totalEvents": 12,
    "totalFeedback": 45,
    "pendingApprovals": 5
  }
}
```

---

## 🎨 Frontend Components

### Context Providers

#### AuthContext
- Manages authentication state
- Provides login, logout, register functions
- Stores user information and JWT token
- Protected route access control

#### ThemeContext
- Manages light/dark theme
- Persists theme preference in localStorage
- Provides theme toggle functionality

### Common Components

#### LoadingSkeleton
- Displays loading placeholders
- Used during data fetching

#### ProtectedRoute
- Wraps protected pages
- Redirects unauthorized users
- Role-based access control

### Layout Components

#### DashboardLayout
- Main layout wrapper for dashboard pages
- Includes sidebar and navbar
- Responsive design

#### Navbar
- Top navigation bar
- User profile dropdown
- Theme toggle
- Logout functionality

#### Sidebar
- Navigation menu
- Role-based menu items
- Active route highlighting

#### Footer
- Application footer
- Copyright information
- Links

### UI Components (shadcn/ui)
All UI components are based on Radix UI primitives and styled with Tailwind CSS:
- Buttons, Inputs, Textareas
- Cards, Badges, Avatars
- Dialogs, Alert Dialogs
- Dropdowns, Select menus
- Tables, Tabs
- Skeletons for loading states

---

## 🚀 Setup & Installation

### Prerequisites
- Node.js (v18 or higher)
- MongoDB (local installation or cloud instance like MongoDB Atlas)
- Git
- npm or yarn package manager

### Step 1: Clone Repository
```bash
git clone <repository-url>
cd college-utility-hub
```

### Step 2: Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment variables file
# Create a .env file in the backend directory with the following:
```

**Backend .env file:**
```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/college-utility-hub
# OR for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/college-utility-hub

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here_change_in_production
JWT_EXPIRE=7d

# CORS (optional, for production)
CLIENT_URL=http://localhost:5173
```

```bash
# Seed default admin account
npm run seed

# Start development server
npm run dev

# Server will run on http://localhost:5000
```

### Step 3: Frontend Setup

```bash
# Open new terminal and navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Create environment variables file
# Create a .env file in the frontend directory with the following:
```

**Frontend .env file:**
```env
# API Configuration
VITE_API_URL=http://localhost:5000/api
```

```bash
# Start development server
npm run dev

# Application will run on http://localhost:5173
```

### Step 4: Access the Application

1. Open browser and navigate to `http://localhost:5173`
2. Use default admin credentials to login:
   - Email: `admin@college.com`
   - Password: `admin123`
3. Students can register through the registration page

---

## 🔐 Environment Variables

### Backend Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `PORT` | Server port number | `5000` |
| `NODE_ENV` | Environment mode | `development` or `production` |
| `MONGODB_URI` | MongoDB connection string | `mongodb://localhost:27017/college-utility-hub` |
| `JWT_SECRET` | Secret key for JWT signing | `your_secret_key` |
| `JWT_EXPIRE` | JWT token expiration time | `7d` |
| `CLIENT_URL` | Frontend URL (for CORS) | `http://localhost:5173` |

### Frontend Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_API_URL` | Backend API base URL | `http://localhost:5000/api` |

---

## 📜 Scripts

### Backend Scripts

```json
{
  "start": "node server.js",          // Production server
  "dev": "nodemon server.js",         // Development server with auto-reload
  "seed": "node utils/seeder.js"      // Seed database with admin user
}
```

### Frontend Scripts

```json
{
  "dev": "vite",                      // Start development server
  "build": "vite build",              // Build for production
  "lint": "eslint .",                 // Lint code
  "preview": "vite preview"           // Preview production build
}
```

---

## 🌐 Deployment

### Backend Deployment (Vercel)

1. **Install Vercel CLI**
```bash
npm install -g vercel
```

2. **Configure vercel.json** (already included in project)
```json
{
  "version": 2,
  "builds": [
    {
      "src": "server.js",
      "use": "@vercel/node"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "server.js"
    }
  ]
}
```

3. **Deploy**
```bash
cd backend
vercel --prod
```

4. **Set Environment Variables in Vercel Dashboard**
- Go to your Vercel project settings
- Add all environment variables from .env file

### Frontend Deployment (Vercel)

1. **Build the application**
```bash
cd frontend
npm run build
```

2. **Deploy to Vercel**
```bash
vercel --prod
```

3. **Update Environment Variables**
- Update `VITE_API_URL` to point to deployed backend URL

### Alternative Deployment Options

#### Backend
- **Heroku**: Push to Heroku with Procfile
- **AWS EC2**: Deploy on EC2 instance
- **DigitalOcean**: Deploy on droplet
- **Railway**: One-click deployment

#### Frontend
- **Netlify**: Drag and drop or Git integration
- **GitHub Pages**: Static hosting
- **AWS S3 + CloudFront**: Scalable hosting

---

## 🔒 Security Features

### Implemented Security Measures

1. **Authentication & Authorization**
   - JWT-based authentication
   - Password hashing with bcryptjs (10 salt rounds)
   - Protected routes with middleware
   - Role-based access control (RBAC)

2. **Data Validation**
   - Input validation using express-validator
   - Schema validation with Mongoose
   - XSS prevention through sanitization

3. **HTTP Security**
   - CORS configured with whitelisted origins
   - Preflight request handling
   - Secure HTTP headers

4. **Error Handling**
   - Centralized error handling middleware
   - Sanitized error messages in production
   - Detailed error logs for debugging

5. **Database Security**
   - MongoDB injection prevention
   - Secure connection strings
   - Environment-based credentials

### Best Practices Implemented

- ✅ Passwords never stored in plain text
- ✅ JWT tokens stored in HTTP-only cookies (frontend uses localStorage with caution)
- ✅ Sensitive data excluded from API responses
- ✅ Rate limiting can be added (recommended for production)
- ✅ Environment variables for sensitive configuration
- ✅ Input sanitization and validation
- ✅ Proper error handling without exposing internal details

---

## 👥 Default Credentials

### Admin Account
- **Email**: `admin@college.com`
- **Password**: `admin123`
- **Role**: Administrator

> ⚠️ **Important**: Change the default admin password immediately after first login in production!

### Student Accounts
Students must register through the application's registration page. There are no default student accounts.

---

## 🔄 API Response Format

### Success Response
```json
{
  "success": true,
  "data": { ... },
  "message": "Operation successful"
}
```

### Error Response
```json
{
  "success": false,
  "error": "Error message",
  "statusCode": 400
}
```

### Paginated Response
```json
{
  "success": true,
  "count": 50,
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 50
  },
  "data": [...]
}
```

---

## 🎯 Key Features Implementation

### Notice Board
- CRUD operations for notices
- Category-based filtering (academic, event, exam, important, general)
- Priority levels (low, medium, high)
- Expiration dates for auto-archival
- Admin-only creation and management

### Event Management
- Event creation with detailed information
- Date range for multi-day events
- Category classification
- Location and organizer details
- Participant capacity tracking
- Upcoming events filter

### Lost & Found
- Two-way system (lost items and found items)
- Image upload support
- Approval workflow for moderation
- Contact information for recovery
- Status tracking (pending, approved, rejected)
- Resolution marking

### Feedback System
- Anonymous and named feedback options
- Category-based classification
- Status tracking (pending, in-review, resolved)
- Admin notes for internal communication
- Privacy-protected submission

### Dashboard Statistics
- Total counts for all entities
- Recent activity tracking
- Pending items highlighting
- Role-specific dashboards

---

## 📱 Responsive Design

The application is fully responsive and works seamlessly on:
- 📱 Mobile devices (320px+)
- 📱 Tablets (768px+)
- 💻 Laptops (1024px+)
- 🖥️ Desktops (1280px+)

Responsive features:
- Mobile-first design approach
- Hamburger menu for navigation on small screens
- Responsive tables with horizontal scroll
- Adaptive layouts using Tailwind's responsive utilities
- Touch-friendly UI elements

---

## 🎨 Styling & Theming

### Tailwind CSS Configuration
- Custom color palette
- Extended spacing and sizing
- Custom animations
- Responsive breakpoints

### Theme Support
- Light mode (default)
- Dark mode support
- Persistent theme preference
- System theme detection

### shadcn/ui Components
Pre-styled, accessible components built on:
- Radix UI primitives
- Tailwind CSS utility classes
- Customizable through CSS variables
- Full keyboard navigation support

---

## 🧪 Testing Recommendations

### Backend Testing (To Implement)
- Unit tests with Jest/Mocha
- Integration tests for API endpoints
- Database tests with test database
- Authentication flow tests

### Frontend Testing (To Implement)
- Component tests with React Testing Library
- E2E tests with Playwright/Cypress
- Accessibility tests
- Snapshot tests for UI consistency

---

## 🐛 Error Handling

### Backend Error Types
1. **Validation Errors** (400): Invalid input data
2. **Authentication Errors** (401): Invalid or missing token
3. **Authorization Errors** (403): Insufficient permissions
4. **Not Found Errors** (404): Resource not found
5. **Server Errors** (500): Internal server errors

### Frontend Error Handling
- Toast notifications for user feedback
- Form validation errors
- Network error handling
- Retry mechanisms for failed requests
- Fallback UI for errors

---

## 📊 Database Relationships

```
User (1) ──────┬───────> (N) Notice
               ├───────> (N) Event
               ├───────> (N) LostAndFound
               └───────> (N) Feedback

Legend:
1 = One
N = Many
```

### Relationships Explained
- **User → Notices**: One admin can create many notices
- **User → Events**: One admin can create many events
- **User → LostAndFound**: One user can post many lost/found items
- **User → Feedback**: One user can submit many feedbacks

---

## 🔍 Additional Features

### Planned/Future Enhancements
- [ ] Email notifications for important notices
- [ ] Push notifications for mobile
- [ ] File upload for notices and events
- [ ] Advanced search and filtering
- [ ] Export data to CSV/PDF
- [ ] Analytics dashboard with charts
- [ ] Chat/messaging system
- [ ] Calendar integration
- [ ] SMS notifications
- [ ] Multi-language support

---

## 📞 Support & Contact

For issues, questions, or contributions:
- Create an issue in the repository
- Contact the development team
- Check documentation and README files

---

## 📄 License

Feel free to use this project for educational purposes.

---

## 👨‍💻 Development Team

This project was developed as a college utility management system to demonstrate full-stack development capabilities using modern web technologies.

---

## 🎉 Acknowledgments

- **shadcn/ui** for beautiful UI components
- **Radix UI** for accessible primitives
- **Tailwind CSS** for utility-first styling
- **Vercel** for hosting and deployment
- **MongoDB** for database
- **Express.js** community for excellent framework

---

**Last Updated**: December 23, 2025

**Version**: 1.0.0

---

## Quick Commands Reference

```bash
# Backend
cd backend
npm install
npm run seed      # Create admin user
npm run dev       # Start dev server

# Frontend
cd frontend
npm install
npm run dev       # Start dev server

# Both
npm run build     # Build for production
```

---

**Happy Coding! 🚀**
