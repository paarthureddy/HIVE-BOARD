### 💻 GitHub Repositories

* Frontend → [https://github.com/paarthureddy/-HiveBoard-Frontend](https://github.com/paarthureddy/-HiveBoard-Frontend)
* Backend → [https://github.com/paarthureddy/HiveBoard-Backend](https://github.com/paarthureddy/HiveBoard-Backend)

---

# 🐝 HiveBoard

**HiveBoard** is a real-time collaborative whiteboard and meeting platform designed for seamless team interactions.
It provides intuitive drawing tools, real-time collaboration, live chat, analytics, AI-powered features, and secure authentication.

---

# 🌐 Live Application & Repositories

### 🚀 Live Deployment

🔗 **[https://hive-board.vercel.app/](https://hive-board.vercel.app/)**

### 💻 GitHub Repositories

* Frontend → [https://github.com/paarthureddy/-HiveBoard-Frontend](https://github.com/paarthureddy/-HiveBoard-Frontend)
* Backend → [https://github.com/paarthureddy/HiveBoard-Backend](https://github.com/paarthureddy/HiveBoard-Backend)

---

# 📖 Project Description

HiveBoard bridges the gap between **brainstorming and structured meetings**.

Users can create **private or public collaborative sessions** with a shared whiteboard canvas that supports **real-time strokes and updates**.

The platform also includes:

* Integrated chat system
* AI enhancements using **Google Gemini**
* Detailed participation analytics
* Secure authentication
* Exportable meeting reports

HiveBoard enables teams to **conceptualize ideas, track participation, and export their collaborative work securely**.

---

# ✨ Key Features

### 🧑‍🤝‍🧑 Real-Time Collaboration

Synchronized whiteboard canvas across all connected clients using **WebSockets (Socket.io)**.

### 📅 Dynamic Meeting Management

Create, join, and manage **public or private meeting rooms**.

### 🔐 Authentication

Secure login using:

* JWT Authentication
* Google OAuth
* Passport.js

### 📊 Analytics & Tracking

Tracks:

* User participation metrics
* Session timelines
* Activity reports

Supports export to:

* PDF
* CSV

### 🤖 AI Integrations

Uses **Google Gemini AI** to generate:

* Intelligent whiteboard summaries
* Meeting insights

### 🎨 Modern Responsive UI

Built using:

* React
* Vite
* Tailwind CSS
* Shadcn UI

---

# 🏗️ Architecture & Workflow

HiveBoard follows a **modern MERN architecture**.

```
User / Browser
      │
      ▼
Frontend (React + Vite + TypeScript)
      │
      ├── UI Layer (Shadcn UI + Tailwind)
      ├── State Management (Hooks + Context)
      ├── HTTP Client (Axios)
      └── WebSocket Client (Socket.io)

      │
      ▼

Backend API (Node.js + Express)
      │
      ├── Express REST API
      ├── Socket.io WebSocket Server
      ├── Authentication (JWT + Passport.js)
      ├── Meeting Management
      ├── Analytics Engine
      └── AI Integration (Google Gemini)

      │
      ▼

Database Layer
MongoDB Atlas (via Mongoose)

External Providers
• Google OAuth
• Google Gemini AI
```

---

# 📁 Project Structure

## Frontend Structure

```
-HiveBoard-Frontend/
│
├── public/
├── src/
│   ├── assets/        # Static assets
│   ├── components/    # UI & Canvas components
│   ├── contexts/      # React contexts (Auth, Meeting, Socket)
│   ├── hooks/         # Custom hooks
│   ├── lib/           # API clients and utilities
│   ├── pages/         # Views (Dashboard, Canvas, Login)
│   ├── tests/         # Unit & integration tests
│   └── types/         # TypeScript definitions
│
├── index.html
├── package.json
└── tailwind.config.ts
```

---

## Backend Structure

```
HiveBoard-Backend/
│
├── controllers/       # Route business logic
├── routes/            # Express route definitions
├── models/            # Mongoose schemas
│                      # (User, Meeting, History)
├── middleware/        # Auth guards & error handling
├── config/            # DB config & Passport strategies
├── utils/             # Helper utilities
│
├── socketHandlers.js  # WebSocket logic
├── index.js
├── server.js
│
├── Dockerfile
└── docker-compose.yml
```

---

# 📡 API Endpoints

## 🔐 Authentication

```
POST   /api/auth/login
POST   /api/auth/register
POST   /api/auth/google/verify
GET    /api/auth/me
```

---

## 📅 Meetings & Collaboration

```
GET    /api/meetings
GET    /api/meetings/:id
POST   /api/meetings
PUT    /api/meetings/:id
```

---

## 📩 Access & Invites

```
POST   /api/invites/generate
POST   /api/invites/:token/join
PUT    /api/invites/:meetingId/toggle
```

---

## 📊 Users & Analytics

```
GET    /api/users/report
GET    /api/analytics
GET    /api/export
```

---

# 🔧 Environment Requirements

## Frontend `.env`

Create a `.env` file in the frontend root:

```env
VITE_GOOGLE_CLIENT_ID=your_google_oauth_client_id
VITE_API_URL=http://localhost:5000/api
```

---

## Backend `.env`

Create a `.env` file in the backend root:

```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_super_secret_jwt_key
GOOGLE_CLIENT_ID=your_google_oauth_client_id
GOOGLE_CLIENT_SECRET=your_google_oauth_client_secret
GOOGLE_CALLBACK_URL=http://localhost:5000/api/auth/google/callback
FRONTEND_URL=http://localhost:5173
```

---

# 💻 Local Setup & Installation

### Prerequisites

* Node.js (v18+)
* MongoDB
* Git

---

## 1️⃣ Database Setup

Run MongoDB locally **or** configure MongoDB Atlas and paste the URI in the backend `.env`.

---

## 2️⃣ Backend Setup

```bash
git clone https://github.com/paarthureddy/HiveBoard-Backend.git

cd HiveBoard-Backend

npm install

npm run dev
```

Backend will run on:

```
http://localhost:5000
```

---

## 3️⃣ Frontend Setup

```bash
git clone https://github.com/paarthureddy/-HiveBoard-Frontend.git

cd -HiveBoard-Frontend

npm install

npm run dev
```

Frontend will run on:

```
http://localhost:5173
```

---

# 🐳 Docker Deployment

HiveBoard supports **containerized deployment using Docker**.

Steps:

1. Install Docker & Docker Compose
2. Clone both repositories
3. Add `.env` files in both folders
4. Run:

```bash
docker-compose up --build
```

Services will run on:

```
Frontend → http://localhost:80
Backend  → http://localhost:5000
MongoDB  → localhost:27017
```

---

# 🚀 Cloud Deployment

### Frontend

Hosted on **Vercel**

* Vite build configuration
* Environment variables managed via Vercel dashboard

### Backend

Hosted on **Render (or similar PaaS)**

* Node.js Express server
* Socket.io real-time communication

### Database

Hosted on **MongoDB Atlas**

* Serverless MongoDB cluster
* Secure connection via environment variables

---

# 📄 License

Educational Project.

---

