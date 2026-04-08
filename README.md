# MedVault

A web application for managing personal health records. Built with React and Node.js as part of a Web Technology assignment.

## Features

- User authentication (register, login, JWT-based sessions)
- Prescription management with medicine details
- Medicine tracker with daily schedule and take/skip tracking
- Appointment scheduling with status tracking
- Doctor directory
- Vitals monitoring with chart visualization
- Medical document upload and storage
- Family member health profiles
- Emergency medical card with shareable link
- Health report export as PDF
- Notification preferences

## Tech Stack

**Frontend:** React, Vite, React Router, Chart.js, jsPDF, React Toastify, React Icons

**Backend:** Node.js, Express, MongoDB, Mongoose, JWT, Multer, bcryptjs

## Project Structure

```
wt/
├── med-vault/          # React frontend (Vite)
│   └── src/
│       ├── api/        # API client and auth helpers
│       ├── components/ # Layout, Navbar, Sidebar, ProtectedRoute
│       ├── context/    # AuthContext (login state)
│       ├── pages/      # All page components
│       ├── App.jsx     # Router setup
│       └── index.css   # Global styles
├── server/             # Express backend
│   ├── server.js       # API routes and middleware
│   ├── models.js       # Mongoose schemas
│   ├── .env            # Environment variables (not committed)
│   └── uploads/        # Uploaded documents (not committed)
└── README.md
```

## Prerequisites

- Node.js (v18 or later)
- MongoDB (running locally or a cloud instance)

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/Giridhar88/Web-tech-assignment.git
cd Web-tech-assignment
```

### 2. Set up the backend

```bash
cd server
npm install
```

Create a `.env` file in the `server/` directory:

```
PORT=5000
MONGO_URI=mongodb://localhost:27017/medvault
JWT_SECRET=your_secret_key_here
```

Start MongoDB if it is not already running:

```bash
sudo systemctl start mongodb
```

Start the server:

```bash
npm run dev
```

The API will be available at `http://localhost:5000`.

### 3. Set up the frontend

Open a new terminal:

```bash
cd med-vault
npm install
npm run dev
```

The app will be available at `http://localhost:5173`.

## API Endpoints

| Method | Endpoint                     | Description              |
|--------|------------------------------|--------------------------|
| POST   | /api/auth/register           | Register a new user      |
| POST   | /api/auth/login              | Login                    |
| GET    | /api/auth/me                 | Get current user         |
| PUT    | /api/auth/profile            | Update profile           |
| GET    | /api/prescriptions           | List prescriptions       |
| POST   | /api/prescriptions           | Add prescription         |
| PUT    | /api/prescriptions/:id       | Update prescription      |
| DELETE | /api/prescriptions/:id       | Delete prescription      |
| GET    | /api/medicines               | List medicines           |
| POST   | /api/medicines               | Add medicine             |
| POST   | /api/medicines/:id/take      | Mark medicine as taken   |
| GET    | /api/appointments            | List appointments        |
| POST   | /api/appointments            | Add appointment          |
| GET    | /api/doctors                 | List doctors             |
| POST   | /api/doctors                 | Add doctor               |
| GET    | /api/vitals                  | List vitals              |
| POST   | /api/vitals                  | Record vital             |
| GET    | /api/documents               | List documents           |
| POST   | /api/documents               | Upload document          |
| GET    | /api/family                  | List family members      |
| POST   | /api/family                  | Add family member        |
| GET    | /api/emergency               | Get emergency card       |
| PUT    | /api/emergency               | Update emergency card    |
| GET    | /api/dashboard/summary       | Dashboard stats          |
| GET    | /api/export/health-report    | Export all health data   |
