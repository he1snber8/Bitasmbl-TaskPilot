# Bitasmbl-TaskPilot

Develop a web-based task management application enabling users to register, authenticate via JWT, and manage tasks organized by projects with priority-based sorting.

## Tech Stack
- Express.js
- MongoDB
- React
- Node.js

## Requirements
- Implement JWT-based authentication
- Design Mongoose schemas for User and Task
- Create RESTful API endpoints for CRUD operations
- Implement priority sorting on front-end
- Optional: Filter tasks by project category

## Installation
1. Clone the repository:
   bash
   git clone https://github.com/YourUsername/Bitasmbl-TaskPilot.git
   cd Bitasmbl-TaskPilot
   
2. Install server dependencies:
   bash
   npm install
   
3. Set up environment variables:
   - Create a `.env` file in the project root or copy `.env.example`:
     bash
     cp .env.example .env
     
   - Define the following variables in `.env`:
     env
     MONGODB_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret_key
     PORT=5000
     
4. Install client dependencies:
   bash
   cd client
   npm install
   

## Usage
1. Start the backend server (from project root):
   bash
   npm run dev
   
2. Start the frontend (in `/client` folder):
   bash
   npm start
   
3. Open your browser at `http://localhost:3000` to use TaskPilot.

## Implementation Steps
1. Initialize a Node.js project and install Express, Mongoose, bcrypt, jsonwebtoken, and other dependencies.
2. Configure Express server (`server.js` or `app.js`) and connect to MongoDB using Mongoose.
3. Define Mongoose schemas and models for `User` (email, password, etc.) and `Task` (title, description, priority, project, user reference).
4. Implement JWT-based authentication: registration and login routes under `/api/auth`, hashing passwords, issuing tokens.
5. Create RESTful endpoints for tasks under `/api/tasks`:
   - GET, POST on `/api/tasks`
   - GET, PUT, DELETE on `/api/tasks/:id`
   - Protect routes with JWT middleware.
6. Initialize React project in `/client` using Create React App.
7. Build components for user authentication, task list, task form, and project filter.
8. Integrate frontend with API using `fetch` or `axios`, store JWT in `localStorage`, set auth header.
9. Implement client-side priority-based sorting and optional filtering by project category.

## API Endpoints
bash
POST   /api/auth/register    # Register a new user
POST   /api/auth/login       # Authenticate user and receive JWT
GET    /api/tasks            # Retrieve all tasks (query: ?project=name&sort=priority)
POST   /api/tasks            # Create a new task
GET    /api/tasks/:id        # Retrieve a single task by ID
PUT    /api/tasks/:id        # Update a task by ID
DELETE /api/tasks/:id        # Delete a task by ID