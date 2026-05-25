# Affiliate++ (SaaS Affiliate Link Management Platform)

An all-in-one SaaS-based Affiliate Link Management Platform designed for content creators, affiliate marketers, freelancers, and small businesses. The platform simplifies link organization, optimizes click attribution, provides real-time geographic and device analytics, and facilitates role-based collaboration for teams, alongside integrated credit-based and subscription payment options.

---

## 📂 Repository Structure

The project is organized as a monorepo consisting of a separate React frontend and a Node.js/Express backend:

```text
.
├── client/                     # React Frontend
│   ├── public/                 # Static assets & index.html
│   ├── src/                    # React Source code
│   │   ├── components/         # Reusable UI components (e.g., UnauthorizedAccess)
│   │   ├── config/             # Endpoints and payment configuration (Razorpay keys)
│   │   ├── layout/             # Shared wrappers (Header, Footer, Layout)
│   │   ├── pages/              # Page components (Home, Login, Register, Dashboards)
│   │   │   ├── links/          # Link Management & Analytics Dashboards
│   │   │   ├── payments/       # Credit pack and Subscription flows (Razorpay)
│   │   │   └── users/          # Subordinate User management (Admin only)
│   │   ├── rbac/               # Role-Based Access Control logic (Can helper, ProtectedRoute)
│   │   ├── redux/              # Store configuration and user slice
│   │   ├── App.js              # Application routes & session initialization
│   │   └── index.js            # Frontend mount entry point
│   ├── package.json            # Frontend dependency and scripts configuration
│   └── README.md               # Frontend-specific documentation
│
├── server/                     # Node.js & Express Backend
│   ├── scripts/                # Database/User seeding scripts (e.g., addUser.js)
│   ├── src/                    # Backend Source Code
│   │   ├── constants/          # Permissions arrays, user roles, payment packages
│   │   ├── controller/         # Request handling logic (auth, links, payments, users)
│   │   ├── middleware/         # Security, validation, and RBAC middlewares
│   │   ├── model/              # MongoDB Models (Users, Links, Clicks)
│   │   ├── routes/             # Express API Endpoints
│   │   ├── service/            # Third-party integrations (Cloudinary, Nodemailer)
│   │   └── util/               # Cryptography and metadata extraction utilities
│   ├── server.js               # Express application setup & database connection entry point
│   └── package.json            # Backend dependency configuration
│
├── prompt.md                   # Technical prompt and requirements document
├── justification.md            # Document intended for design justification details
└── README.md                   # Root documentation (this file)
```

---

## ⚙️ Instructions for Running the Code

### 1. Prerequisites
Ensure you have the following installed on your machine:
- **Node.js** (v16.x or higher)
- **MongoDB** (Local instance running on port 27017 or a MongoDB Atlas connection string)
- **Razorpay Developer Account** (For subscription and payment gateway keys)
- **Cloudinary Account** (For image/thumbnail hosting)
- **Gmail SMTP Credentials** (With App Passwords enabled, for automated emails)

---

### 2. Environment Setup

Configure environment variables in both directories to allow integration services to connect successfully.

#### A. Backend Setup (`server/.env`)
Create a `.env` file inside the `server/` directory and populate it with the following:
```env
PORT=5001
MONGO_URI=mongodb://localhost:27017/affiliate_platform
JWT_SECRET=your_jwt_access_secret_key
JWT_REFRESH_TOKEN_SECRET=your_jwt_refresh_token_secret_key
GOOGLE_CLIENT_ID=your_google_client_id.apps.googleusercontent.com
GMAIL_EMAIL_ID=your_gmail_email@gmail.com
GMAIL_APP_PASSWORD=your_gmail_app_password
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
RAZORPAY_WEBHOOK_SECRET=your_razorpay_webhook_secret
RAZORPAY_YEARLY_PLAN_ID=your_yearly_plan_id
RAZORPAY_MONTHLY_PLAN_ID=your_monthly_plan_id
NODE_ENV=development
```

#### B. Frontend Setup (`client/.env`)
Create a `.env` file inside the `client/` directory and populate it with:
```env
REACT_APP_SERVER_ENDPOINT=http://localhost:5001
REACT_APP_GOOGLE_CLIENT_ID=your_google_client_id.apps.googleusercontent.com
REACT_APP_RAZORPAY_KEY_ID=your_razorpay_key_id
```

---

### 3. Executing the Application

#### Step 1: Install and Run the Backend Server
```bash
cd server
npm install
node server.js
```
The server will boot and display `Server is running at http://localhost:5001` and `MongoDB Connected`.

#### Step 2: Install and Run the Frontend Client
Open a separate terminal window:
```bash
cd client
npm install
npm start
```
The React development server will start at `http://localhost:3000`.

---

## 🧪 Testing the Application

### Running Frontend Tests
Frontend tests are powered by **Jest** and **React Testing Library**. You can initiate the test runner in watch mode:
```bash
cd client
npm run test
```

### Manual API Testing
For backend endpoints, you can import and test routes via Postman, Thunder Client, or cURL.
Key testing routes:
1. **User Sign Up & Login**: `POST /auth/register` and `POST /auth/login`
2. **Access token verification**: `POST /auth/is-user-logged-in`
3. **Link Creation**: `POST /links` (Requires Bearer Token/Cookie)
4. **URL Redirection**: `GET /links/r/:id` (Accessing this in the browser redirects to the target destination while logging click statistics)

---

## 📈 Evaluation Methodology

The system's features and robustness are evaluated based on the following multi-dimensional criteria:

### 1. Functional Authentication & Session Integrity
- **JWT & OAuth Validation**: Tested to ensure OAuth credentials (via Google login) exchange profiles cleanly and resolve to registered accounts, and that forgot/reset password codes expire within their set threshold.
- **Persistent Sessions**: Verified that refresh tokens correctly keep users logged in across page reloads without forcing credential re-entry, while keeping access tokens stateless.

### 2. Role-Based Access Control (RBAC)
- **Role Limits**: Validated that `admin`, `developer`, and `viewer` accounts receive proper UI visibility and endpoint restrictions:
  - **Admin**: Has full CRUD control over users and links.
  - **Developer**: Restricted from creating/deleting links and modifying user bases.
  - **Viewer**: Read-only permissions on designated assets.
- **Middleware Guarding**: Verified that invoking illegal requests manually on backend routes (e.g., `POST /users` from a `developer` account) triggers an HTTP `403 Forbidden` response.

### 3. Click Tracking & IP Geolocation Parsing
- **Local Fallback Testing**: During development, IP resolving falls back to Google's public DNS IP (`8.8.8.8`) to verify location mapping queries via the HTTP-based `ip-api.com` service without crashing the redirection workflow.
- **Device & Browser Sniffing**: Verified that the click log parses distinct mobile vs. desktop user-agent strings, tracking and populating statistics charts.

### 4. Subscription & Credit Consumption Flow
- **Credit Debits**: Validated that link generation deducts `1 credit` from standard accounts, but proceeds without deduction for accounts with active unlimited subscriptions.
- **Webhook Integration Security**: Tested webhook verification logic using SHA256 HMAC comparisons against the `x-razorpay-signature` header to ensure unauthorized agents cannot forge success events to credit users artificially.
