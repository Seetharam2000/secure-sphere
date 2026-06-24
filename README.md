Secure Sphere is a security-first banking operations and real-time fraud detection dashboard. It provides bank operators, risk analysts, and administrators with a comprehensive, centralized platform to manage bank customers, accounts, transactions, and cards, while proactively identifying and mitigating fraudulent activity using rule-based risk scoring and alert management.
---
Key Features
Interactive Operations Dashboard**: High-level telemetry displaying total customers, active accounts, transaction volumes, and unresolved fraud alerts at a glance.
Customer & Account Directory**: Add, update, view, and manage customer profiles and their associated savings or current accounts.
  Smart Card Management**: Monitor and control customer credit/debit cards, adjust limits, and update card status.
Real-time Transaction Ledger**: Audit history of all financial transactions (Credits, Debits, Transfers) with status tracking (Completed, Flagged, Failed).
Automated Fraud Detection**: Risk-score engine evaluating transaction profiles and flagging potential threats with automated explanations (e.g., suspicious transfer sizes, high-risk activity).
Fraud & Risk Reporting**: Visualize transaction and security trends using dynamic Recharts visualizations (credits vs. debits, resolved alerts vs. false positives).
Role-Based Simulated Access**: Administrative panel for audit trails, security configurations, and operational logs.
---
Tech Stack
Frontend
* **Core**: React 18, TypeScript, Vite
* **Routing & State**: React Router DOM (v6), TanStack React Query (v5)
* **Styling & UI**: Tailwind CSS, Shadcn UI (Radix UI primitives), Lucide React (Icons)
* **Data Visualization**: Recharts
* **Forms & Validation**: React Hook Form, Zod
### Backend API
* **Runtime & Framework**: Node.js, Express
* **Database**: SQLite (via `better-sqlite3`)
* **Features**: Auto-seeding database migrations, modular API routes, CORS validation.
---
 Project Structure
```text
├── server/                 # Express backend API & SQLite database
│   ├── data/               # SQLite database storage (gitignored)
│   ├── db.js               # Database schema initialization and seeds
│   ├── index.js            # Express server, middleware, and routes
│   └── package.json        # Backend dependencies & scripts
├── src/                    # Frontend React SPA
│   ├── components/         # Reusable UI widgets & layout containers
│   ├── hooks/              # Custom React hooks (auth, query hooks)
│   ├── lib/                # API client wrapper & types
│   ├── pages/              # Routing page views (Dashboard, Customers, Alerts, etc.)
│   ├── App.tsx             # Route definitions and configuration
│   └── main.tsx            # React application entry point
├── render.yaml             # Render Blueprint configuration
├── vercel.json             # Vercel SPA router config
└── package.json            # Frontend workspace configuration
```
---
 Getting Started
Prerequisites
* [Node.js](https://nodejs.org/) (version 20 or higher recommended)
* `npm` (included with Node.js)
Local Installation
1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd secure-sphere
   ```
2. **Install frontend dependencies:**
   ```bash
   npm install
   ```
3. **Install backend dependencies:**
   ```bash
   npm install --prefix server
   ```
### Running Locally
To run both the Vite frontend dev server and Express API server concurrently:
```bash
npm run dev:all
```
* **Frontend Dev Server**: [http://localhost:8080](http://localhost:8080)
* **Backend API**: [http://localhost:3001](http://localhost:3001)
The frontend uses Vite's built-in proxy settings (`vite.config.ts`) to forward `/api/*` calls directly to the Express server running on port `3001`.
---
## ☁️ Deployment
For deployment instructions to host the backend on **Render** and frontend on **Vercel**, please refer to the detailed [Deployment Guide](deployment_guide.md).
---
 License
This project is licensed under the MIT License. See the LICENSE file for details.
