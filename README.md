# ProjectSync

A full-stack project management application built with Next.js, Express, and Prisma. It provides a comprehensive dashboard for managing projects, tasks, teams, and users with real-time data visualization.

## Features

- **Dashboard**: Overview of task priorities, project status, and recent tasks
- **Project Management**: Create, view, and manage projects with multiple view modes (Board, List, Table, Timeline)
- **Task Management**: Organize tasks by priority levels (Backlog, Low, Medium, High, Urgent)
- **Team Collaboration**: Manage teams and assign tasks to team members
- **User Management**: Handle user accounts and permissions
- **Search Functionality**: Powerful search across projects and tasks
- **Dark Mode Support**: Toggle between light and dark themes
- **Responsive Design**: Works seamlessly on desktop and mobile devices

## Tech Stack

### Frontend
- **Next.js 14** - React framework for production
- **TypeScript** - Type-safe JavaScript
- **Tailwind CSS** - Utility-first CSS framework
- **Material-UI (MUI)** - React components library
- **Redux Toolkit** - State management
- **AWS Amplify** - Authentication and backend services
- **Recharts** - Data visualization library
- **React DnD** - Drag and drop functionality

### Backend
- **Express.js** - Web application framework
- **TypeScript** - Type-safe JavaScript
- **Prisma** - Database ORM
- **PostgreSQL** - Database (via Prisma)
- **CORS** - Cross-origin resource sharing
- **Helmet** - Security middleware
- **Morgan** - HTTP request logger

## Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- PostgreSQL database

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd projectsync_main
   ```

2. **Install client dependencies**
   ```bash
   cd client
   npm install
   ```

3. **Install server dependencies**
   ```bash
   cd ../server
   npm install
   ```

4. **Set up environment variables**

   Create `.env` files in both `client` and `server` directories.

   **Server (.env)**
   ```
   DATABASE_URL="postgresql://username:password@localhost:5432/projectsync"
   PORT=3000
   ```

   **Client (.env.local)**
   ```
   NEXT_PUBLIC_API_URL=http://localhost:3000
   ```

5. **Set up the database**
   ```bash
   cd server
   npx prisma migrate dev
   npx prisma db seed
   ```

6. **Start the development servers**

   **Terminal 1 - Server**
   ```bash
   cd server
   npm run dev
   ```

   **Terminal 2 - Client**
   ```bash
   cd client
   npm run dev
   ```

7. **Open your browser**

   Navigate to `http://localhost:3000` to view the application.

## Usage

### Dashboard
- View task priority distribution charts
- Monitor project status
- See your assigned tasks in a data grid

### Projects
- Create new projects
- Switch between different view modes:
  - Board View: Kanban-style task management
  - List View: Simple list of tasks
  - Table View: Spreadsheet-like interface
  - Timeline View: Gantt chart visualization

### Tasks
- Create tasks with different priority levels
- Assign tasks to team members
- Track task status and due dates

### Teams
- Create and manage teams
- Assign users to teams
- View team performance

### Users
- Manage user accounts
- Set user permissions
- View user activity

## API Endpoints

The API provides the following main endpoints:

- `GET /` - Health check
- `GET/POST/PUT/DELETE /projects` - Project management
- `GET/POST/PUT/DELETE /tasks` - Task management
- `GET/POST/PUT/DELETE /users` - User management
- `GET/POST/PUT/DELETE /teams` - Team management
- `GET /search` - Search functionality

## Project Structure

```
projectsync_main/
├── client/                 # Next.js frontend
│   ├── src/
│   │   ├── app/           # Next.js app router pages
│   │   ├── components/    # Reusable React components
│   │   ├── lib/           # Utility functions
│   │   └── state/         # Redux store and API slices
│   └── public/            # Static assets
├── server/                 # Express.js backend
│   ├── src/
│   │   ├── controllers/   # Route controllers
│   │   ├── routes/        # API routes
│   │   └── index.ts       # Server entry point
│   └── prisma/            # Database schema and migrations
└── README.md
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Scripts

### Client Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

### Server Scripts
- `npm run dev` - Start development server with hot reload
- `npm run build` - Compile TypeScript
- `npm run start` - Start production server
- `npm run seed` - Seed the database

## License

This project is licensed under the ISC License.
