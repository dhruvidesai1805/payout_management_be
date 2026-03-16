# PayFlow — Backend API

Node.js + Express + MongoDB REST API for the Payout Management system.

## Tech Stack
- Node.js + Express 4
- MongoDB Atlas (Mongoose)
- JWT Authentication (8h expiry)
- bcryptjs password hashing

## Quick Start (under 5 minutes)

```bash
# 1. Install dependencies
npm install

# 2. Configure environment (.env already included)
# PORT=5000, MONGO_URI, JWT_SECRET are set

# 3. Seed users into MongoDB
npm run seed

# 4. Start development server
npm run dev
```

Server runs on `http://localhost:5000`

## API Endpoints

| Method | Endpoint | Role | Description |
|--------|----------|------|-------------|
| POST | /api/auth/login | Any | Get JWT token |
| GET | /api/vendors | OPS | List vendors |
| POST | /api/vendors | OPS | Create vendor |
| GET | /api/payouts | OPS, FINANCE | List payouts (filters: status, vendor_id) |
| POST | /api/payouts | OPS | Create draft payout |
| GET | /api/payouts/:id | OPS, FINANCE | Payout detail |
| GET | /api/payouts/:id/audit | OPS, FINANCE | Audit trail |
| POST | /api/payouts/:id/submit | OPS | Draft → Submitted |
| POST | /api/payouts/:id/approve | FINANCE | Submitted → Approved |
| POST | /api/payouts/:id/reject | FINANCE | Submitted → Rejected (reason required) |


## Project Structure
```
├── models/
│   ├── User.js
│   ├── Vendor.js
│   ├── Payout.js
│   └── PayoutAudit.js
├── routes/
│   ├── auth.js
│   ├── vendors.js
│   └── payouts.js
├── middleware/
│   └── auth.js        # JWT verify + role guard
├── server.js
└── seed.js
```
