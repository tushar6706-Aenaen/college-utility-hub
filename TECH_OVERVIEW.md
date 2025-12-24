# College Utility Hub - Technical Overview

## 📋 Purpose

College Utility Hub is a full-stack web application that centralizes college utilities and communication. It provides a unified platform for managing notices, events, lost & found items, and feedback with role-based access control for students and administrators.

## 🛠 Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **JWT** - Authentication
- **bcryptjs** - Password hashing

### Frontend
- **React 18** - UI library
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **shadcn/ui** - UI components
- **React Router** - Routing
- **Axios** - HTTP client
- **React Hook Form** - Form handling

## ⚡ Quick Start

### Backend
```bash
cd backend
npm install
npm run seed    # Create admin user
npm run dev     # Start on port 5000
```

### Frontend
```bash
cd frontend
npm install
npm run dev     # Start on port 5173
```


## 🎯 Key Features

- Notice board with categories
- Event management system
- Lost & found with approval workflow
- Anonymous feedback system
- Role-based dashboards (Student/Admin)
- Responsive design

## 📁 Structure

```
├── backend/          # Express API
│   ├── controllers/  # Business logic
│   ├── models/       # Mongoose schemas
│   ├── routes/       # API endpoints
│   └── middleware/   # Auth & validation
│
└── frontend/         # React app
    ├── components/   # UI components
    ├── pages/        # Page components
    └── context/      # State management
```

## 🔐 Security

- JWT authentication
- Password hashing
- Input validation
- Role-based access control
- CORS configuration
