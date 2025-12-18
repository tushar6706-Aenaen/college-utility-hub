# College Utility Hub

A comprehensive full-stack web application for managing college utilities including notices, events, lost & found items, and feedback.

## Features

- **Notice Board**: Post and view college announcements with categories
- **Event Management**: Manage and browse upcoming events
- **Lost & Found**: Report and search for lost/found items with approval workflow
- **Feedback System**: Submit and manage anonymous/named feedback
- **Role-based Access**: Separate portals for students and administrators

## Tech Stack

### Backend
- Node.js + Express.js
- MongoDB with Mongoose
- JWT Authentication
- bcryptjs for password hashing
- express-validator for validation

### Frontend
- React 18 with Vite
- Tailwind CSS
- shadcn/ui components
- React Router DOM
- React Hook Form
- Axios

## Project Structure

```
college-utility-hub/
├── backend/           # Node.js API server
│   ├── config/        # Database configuration
│   ├── controllers/   # Route controllers
│   ├── middleware/    # Custom middleware
│   ├── models/        # Mongoose models
│   ├── routes/        # API routes
│   └── utils/         # Utilities
│
└── frontend/          # React application
    ├── src/
    │   ├── components/
    │   ├── context/
    │   ├── lib/
    │   └── pages/
    └── public/
```

## Quick Start

### Prerequisites
- Node.js (v18+)
- MongoDB (running locally or cloud instance)

### Backend Setup

```bash
cd backend
npm install

# Create .env file
# PORT=**
# MONGODB_URI=Your_mongo_uri
# JWT_SECRET=""
# JWT_EXPIRE=""
# NODE_ENV=""

# Seed default admin
npm run seed

# Start server
npm run dev
```

### Frontend Setup

```bash
cd frontend
npm install

# Create .env file
# VITE_API_URL=""

# Start development server
npm run dev
```

## Default Credentials
 
As you wish

Students can register through the application.

