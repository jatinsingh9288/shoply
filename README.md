# Shoply

Shoply is a full-stack e-commerce web app. Users can browse products, add them to a cart or wishlist, and pay online with Stripe. Admins get a dashboard to manage products, orders and users.

The frontend is built with React and the backend is a REST API built with Node.js, Express and MongoDB.

## Features

- Register and login (passwords hashed, login handled with JWT)
- Browse products with filtering and sorting
- Product details page with customer reviews
- Cart (add, remove, clear)
- Wishlist
- Checkout with Stripe (test mode)
- Order placement after payment
- Admin dashboard to add, edit and delete products, view orders, and manage users
- Responsive layout

## Tech Stack

**Frontend:** React, Redux Toolkit, React Router, Material UI, Bootstrap, Styled Components, Formik, Yup, Axios

**Backend:** Node.js, Express, MongoDB, Mongoose, JSON Web Tokens, bcryptjs, express-validator

**Payments:** Stripe Checkout

## Project Structure

```
shoply/
├── client/    # React app
└── server/    # Express API
```

## Getting Started

### What you need

- [Node.js](https://nodejs.org/) (v16 or newer)
- MongoDB, either installed locally or a free [MongoDB Atlas](https://www.mongodb.com/atlas) cluster
- A [Stripe](https://stripe.com/) account for test API keys (only needed for checkout)

### 1. Clone the repo

```bash
git clone https://github.com/<your-username>/shoply.git
cd shoply
```

### 2. Set up the backend

```bash
cd server
npm install
```

Create a `.env` file in the `server` folder (you can copy `.env.example`) and fill in your values:

```
PORT=8080
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=any_random_secret_string
STRIPE_SECRET_KEY=your_stripe_test_secret_key
```

Start the server:

```bash
npm run dev
```

The API runs on `http://localhost:8080`. On the first run, when the database is empty, it adds some sample products and two demo users automatically.

### 3. Set up the frontend

Open a new terminal:

```bash
cd client
npm install
```

Create a `.env` file in the `client` folder (you can copy `.env.example`):

```
REACT_APP_API_URL=http://localhost:8080/
```

Keep the `/` at the end of the URL, because the code adds the API paths directly after it.

Start the app:

```bash
npm start
```

The app opens at `http://localhost:3000`.

## Demo Accounts

These are created by the sample data when the database is empty:

| Role  | Email             | Password   |
| ----- | ----------------- | ---------- |
| Admin | admin@example.com | Admin@54321 |
| User  | john@example.com  | John@54321  |

## Testing Payments

Checkout runs in Stripe test mode. Use the test card `4242 4242 4242 4242` with any future expiry date, any CVC and any ZIP code. No real money is charged.

## Scripts

**client**

| Command         | What it does                  |
| --------------- | ----------------------------- |
| `npm start`     | Runs the app in development   |
| `npm run build` | Creates a production build    |

**server**

| Command       | What it does                              |
| ------------- | ----------------------------------------- |
| `npm run dev` | Runs the API with nodemon (auto-restarts) |
| `npm start`   | Runs the API with node                    |
