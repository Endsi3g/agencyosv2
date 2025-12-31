# 🚀 AgencyOS v2 - CRM Suite

A modern, full-featured CRM (Customer Relationship Management) application built with Next.js 16, React 19, and TypeScript. Designed for agencies and businesses to manage contacts, companies, deals, and activities efficiently.

![CRM Dashboard](https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&q=80&w=2670)

---

## ✨ Features

- **🔐 Robust Authentication** - JWT-based auth with refresh tokens and role-based access control (Admin, Sales, Marketing)
- **📇 Contact Management** - Store and manage customer contacts with detailed profiles
- **🏢 Company Tracking** - Organize companies and link contacts to them
- **💰 Deal Pipeline** - Visual Kanban board to track sales opportunities through customizable stages
- **📝 Activity Logging** - Log calls, emails, meetings, and tasks with rich timeline views
- **🤖 Automation** - visual workflow builder for marketing automation
- **📊 Dashboard** - Visual overview of your KPI and performance
- **🌙 Dark Mode** - Beautiful dark theme with glassmorphism design
- **📱 Responsive** - Works seamlessly on desktop and mobile

---

## 🛠️ Architecture & Tech Stack

The application uses a modern **Client-Server** architecture:

### Frontend (`crm-app`)

- **Framework**: Next.js 16.1 (App Router)
- **Language**: TypeScript 5
- **Styling**: Tailwind CSS 4, Framer Motion
- **State**: React Context + Hooks
- **Data Fetching**: Axios with Interceptors

### Backend (`crm-app/server`)

- **Runtime**: Node.js + Express
- **Database**: PostgreSQL (via Supabase)
- **ORM**: Prisma
- **Auth**: JWT (Access + Refresh Tokens)
- **Validation**: Express-validator, Zod
- **Security**: Helmet, CORS, Rate Limiting

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn
- PostgreSQL Database (Supabase recommended)

### 1. Database & Backend Setup

Navigate to the server directory:
```bash
cd crm-app/server
```

Install dependencies and generate Prisma client:
```bash
npm install
npx prisma generate
```

Set up your `.env` file (copy `.env.example`).

Seed the database with demo data (Users, Deals, Contacts):
```bash
npm run seed
```

Start the Backend Server (runs on port 3001):
```bash
npm run dev
```

### 2. Frontend Setup

Open a new terminal and navigate to the app directory:
```bash
cd crm-app
```

Install dependencies:
```bash
npm install
```

Start the Frontend (runs on port 3000):
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the application.

---

## 🔑 Demo Credentials

After seeding the database, use these credentials to log in:

- **Email**: `admin@crmsuite.com`
- **Password**: `password123`

---

## 📁 Project Structure

```plaintext
crm-app/
├── server/            # Express Backend API
│   ├── prisma/        # Database Schema & Seeds
│   ├── src/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── routes/
│   │   └── services/
├── src/               # Next.js Frontend
│   ├── app/           # App Router pages
│   ├── components/    # Reusable UI components
│   ├── context/       # React Context (Auth)
│   ├── services/      # API Integration
│   └── types/         # TypeScript definitions
└── public/            # Static assets
```

---

## 📜 Available Scripts

| Category | Command | Description |
|----------|---------|-------------|
| **Backend** | `npm run dev` | Start development server (port 3001) |
| | `npm run db:push` | Push schema changes to DB |
| | `npm run seed` | Populate DB with demo data |
| | `npm run studio` | Open Prisma Studio GUI |
| **Frontend** | `npm run dev` | Start Next.js dev server (port 3000) |
| | `npm run build` | Build for production |
| | `npm run lint` | Run ESLint |

---

## 👤 Author

**Endsi3g**

<p align="center">
  Built with ❤️ using Next.js and TypeScript
</p>
