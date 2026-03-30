# Full-Stack Authentication Learning Project

This workspace now contains a beginner-friendly authentication system with:

- Frontend: React + Tailwind CSS
- Backend: Node.js + Express
- Database: MySQL
- Security: bcrypt password hashing + JWT

The old static HTML files are still present at the root for reference, but the active learning project is inside `frontend/` and `backend/`.

## Project Structure

```
Intern-Assignment/
├── frontend/                 # React + Tailwind app
├── backend/                  # Express + MySQL API
├── index.html                # legacy static file
├── register.html             # legacy static file
├── forgot-password.html      # legacy static file
├── reset-password.html       # legacy static file
├── dashboard.html            # legacy static file
├── styles.css                # legacy static file
└── README.md
```

## Frontend Pages

Inside `frontend/src/pages/`:

1. `LoginPage.jsx`
2. `RegisterPage.jsx`
3. `ForgotPasswordPage.jsx`
4. `ResetPasswordPage.jsx`

Navigation is included between Login, Register, and Forgot Password.

## Backend APIs

Inside `backend/src/server.js`:

- `POST /register`
- `POST /login`
- `POST /forgot-password`
- `POST /reset-password`

## Database Setup (MySQL)

1. Create database and tables using `backend/schema.sql`.
2. Example command:

```sql
SOURCE path/to/Intern-Assignment/backend/schema.sql;
```

## Environment Variables

### Backend

1. Go to `backend/`.
2. Copy `.env.example` to `.env`.
3. Update MySQL credentials and JWT secret.

### Frontend

1. Go to `frontend/`.
2. Copy `.env.example` to `.env`.
3. Keep `VITE_API_BASE_URL=http://localhost:5000` (default local backend URL).

## Run Locally

Open two terminals.

### Terminal 1: Backend

```bash
cd backend
npm install
npm run dev
```

Backend runs on `http://localhost:5000`.

### Terminal 2: Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on `http://localhost:5173`.

## Learning Notes

- Passwords are hashed using `bcryptjs` before storing.
- JWT token is returned on register/login.
- Forgot password generates a reset link.
- If SMTP is not configured, reset link is printed in backend console (mock email mode).
- Reset password verifies token and updates hashed password.

## Quick API Examples

### Register

```json
POST /register
{
    "name": "Jayanth",
    "email": "jayanth@example.com",
    "password": "secret123"
}
```

### Login

```json
POST /login
{
    "email": "jayanth@example.com",
    "password": "secret123"
}
```

### Forgot Password

```json
POST /forgot-password
{
    "email": "jayanth@example.com"
}
```

### Reset Password

```json
POST /reset-password
{
    "token": "<reset-token>",
    "newPassword": "newsecret123"
}
```
