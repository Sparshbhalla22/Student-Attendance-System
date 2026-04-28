# 🎓 EduTrack: Smart Attendance & Analytics System

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

A production-ready full-stack web application designed for educational institutions to manage student attendance, organize courses, share documents, and generate predictive AI insights to identify at-risk students.

---

## ✨ Features

- **🔒 Role-Based Access Control (RBAC):** Secure JWT authentication with strict authorization handling for Admins, Teachers, and Students.
- **📊 Advanced Dashboard:** Interactive overview featuring Recharts-based statistics and visual attendance trends.
- **📝 Attendance Module:** Real-time present, absent, and late tracking. Instantly saves data without page reloads. Includes CSV Export functionality.
- **📚 Course Management:** Dynamic course creation, faculty assignment, and seamless student enrollment.
- **🧠 AI Analytics:** Predicts at-risk students falling below minimum attendance thresholds (75%) using trend analysis, ensuring early intervention.
- **🧑‍🎓 Student Portal:** Dedicated view for students to monitor their own attendance history and status.
- **📁 Document Sharing:** Secure file upload/download system for course materials using Multer.
- **🎨 Modern UI/UX:** Built with Tailwind CSS v4, Lucide icons, and a highly responsive layout.

## 🛠️ Tech Stack

- **Frontend:** React (Vite), Tailwind CSS, Recharts, Axios, React Router, Lucide React
- **Backend:** Node.js, Express.js, MongoDB (Mongoose), JSON Web Tokens (JWT), Bcrypt.js, Multer

---

## 🚀 Getting Started

### 1. Prerequisites
- [Node.js](https://nodejs.org/) (v16+)
- [MongoDB](https://www.mongodb.com/) (Running locally or via MongoDB Atlas)

### 2. Backend Setup
1. Clone the repository and navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `backend/` directory:
   ```env
   MONGO_URI=mongodb://127.0.0.1:27017/edutrack
   PORT=5000
   JWT_SECRET=supersecretjwtkey123
   ```
4. Seed the database with sample data (creates default users and courses):
   ```bash
   npm run data:import
   ```
5. Start the backend server:
   ```bash
   npm run dev
   ```

### 3. Frontend Setup
1. Open a new terminal and navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Vite development server:
   ```bash
   npm run dev
   ```

---

## 🔑 Default Login Credentials
Use these accounts to test the application after running the seeder (`npm run data:import`).

| Role | Email | Password |
|------|-------|----------|
| **Admin** | admin@test.com | password123 |
| **Teacher** | rajesh@test.com | password123 |
| **Student** | aarav@test.com | password123 |

---

## 📡 API Endpoints

### Authentication
- `POST /api/auth/login` - Authenticate user & retrieve token
- `POST /api/auth/register` - Register a new user

### Courses
- `GET /api/courses` - Fetch all courses
- `POST /api/courses` - Create a new course *(Teacher/Admin only)*
- `POST /api/courses/:id/enroll` - Enroll a student *(Teacher/Admin only)*

### Attendance & Students
- `GET /api/students` - Get all registered students *(Teacher/Admin only)*
- `GET /api/students/:id/attendance` - Get attendance history for a specific student
- `GET /api/attendance` - Get attendance records for a specific course and date
- `POST /api/attendance` - Mark or update attendance records *(Teacher/Admin only)*

### Documents
- `GET /api/files` - List all uploaded documents
- `POST /api/files/upload` - Upload a new document *(Teacher/Admin only)*
- `DELETE /api/files/:id` - Delete an uploaded document *(Teacher/Admin only)*

---

## 📂 Project Structure
- `/frontend` - Contains the React Vite SPA.
- `/backend` - Contains the Express REST API, Mongoose Models, Controllers, and Middleware.
- `/uploads` - (Generated automatically) Stores documents uploaded via the platform.

---

## 🌍 Deployment
- **Frontend:** Highly optimized for deployment on [Vercel](https://vercel.com/) or [Netlify](https://www.netlify.com/).
- **Backend:** Easily deployable to [Render](https://render.com/), [Railway](https://railway.app/), or Heroku. Make sure to set up your MongoDB Atlas connection string in the environment variables.

---

## 📝 License
This project is open-source and available under the [MIT License](LICENSE).
