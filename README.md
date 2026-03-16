# Payout Management MVP — Backend

Node.js + Express backend for the Payout Management system.

## Tech Stack
- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT Authentication

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Create `.env` file from the template:
   ```bash
   cp .env.example .env
   ```

3. Update `.env` with your MongoDB Atlas URI and JWT secret.

4. Seed the database:
   ```bash
   npm run seed
   ```

5. Run the development server:
   ```bash
   npm run dev
   ```

The server will start on `http://localhost:5000`.

## Seeded Users
| Email              | Password | Role    |
|--------------------|----------|---------|
| ops@demo.com       | ops123   | OPS     |
| finance@demo.com   | fin123   | FINANCE |
