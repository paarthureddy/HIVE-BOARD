Review
🐝 HiveBoard
HiveBoard is a real-time, collaborative whiteboard and meeting platform designed for seamless team interactions. It offers intuitive drawing tools, live chat, session analytics, AI-powered features, and secure authentication.

🌐 Live Application & Repositories
Live Deployment: https://hive-board.vercel.app/
Frontend Repository: https://github.com/paarthureddy/-HiveBoard-Frontend
Backend Repository: https://github.com/paarthureddy/HiveBoard-Backend
📖 Project Description
HiveBoard bridges the gap between brainstorming and structured meetings. It allows users to create private or public collaborative sessions with a shared canvas that supports real-time strokes and updates. Accompanied by integrated chat, AI enhancements (via Google Gemini), and detailed session analytics, HiveBoard enables teams to conceptualize, track participation, and export their work securely.

✨ Key Features
Real-Time Collaboration: Synchronized whiteboard canvas across all connected clients using WebSockets.
Dynamic Meeting Management: Create, join, and manage access to private or public meeting rooms.
Authentication: Secure JWT and Google OAuth integration via Passport.js.
Analytics & Tracking: Detailed user participation metrics, session activity timelines, and data export (PDF/CSV).
AI Integrations: Leverage Google Gemini for intelligent whiteboard summaries or meeting enhancements.
Responsive UI: built with React, Vite, Tailwind CSS, and Shadcn UI.
🏗️ Architecture & Workflow
HiveBoard is built on a modern MERN stack (MongoDB, Express.js, React, Node.js) configured with TypeScript on the frontend and containerized via Docker.

External Providers
Database Layer
Backend API Server (Node.js + Express)
Frontend Engine (Vite + React + TS)
Services
Access Web App
REST API Requests
Real-time Sync
Periodically Save State
User / Browser
UI Layer (Shadcn UI + Tailwind)
State Management (Hooks + Context)
HTTP Client (Axios)
WebSocket Client (Socket.io)
Express Router (/api)
Socket.io WebSocket Server
Auth & OAuth (Passport.js/JWT)
Meeting Management
Access & Invites System
Analytics & Tracking
User Profiles
AI Capabilities (Gemini)
MongoDB (Mongoose)
Google OAuth
Google GenAI (Gemini)
📁 Project Structure
Frontend Structure
text
-HiveBoard-Frontend/
├── public/
├── src/
│   ├── assets/        # Static assets
│   ├── components/    # Reusable UI & Canvas components (Shadcn UI)
│   ├── contexts/      # React Contexts (Auth, Meeting, Socket)
│   ├── hooks/         # Custom React hooks
│   ├── lib/           # Utility functions and API clients
│   ├── pages/         # Route views (Dashboard, Canvas, Login)
│   ├── tests/         # Unit and integration tests
│   └── types/         # TypeScript definitions
├── index.html
├── package.json
└── tailwind.config.ts
Backend Structure
text
HiveBoard-Backend/
├── controllers/       # Business logic for routes
├── routes/            # Express route definitions
├── models/            # Mongoose schemas (User, Meeting, History)
├── middleware/        # JWT & Auth guards, Error handling
├── config/            # DB configuration, Passport strategies
├── utils/             # Helper utilities
├── socketHandlers.js  # WebSocket event logic
├── index.js / server.js
├── Dockerfile
└── docker-compose.yml
📡 API Endpoints
🔐 Authentication
POST /api/auth/login - Local user login
POST /api/auth/register - Local user registration
POST /api/auth/google/verify - Verify Google OAuth tokens
GET /api/auth/me - Fetch authenticated user data
📅 Meetings & Collaboration
GET /api/meetings - Fetch all user meetings
GET /api/meetings/:id - Fetch specific meeting metadata
POST /api/meetings - Create a new meeting instance
PUT /api/meetings/:id - Update meeting details
📩 Access & Invites
POST /api/invites/generate - Generate shareable access token
POST /api/invites/:token/join - Join meeting via token
PUT /api/invites/:meetingId/toggle - Manage meeting access status
📊 Users & Analytics
GET /api/users/report - Get individual user contribution reports
GET /api/analytics - Fetch session activity and participation metrics
GET /api/export - Export reports to CSV/PDF
🔧 Environment Requirements
Frontend (
.env
)
Create a 
.env
 file in the root of the frontend repository:

env
VITE_GOOGLE_CLIENT_ID=your_google_oauth_client_id
VITE_API_URL=http://localhost:5000/api
Backend (
.env
)
Create a 
.env
 file in the root of the backend repository:

env
PORT=5000
MONGODB_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_super_secret_jwt_key
GOOGLE_CLIENT_ID=your_google_oauth_client_id
GOOGLE_CLIENT_SECRET=your_google_oauth_client_secret
GOOGLE_CALLBACK_URL=http://localhost:5000/api/auth/google/callback
FRONTEND_URL=http://localhost:5173
💻 Local Setup & Installation
Prerequisites: Node.js (v18+), MongoDB, and Git.

1. Database Setup
Ensure you have a local MongoDB instance running, or configure an Atlas cluster and paste the URI in your backend 
.env
.

2. Backend Setup
bash
git clone https://github.com/paarthureddy/HiveBoard-Backend.git
cd HiveBoard-Backend
npm install
npm run dev
# The API will start on http://localhost:5000
3. Frontend Setup
bash
git clone https://github.com/paarthureddy/-HiveBoard-Frontend.git
cd -HiveBoard-Frontend
npm install
npm run dev
# The App will start on http://localhost:5173
🐳 Docker Deployment
The project includes a 
docker-compose.yml
 file in the backend repository that maps both the frontend and backend containers together seamlessly alongside a MongoDB instance.

Ensure Docker and Docker Compose are installed.
Clone both repositories into the same parent directory.
Place your 
.env
 files in their respective folders.
From the HiveBoard-Backend folder, run:
bash
docker-compose up --build
Frontend will listen on http://localhost:80
Backend API will run on http://localhost:5000
MongoDB will be available safely on localhost:27017
🚀 Cloud Deployment
Frontend: Deployed globally using Vercel.
Configured with Vite build settings and environment variables handled securely via Vercel's platform.
Backend: Deployed via Render (or similar PaaS).
Handles the Node.js Express server + Socket.io instances using appropriate CORS matching the frontend URL.
Database: Hosted serverlessly on MongoDB Atlas.
📄 License
Educational Project.


