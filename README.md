📌 PHASE 1: INITIAL SETUP (Both Sides)

STEP 1: Create a GitHub Repo
Create a repo called promanage-fullstack (or two separate repos: promanage-frontend and promanage-backend)

STEP 2: Initialize Backend Project

Create backend folder:
mkdir promanage-backend && cd promanage-backend

Initialize Node:
npm init -y

Install base dependencies:
npm install express mysql2 sequelize dotenv cors

Install dev tools:
npm install --save-dev nodemon

Setup Sequelize:
npx sequelize-cli init

Create MySQL DB: promanage_dev (via phpMyAdmin or MySQL CLI)

Set up .env file for DB config

STEP 3: Initialize Frontend Project

Create frontend folder:
npx create-react-app promanage-frontend

Install tools:
npm install axios react-router-dom react-icons

Setup base folder structure: /components, /pages, /api, /contexts

───────────────────────────────────────

📌 PHASE 2: USER AUTHENTICATION (Frontend + Backend)

BACKEND:

Create User model (Sequelize): name, email, password, role

Add bcrypt for password hashing

Setup JWT auth (access + refresh tokens)

Create login, register APIs

Add auth middleware to protect routes

FRONTEND:

Create login and register pages

Use Axios to call backend

Store JWT (preferably in memory or localStorage)

Setup React Context for global auth state

Protect dashboard route using a PrivateRoute component

Concepts covered:

JWT authentication

Protected routes

React Context

Form handling + validation

───────────────────────────────────────

📌 PHASE 3: USERS, TEAMS, ROLES (RBAC)

BACKEND:

Create Team model

Many-to-many: Users ↔ Teams

Create TeamMember join table

Implement role-based access (Admin, Team Lead, Member)

APIs: create/join/leave team, list team members

FRONTEND:

Team creation form

Show teams user belongs to

Show/hide UI by role

Add role-based guards on frontend

Concepts covered:

MySQL associations (Sequelize)

Role-based access control (RBAC)

React conditional rendering

───────────────────────────────────────

📌 PHASE 4: PROJECTS & TASKS

BACKEND:

Create Project and Task models

Relationships:

Team → Projects (1:m)

Project → Tasks (1:m)

Task → User (assignedTo)

CRUD APIs for Projects and Tasks

Add search, filter, pagination

FRONTEND:

Project list page

Task board (Kanban-style)

Assign task to users

Pagination and filter UI

Concepts covered:

React state and props

CRUD operations

Pagination and filtering

Nested routes and dynamic routing

───────────────────────────────────────

📌 PHASE 5: FILE UPLOADS & COMMENTS

BACKEND:

Add Multer for file upload

Attachments linked to tasks

Comments model: Task ↔ User

APIs: Upload file, post comment, list comments

FRONTEND:

File upload UI

Comments section under each task

Preview/download attachments

Concepts covered:

File uploads (Multer)

useRef for file inputs

FormData handling in React

───────────────────────────────────────

📌 PHASE 6: REAL-TIME UPDATES (Socket.io)

BACKEND:

Install socket.io

Emit events on task updates, new comments

FRONTEND:

Connect to socket server

Listen for task updates or comments

Update UI live without reload

Concepts covered:

WebSockets (Socket.io)

useEffect for subscriptions

Real-time data flow

───────────────────────────────────────

📌 PHASE 7: ERROR HANDLING, LOGGING, SECURITY

BACKEND:

Global error handler

Winston for logging

Helmet, CORS, input validation (Joi)

FRONTEND:

Show toast messages for API errors

Form validation

Error boundaries (React)

Concepts covered:

Centralized error handling

Secure headers

Client-side feedback

───────────────────────────────────────

📌 PHASE 8: TESTING

BACKEND:

Install Jest + Supertest

Write tests for auth, task APIs

FRONTEND:

React Testing Library

Test login form, task form, API mocking

Concepts covered:

Unit and integration tests

Mocking API calls

───────────────────────────────────────

📌 PHASE 9: DEPLOYMENT

BACKEND:

Host on Render or Railway

Use PM2 for production

Use .env variables

FRONTEND:

Build and deploy to Netlify or Vercel

Connect to backend via env variables

Concepts covered:

Environment management

Deployment and CI basics

───────────────────────────────────────
