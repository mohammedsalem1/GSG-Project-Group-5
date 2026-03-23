# 📦 Skill Swap Platform

**TypeScript • NestJS • Prisma • PostgreSQL • Docker**

A scalable peer-to-peer platform that enables users to exchange skills instead of money, combining real-time communication, gamification, dispute resolution, and a powerful admin control system.

---

## 📋 Table of Contents

- Project Overview  
- Key Features  
- Business Model  
- Tech Stack  
- Prerequisites  
- Installation  
- Configuration  
- Usage  
- API Documentation  
- System Design  
- Modules  
- Database Schema  
- Testing  
- Deployment  
- Project Structure  
- Contributing  
- License  

---

## 🎯 Project Overview

The **Skill Swap Platform** allows users to exchange skills using a barter-based model.

Users can:
- Offer skills
- Request skills
- Match with other users
- Communicate via chat
- Schedule sessions
- Reviews & Feedback
- Resolve disputes
- Earn points and badges
- Build reputation through reviews

---

## ✨ Key Features

### 👤 User Management
- User registration, login, logout
- JWT authentication with refresh tokens
- Email verification with OTP
- Forgot password & reset flow
- Profile management (update info, change password)

### 🧠 Skills System
- Add offered and wanted skills
- Manage skills & categories
- Search, filter, and autocomplete skills
- User skill details, ratings, and sessions
- Popular & trending skills
- Admin: list, view, delete skills
- Pagination and feedback aggregations

### 🔄 Swaps System
- Send swap requests between users
- Accept, decline, or cancel requests
- Automatic expiration of pending requests (cron job)
- Track sessions and conversations for accepted swaps
- Get swap statistics (sent, received, accepted, rejected)
- Notifications for all actions (request, accept, decline, cancel)

### 📅 Session Management
- Schedule sessions – Create and plan sessions between hosts and attendees.

- Track completion – Mark sessions as completed, award points, and trigger review requests.

- Update sessions – Reschedule or cancel sessions with notifications sent to participants.

- View sessions – Retrieve session details, personal calendar, or admin-level listings.

### 💬 Chat System
- One-to-one messaging
- Linked to sessions/swaps

### 🔔 Notification System
- Event-based notifications
- Read/unread tracking

### ⚖️ Dispute System
- Open disputes after sessions
- Admin resolution workflow

### ⭐ Reviews & Feedback
- Rate users after completed sessions

- Leave comments and feedback for other users

- Retrieve reviews received by user or by specific skills

- Paginate and filter reviews (public & verified only)

- Flag inappropriate reviews for moderation

- Gamification points awarded for submitting reviews

### 🎮 Gamification
- Points System: Users earn points for actions like submitting reviews, completing sessions, and unlocking badges.

- Badges & Rewards: Users can unlock badges based on completed sessions, skill achievements, or platform milestones.

- Progress Tracking: View earned badges, locked badges, and remaining progress toward the next badge.

- User Leaderboard: Track total points and badges across the platform.

- Admin Controls: Adjust user points, update badge requirements, and monitor badge distribution.

- Gamification Feedback: Users are notified when they earn points or unlock a badge.

### 🛡️ Admin Panel

#### 📊 Dashboard Analytics
- View platform-wide metrics including:
  - Completed sessions
  - Active users
  - Swaps
  - Weekly reports
  - Top skills
  - User activity
  - Session trends

#### 👤 User Moderation
- Ban, unban, suspend, or unsuspend users
- Issue warnings or add admin notes to user profiles
- Track flagged users
- Monitor users with multiple cancellations

#### 📝 Audit Logs
- Maintain a detailed history of admin actions and system changes
- Ensure transparency and accountability

#### 📁 Data Export
- Export sessions, swaps, or user activity as CSV
- Use for reporting and analysis

#### 🔍 User Insights
- Access detailed overviews of individual users:
  - Session history
  - Swaps
  - Badges
  - Points
  - Activity logs
- Monitor users’ disputes and feedback

#### 🎮 Gamification Management
- View all badges and total users per badge
- Adjust badge requirements
- Adjust user points directly from the admin panel

#### ⚙️ Skills & Swaps Management
- Manage platform skills (create, update, deactivate)
- Track all swap requests with filtering, pagination, and export options

### 🛠️ Tech Stack

#### Backend
- **Framework:** NestJS (Node.js framework)  
- **Language:** TypeScript  
- **ORM:** Prisma  
- **Database:** PostgreSQL  
- **Authentication:** Passport.js with JWT  
- **Validation:** class-validator, class-transformer  
- **Documentation:** Swagger/OpenAPI  

#### DevOps & Tools
- **Containerization:** Docker & Docker Compose  
- **Testing:** Jest (Unit & E2E tests)  
- **Version Control:** Git  
- **API Testing:** Postman / Thunder Client  

#### Key Dependencies
```json
{
  "@nestjs/core": "^10.x",
  "@nestjs/passport": "^10.x",
  "@nestjs/jwt": "^10.x",
  "@prisma/client": "^5.x",
  "bcrypt": "^5.x",
  "class-validator": "^0.14.x"
}
```

### 🚀 Getting Started

#### Local Development Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/RedaAwwad/Food-Delivery.git
   cd Food-Delivery
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Set up environment variables**

   Create a `.env` file in the root directory:

   ```env
   PORT=4000
   API_VERSION=v1
   APP_BASE_URL=http://localhost:4000

   # Database Configuration
   POSTGRES_USER=root
   POSTGRES_PASSWORD=example
   POSTGRES_DB=food_delivery
   DATABASE_URL=postgresql://root:example@postgres:5432/food_delivery
   ```

4. **Generate Swagger documentation**

   ```bash
   npm run swagger
   ```

5. **Start the development server**

   ```bash
   npm run dev
   ```

   The API will be available at `http://localhost:4000`

#### Docker Setup

Start the entire application stack (API + PostgreSQL) with Docker Compose:

```bash
docker-compose up --build
```

This will start:

- Express API server on `http://localhost:4000`
- PostgreSQL database (accessible internally to the app)
- Automatic volume mounting for development

To run in detached mode:

```bash
docker-compose up -d
```

To stop all services:

```bash
docker-compose down
```

### 📖 API Documentation

Once the server is running, you can access:

- **API Documentation**: `http://localhost:4000/api-docs`
- **Health Check**: `http://localhost:4000/`

### 🐳 Docker Commands

```bash
# Build and start all services
docker-compose up --build

# Start services in background
docker-compose up -d

# Stop all services
docker-compose down

# View logs
docker-compose logs -f

# View logs for specific service
docker-compose logs -f node-app

# Rebuild and restart specific service
docker-compose up --build node-app

# Remove all containers and volumes
docker-compose down -v
```

### 🔍 Development

### TypeScript Configuration

The project uses strict TypeScript configuration with:

- Strict mode enabled
- No unchecked indexed access
- Exact optional property types
- ES modules with Node.js resolution

⭐ **Star this repository** if you find it helpful!  

Made with ❤️ by **Mohammed Salem**, **Izz Masri**, & **Mohanad Abo Sabha**