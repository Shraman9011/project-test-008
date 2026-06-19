# test oo8

## Project Setup

This project is a monorepo with a frontend React application and a backend (no-backend) structure.

## Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd test-oo8
   ```

2. **Install frontend dependencies:**
   ```bash
   cd frontend
   npm install
   ```

3. **Install backend dependencies (if any were added later, though currently no-backend):
   ```bash
   cd backend
   npm install
   ```

4. **Set up environment variables:**
   Copy the `.env.example` file to `.env` in the root directory and fill in your database connection details.
   ```bash
   cp .env.example .env
   ```

## Running Locally

1. **Start the frontend development server:**
   ```bash
   cd frontend
   npm run dev
   ```
   This will typically start the React development server on `http://localhost:5173` (or another port if specified in `vite.config.ts`).

2. **Backend (no-backend):
   Since there is no backend framework, there is no backend server to run.

## Database

This project uses PostgreSQL as its primary database. Ensure you have a PostgreSQL instance running and accessible, and configure the `DATABASE_URL` in your `.env` file.
