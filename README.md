# Online Exam Portal

A full-stack web application designed for conducting online exams and assessments, featuring dedicated interfaces for Administrators, Teachers, and Students.

---

## Overview

The repository consists of three components:

- **Backend (`/backend`)**: Node.js & Express REST API with MongoDB. Handles JWT authentication, question and exam scheduling logic, automated scoring, and user role management.
- **Admin Portal (`/frontend`)**: React dashboard for administrators to oversee subjects, teachers, and platform configurations.
- **User Portal (`/user-portal-frontend`)**: React application for teachers (question bank creation, exam configuration) and students (taking tests and reviewing results).

---

## Features

### Student
- Browse upcoming and available tests
- Register and take timed MCQ assessments
- Immediate results upon submission with explanations and answer keys

### Teacher
- Question bank management (create, update, organize questions by subject)
- Create and schedule exams with custom duration, passing marks, and question sets
- View test submissions and student performance

### Admin
- Manage teacher accounts and access permissions
- Create and manage subjects / course categories
- Platform monitoring and user administration

---

## Tech Stack

- **Frontend**: React.js, Redux, Material-UI, Axios
- **Backend**: Node.js, Express.js, Passport.js (JWT & Local Strategy), Mongoose
- **Database**: MongoDB
- **DevOps**: Docker & Docker Compose

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v16 or newer recommended)
- [MongoDB](https://www.mongodb.com/) running locally on port `27017` (or use Docker)

---

### Local Setup

1. **Clone the repo:**
   ```bash
   git clone https://github.com/kaustubh-28/online-exam-portal.git
   cd online-exam-portal
   ```

2. **Configure environment settings:**
   Check `backend/config/default.json` and adjust the MongoDB connection string or JWT secret if needed:
   ```json
   {
     "mongodb": {
       "connectionString": "mongodb://localhost:27017/Online-Exam-Portal"
     },
     "jwt": {
       "secret": "your_jwt_secret"
     }
   }
   ```

3. **Install dependencies:**
   ```bash
   # Backend
   cd backend && npm install

   # Admin frontend
   cd ../frontend && npm install

   # Student & Teacher user portal
   cd ../user-portal-frontend && npm install
   ```

4. **Run the services:**
   Open three terminal tabs and start each service:

   ```bash
   # Terminal 1: Backend API (runs on port 5000)
   cd backend
   npm start

   # Terminal 2: Admin Portal (runs on port 3000)
   cd frontend
   npm start

   # Terminal 3: User Portal (runs on port 3001)
   cd user-portal-frontend
   npm start
   ```

> **Default Admin Account**:
> On initial backend start, a default administrator is seeded automatically:
> - **Username**: `sysadmin`
> - **Password**: `systemadmin`
>
> *(Configured in `backend/services/admin.js` via `addAdminIfNotFound()`)*

---

### Running with Docker

To build and run all services (MongoDB, Mongo Express, Backend, Admin UI, User UI) together:

```bash
docker-compose up --build
```

Default container ports:
- **Backend API**: `http://localhost:5000`
- **Admin Frontend**: `http://localhost:3100`
- **User Frontend**: `http://localhost:3200`
- **Mongo Express GUI**: `http://localhost:8080`

---

## Author

- **Kaustubh Srivastava**
- GitHub: [@kaustubh-28](https://github.com/kaustubh-28)
- Email: kaustubh282.s@gmail.com

---

## License

This project is licensed under the [MIT License](LICENSE).
