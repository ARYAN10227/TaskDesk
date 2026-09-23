# NeatDesk

A modern project management application built with React and Node.js, featuring workspaces, projects, tasks, and team collaboration.

## Features

- **Workspaces** - Create and manage multiple workspaces with role-based access (Admin/Member)
- **Projects** - Track projects with status, priority, progress, and deadlines
- **Tasks** - Create tasks with types (Task, Bug, Feature, Improvement), priorities, and assignees
- **Team Collaboration** - Invite members, assign tasks, and add comments
- **Analytics** - View project analytics and statistics with interactive charts
- **Calendar View** - Visualize tasks and deadlines on a calendar

## Tech Stack

### Frontend
- React 19
- Vite 7
- TailwindCSS 4
- Redux Toolkit
- React Router
- Recharts (charts/analytics)
- Clerk (authentication)

### Backend
- Node.js / Express 5
- Prisma ORM
- PostgreSQL (Neon serverless)
- Inngest (background jobs)
- Nodemailer (email notifications)
- Clerk (authentication)

## Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── features/       # Redux slices
│   │   ├── configs/        # API configuration
│   │   └── app/            # Redux store
│   └── public/             # Static assets
│
└── server/                 # Node.js backend
    ├── controllers/        # Route handlers
    ├── routes/             # API routes
    ├── middlewares/        # Auth middleware
    ├── prisma/             # Database schema
    ├── inngest/            # Background job functions
    └── configs/            # Prisma & Nodemailer config
```

## Prerequisites

- Node.js 18+
- npm or yarn
- PostgreSQL database (or Neon account)
- Clerk account for authentication

## Environment Variables

### Client (`client/.env`)
```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_API_URL=http://localhost:5000
```

### Server (`server/.env`)
```env
PORT=5000
DATABASE_URL=your_neon_pooled_connection_string
DIRECT_URL=your_neon_direct_connection_string
CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
INNGEST_EVENT_KEY=your_inngest_event_key
INNGEST_SIGNING_KEY=your_inngest_signing_key
```

## Installation

### 1. Clone the repository
```bash
git clone <repository-url>
cd NeatDesk
```

### 2. Install dependencies

**Client:**
```bash
cd client
npm install
```

**Server:**
```bash
cd server
npm install
```

### 3. Set up the database
```bash
cd server
npx prisma generate
npx prisma db push
```

### 4. Start the development servers

**Server:**
```bash
cd server
npm run server
```

**Client:**
```bash
cd client
npm run dev
```

The client will be available at `http://localhost:5173` and the server at `http://localhost:5000`.

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET/POST | `/api/workspaces` | Manage workspaces |
| GET/POST | `/api/projects` | Manage projects |
| GET/POST | `/api/tasks` | Manage tasks |
| GET/POST | `/api/comments` | Manage comments |

## Deployment

Both client and server are configured for deployment on Vercel with included `vercel.json` configuration files.

## License

See [LICENSE.md](client/LICENSE.md) for details.