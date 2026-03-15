# INVORA — Smart Inventory Management System

![INVORA Dashboard](https://github.com/aryamansinghbca2023-ctrl/smart-inventory-management-system/assets/placeholder-dashboard.png) *(Note: Add a screenshot of your dashboard here!)*

INVORA is a modern, full-stack inventory management system built to track products, categories, stock levels, system audits, and user approvals seamlessly. Designed with a sleek dark industrial aesthetic, it provides businesses with a production-ready, dynamic view of their real-time operations.

## 🚀 Features
* **Role-Based Access Control (RBAC):** Distinct permissions for `Admin`, `Manager`, and `Employee` roles.
* **Real-time Inventory Tracking:** Categorization, SKU auto-generation, and instantaneous low-stock warnings.
* **Approval Workflow:** Complete system for employees to request stock, and managers to approve/reject them.
* **System Audit Log:** Immutable tracking of every `CREATE`, `UPDATE`, `DELETE`, and `LOGIN` action directly tied to user IDs and IPs.
* **Dynamic Reports:** Downloadable CSV exports for stock summaries, low stock warnings, and historical stock movements.
* **Serverless Ready:** Fully configured for single-click deployment to Vercel.

## 🛠️ Tech Stack
* **Frontend:** React.js, Vite, Tailwind CSS, React Context API.
* **Backend:** Node.js, Express.js, JWT Authentication.
* **Database:** MongoDB (with Mongoose ORM). Includes an automated fallback to `mongodb-memory-server` with auto-seeding for instant zero-config local testing.

## 📦 Local Development

1. **Clone the repository:**
```bash
git clone https://github.com/aryamansinghbca2023-ctrl/smart-inventory-management-system.git
cd smart-inventory-management-system
```

2. **Install all dependencies:**
There is a custom script in the root to install everything at once.
```bash
npm run install-all
```

3. **Start the applications:**
Open two terminal windows from the root directory:

**Terminal 1 (Backend):**
```bash
cd server
npm start
```

**Terminal 2 (Frontend):**
```bash
cd client
npm run dev
```

4. **Login:**
The database will automatically seed itself if it is empty. Log in at `http://localhost:5173` using:
* `admin@store.com` / `admin123`
* `manager@store.com` / `manager123`
* `employee@store.com` / `emp123`

## ☁️ Deployment (Vercel)

This monorepo is natively configured to be deployed as a unified application on Vercel.

1. Create a Free Cluster on [MongoDB Atlas](https://www.mongodb.com/atlas/database) and get your connection string.
2. Import this repository into Vercel.
3. Before deploying, add the following Environment Variables in Vercel:
   * `MONGO_URI`: Your MongoDB Atlas connection string *(Required, because Vercel Serverless wipes memory databases every 10 seconds)*
   * `JWT_SECRET`: Any secure random string
   * `JWT_EXPIRES_IN`: `7d`
4. Click **Deploy**. Vercel will automatically host your Vite frontend and wire the `/api` routes directly to your Node Serverless functions.

---
*Created by [Aryaman Singh](https://github.com/aryamansinghbca2023-ctrl) - 2026*
