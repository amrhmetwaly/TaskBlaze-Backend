# 🚀 TaskBlaze Backend

The backend server for TaskBlaze, built with Express.js, Prisma, and MySQL.

## 🛠 Tech Stack

- Express.js
- Prisma ORM
- MySQL
- TypeScript
- CORS enabled

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- MySQL installed and running
- npm or yarn

### Database Setup

1. **Install MySQL**
   ```bash
   # macOS (using Homebrew)
   brew install mysql
   brew services start mysql

   # Ubuntu
   sudo apt install mysql-server
   sudo systemctl start mysql
   ```

2. **Create Database**
   ```bash
   # Access MySQL
   mysql -u root -p

   # Create database
   CREATE DATABASE TODO_APP_DB;
   ```

### Installation

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Configure environment**
   ```bash
   # Create .env file
   cp .env.example .env

   # Update database connection
   DATABASE_URL="mysql://root:your_password@localhost:3306/TODO_APP_DB"
   ```

3. **Initialize Prisma**
   ```bash
   # Generate Prisma Client
   npx prisma generate

   # Run migrations
   npx prisma migrate dev
   ```

4. **Start the server**
   ```bash
   npm start
   ```

## 📁 Project Structure

```
backend/
├── prisma/
│   ├── schema.prisma      # Database schema
│   └── migrations/        # Database migrations
├── server.ts             # Express server setup
└── package.json
```

## 🔑 Environment Variables

```env
DATABASE_URL="mysql://root:password@localhost:3306/TODO_APP_DB"
PORT=3000
```

## 📝 Available Scripts

- `npm start` - Start the server
- `npm run dev` - Start with nodemon
- `npx prisma studio` - Open Prisma Studio
- `npx prisma migrate dev` - Run migrations

## 📡 API Endpoints

### Tasks

- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task

### Request Examples

**Create Task**
```json
POST /api/tasks
{
  "title": "New Task",
  "color": "#3B82F6"
}
```

**Update Task**
```json
PUT /api/tasks/:id
{
  "completed": true
}
``` 