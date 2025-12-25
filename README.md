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
# PORT=5000
# MONGODB_URI=mongodb://localhost:27017/college-utility-hub
# JWT_SECRET=your_secret_key
# JWT_EXPIRE=7d
# NODE_ENV=development

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
# VITE_API_URL=http://localhost:5000/api

# Start development server
npm run dev
```



Students can register through the application.

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register student
- `POST /api/auth/login` - Login
- `GET /api/auth/me` - Get current user
- `POST /api/auth/logout` - Logout

### Notices
- `GET /api/notices` - Get all notices
- `POST /api/notices` - Create notice (admin)
- `PUT /api/notices/:id` - Update notice (admin)
- `DELETE /api/notices/:id` - Delete notice (admin)

### Events
- `GET /api/events` - Get all events
- `GET /api/events/upcoming` - Get upcoming events
- `POST /api/events` - Create event (admin)
- `PUT /api/events/:id` - Update event (admin)
- `DELETE /api/events/:id` - Delete event (admin)

### Lost & Found
- `GET /api/lostfound` - Get approved posts
- `GET /api/lostfound/my-posts` - Get user's posts
- `POST /api/lostfound` - Create post
- `PATCH /api/lostfound/:id/approve` - Approve post (admin)
- `PATCH /api/lostfound/:id/reject` - Reject post (admin)

### Feedback
- `GET /api/feedback` - Get all feedback (admin)
- `POST /api/feedback` - Submit feedback
- `PATCH /api/feedback/:id/resolve` - Mark resolved (admin)

## Screenshots

The application features:
- Beautiful landing page with feature overview
- Secure login and registration forms
- Dashboard with statistics and quick actions
- Responsive design for mobile and desktop

## License

MIT

