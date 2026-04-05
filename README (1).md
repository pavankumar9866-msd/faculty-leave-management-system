# 🎓 Faculty Leave Management System

A full-stack web application for managing faculty leave requests with admin approval workflow, email notifications, and a leave calendar.

---

## 📁 Project Structure

```
faculty-leave-system/
├── backend/                  # Node.js + Express API
│   ├── config/
│   │   └── db.js             # MySQL database connection
│   ├── middleware/
│   │   └── auth.js           # JWT authentication middleware
│   ├── routes/
│   │   ├── auth.js           # Login, register, password reset
│   │   ├── faculty.js        # Faculty leave operations
│   │   └── admin.js          # Admin approval operations
│   ├── utils/
│   │   └── email.js          # Nodemailer email utility
│   ├── server.js             # Main Express server
│   ├── package.json
│   └── .env.example          # Environment variable template
├── frontend/                 # HTML + CSS + JS frontend
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   ├── auth.js           # Auth helpers & API fetch wrapper
│   │   └── EmailService.js
│   ├── index.html            # Login page
│   ├── register.html
│   ├── faculty-dashboard.html
│   ├── admin-dashboard.html
│   ├── apply-leave.html
│   ├── leave-calendar.html   # Admin leave calendar view
│   ├── leave-history.html
│   ├── leave-status.html
│   ├── forgot-password.html
│   └── reset-password.html
└── database/
    └── schema.sql            # MySQL database schema
```

---

## 🚀 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/faculty-leave-system.git
cd faculty-leave-system
```

### 2. Set Up the Database

- Open MySQL and run the schema:

```sql
source database/schema.sql;
```

### 3. Configure the Backend

```bash
cd backend
cp .env.example .env
```

Edit `.env` with your actual values:
- Database credentials
- JWT secret key
- Gmail email & app password

### 4. Install Dependencies & Start Server

```bash
cd backend
npm install
npm start
```

Server runs on: `http://localhost:5000`

### 5. Open the Frontend

Open `frontend/index.html` in your browser **via a Live Server** (e.g., VS Code Live Server extension).

> ⚠️ Do NOT open HTML files by double-clicking. Use Live Server at `http://localhost:5500`

---

## 🔧 Tech Stack

- **Frontend:** HTML, CSS, JavaScript (Vanilla)
- **Backend:** Node.js, Express.js
- **Database:** MySQL (mysql2)
- **Authentication:** JWT (jsonwebtoken) + bcrypt
- **Email:** Nodemailer (Gmail SMTP)

---

## 👤 Default Roles

- **Faculty** — Apply for leave, view history & status
- **Admin** — Approve/reject leaves, view leave calendar

---

## 📧 Email Features

- Admin gets notified when a faculty applies for leave
- Faculty gets notified when their leave is approved/rejected
- Password reset via email OTP

---

## ⚙️ Environment Variables

| Variable | Description |
|----------|-------------|
| `DB_HOST` | MySQL host (usually `localhost`) |
| `DB_USER` | MySQL username |
| `DB_PASSWORD` | MySQL password |
| `DB_NAME` | Database name |
| `JWT_SECRET` | Secret key for JWT tokens |
| `PORT` | Backend server port (default: 5000) |
| `EMAIL_USER` | Gmail address for sending emails |
| `EMAIL_PASS` | Gmail App Password |
| `FRONTEND_URL` | Frontend URL for email links |
