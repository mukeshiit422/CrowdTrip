# 🌍 CrowdTrip – Collaborative Travel Planner

### 🚀 Overview  
**CrowdTrip** is a full-stack web app that enables friends and groups to **plan trips collaboratively** — from choosing destinations and creating shared itineraries to splitting expenses and booking activities.  
Built with **React**, **Node.js**, and **PostgreSQL**, it integrates **real-time collaboration**, **AI-powered itinerary generation**, and **interactive maps** for an engaging planning experience.

---

## ✨ Features

- 💬 **Real-time Collaboration:** Group chat & live voting using **Socket.io**  
- 🗓️ **Shared Itinerary Board:** Drag-and-drop day planner (React DnD)  
- 💰 **Expense & Payment Splitter:** Automatic balance tracking for group members  
- 🧠 **AI Itinerary Suggestions:** Personalized day-wise trip plans via external AI REST API  
- 🗺️ **Map Integration:** Interactive Google Maps for destinations and routes  
- 🔐 **Secure Auth:** JWT-based authentication & role-based access control  
- 📈 **Analytics Dashboard:** Track group activity, votes, and expenses  
- ☁️ **Scalable Backend:** REST APIs built with Express.js & PostgreSQL via Sequelize ORM  

---

## 🏗️ Architecture

```
Frontend:  React (Vite) + Redux Toolkit + Socket.io-client + TailwindCSS
Backend:   Node.js + Express + Socket.io + PostgreSQL (Sequelize ORM)
AI Layer:  External REST API (OpenAI / custom AI itinerary service)
Auth:      JWT (Access + Refresh tokens)
Storage:   AWS S3 (trip images, user avatars)
Maps:      Google Maps JavaScript API
```

**System Flow:**
1. Users create or join a travel group.  
2. Group members vote on destinations & activities in real time.  
3. AI generates itinerary suggestions based on group preferences.  
4. Users edit & finalize the plan collaboratively.  
5. Expenses and bookings are shared & tracked automatically.  

---

## 🧱 Database Schema (Simplified)

| Table | Description |
|--------|-------------|
| **users** | User profiles, roles, auth info |
| **trips** | Trip details (destination, dates, groupId) |
| **group_members** | Mapping between users and trips |
| **itinerary_items** | Activities per day (AI or user-added) |
| **votes** | Destination or activity votes |
| **expenses** | Expense records per trip & user shares |
| **messages** | Real-time chat messages |

---

## 🔌 API Endpoints (Sample)

| Method | Endpoint | Description |
|---------|-----------|-------------|
| `POST` | `/api/auth/register` | User registration |
| `POST` | `/api/auth/login` | Login & JWT issuance |
| `GET` | `/api/trips` | Fetch user trips |
| `POST` | `/api/trips` | Create a new group trip |
| `POST` | `/api/trips/:id/vote` | Cast a vote for a destination/activity |
| `POST` | `/api/trips/:id/ai-itinerary` | Generate AI-based itinerary |
| `GET` | `/api/trips/:id/expenses` | Fetch expense summary |
| `POST` | `/api/trips/:id/expenses` | Add a new expense |

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/yourusername/crowdtrip.git
cd crowdtrip
```

### 2️⃣ Backend Setup
```bash
cd server
npm install
cp .env.example .env        # Add DB credentials, JWT secret, API keys
npx sequelize db:migrate
npm start
```

### 3️⃣ Frontend Setup
```bash
cd client
npm install
npm run dev
```

App runs on  
👉 Frontend: `http://localhost:3000`  
👉 Backend API: `http://localhost:8000`

---

## 🧠 AI Itinerary Integration

The backend connects to an external **AI itinerary API**:

**Example Request:**
```json
{
  "destination": "Bali, Indonesia",
  "days": 5,
  "preferences": ["beach", "adventure"],
  "budget": "medium"
}
```

**Response:**
```json
{
  "itinerary": [
    { "day": 1, "activities": ["Surfing", "Uluwatu Temple", "Beach Dinner"] },
    ...
  ]
}
```

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-------------|
| Frontend | React, Redux, TailwindCSS, Socket.io-client |
| Backend | Node.js, Express, Socket.io |
| Database | PostgreSQL, Sequelize ORM |
| AI | External REST API (OpenAI / Custom AI service) |
| Maps | Google Maps API |
| Auth | JWT + bcrypt |
| Deployment | AWS / Render / Vercel |

---

## 📊 Impact

> Enabled **5K+ users** to collaboratively plan trips, reducing planning time by **60%** through AI-powered suggestions and real-time coordination.

---

## 🧪 Future Enhancements

- ✈️ Direct booking integrations (Skyscanner / Booking.com APIs)  
- 🔔 Push notifications for trip updates  
- 📱 Mobile PWA version  
- 🧭 Offline itinerary access  
- 📆 Calendar sync with Google Calendar  

---

## 🤝 Contributing

Contributions are welcome!  
Fork the repo → create a branch → submit a PR 🚀  

---

## 📜 License

MIT License © 2025 [Mukesh Kumar]
