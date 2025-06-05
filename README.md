
# Mango Medical Group – Admin Dashboard

The Mango Medical Admin Dashboard allows healthcare providers to manage appointments, view patient messages, and respond in real-time. This web application is built with Flask (Python) for the backend and vanilla HTML/CSS/JS for the frontend.

---

## Features

- Secure admin login using JWT
- Dashboard showing:
  - Total appointments
  - Urgent cases
  - Completed cases
  - **Today’s Appointments** table with all relevant details
- Filterable appointment messages by priority (High, Moderate, Low)
- Inline response functionality per appointment
- Displays logged-in admin's name and initials dynamically

---

## ⚙️ Tech Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Python Flask
- **Database**: MySQL
- **Auth**: JWT (via flask-jwt-extended)
- **Others**: PyMySQL, CORS, Werkzeug

---

##  Setup Guide

1. **Clone and Navigate**
   ```
   cd mango-medical-dashboard
   ```

2. **Backend Setup**
   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   python app.py
   ```

3. **Database Setup**
   - Create a MySQL database named `Mango`
   - Ensure required tables exist (`users`, `appointments`, `specialties`, etc.)

4. **Frontend**
   - Access `http://127.0.0.1:5000/admin` to view the admin dashboard
   - Static files are located under `/static`

---

## Authentication

- On login, JWT is saved in `localStorage`
- All protected API routes use `Authorization: Bearer <token>`

---

## Key API Endpoints

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/login` | POST | Admin login |
| `/register` | POST | Register admin/patient |
| `/api/admin/stats` | GET | Dashboard metrics |
| `/api/admin/messages` | GET | All assigned messages |
| `/api/admin/respond` | POST | Submit response to patient |
| `/api/admin/today_appointments_detail` | GET | List of today’s appointments |

---
