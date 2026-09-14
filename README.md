# # Full-Stack E-Commerce Platform

Full-stack e-commerce application built with React/Vite/Tailwind, Node.js/Express, MongoDB/Mongoose, JWT and bcrypt.

## Features

### Customer
- Registration/login with bcrypt-hashed passwords
- Profile and saved shipping address
- Product browsing, search, category and brand filters
- Product details and stock availability
- Persistent shopping cart with quantity controls
- Checkout and database-backed order creation
- Order history, order details and delivery tracking

### Admin
- Protected admin dashboard
- Live products, customers, orders and revenue statistics
- Product CRUD, price/stock/featured management
- Category CRUD
- Brand CRUD
- Customer list
- View all customer orders and order details
- Update order status: `Pending → Processing → Shipped → Delivered`

### Dynamic catalog
Categories and brands are stored in MongoDB. Products reference their names, so catalog changes are reflected in customer filters and product management immediately. Renaming a category or brand also updates products using it; deletion is blocked while it is still in use.

## Run locally

### 1. Backend

```bash
cd backend
npm install
```

Copy `backend/.env.example` to `backend/.env` and set your MongoDB URI, JWT secret, and admin credentials.

Then seed the initial admin and products:

```bash
npm run seed
npm run dev
```

Backend: `http://localhost:5000`

### 2. Frontend

```bash
cd frontend
npm install
```

Copy `frontend/.env.example` to `frontend/.env` if needed, then:

```bash
npm run dev
```

Frontend: `http://localhost:5173`

## Admin login

Use the `ADMIN_EMAIL` and `ADMIN_PASSWORD` values configured in `backend/.env`. Run `npm run seed` after changing them.

## Deployment

Architecture:

`Vercel (React) → Render/Railway (Express API) → MongoDB Atlas`

### Backend
- Root directory: `backend`
- Build/install: `npm install`
- Start: `npm start`
- Configure `MONGODB_URI`, `JWT_SECRET`, `JWT_EXPIRES_IN`, `CLIENT_URL`, `ADMIN_EMAIL`, and `ADMIN_PASSWORD`.
- Run `npm run seed` once against the production database.

### Frontend
- Root directory: `frontend`
- Build: `npm run build`
- Output: `dist`
- Set `VITE_API_URL` to the deployed backend API URL ending in `/api`.

Do not commit `.env` files. Keep secrets only in the deployment provider's environment-variable settings.

## Testing checklist

1. Register a customer and log in.
2. Search for products.
3. Filter by category and brand.
4. Add products to the cart and change quantities.
5. Complete checkout and verify the order.
6. Log in as admin.
7. Add/edit/delete a category and brand.
8. Add/edit/delete a product and change its stock/price.
9. Verify customer-side catalog updates without hard-coded data.
10. Open all orders, view an order, and move it through the four statuses.
11. Verify dashboard revenue/order/customer/product counts.

No payment gateway is included; checkout creates a real database order and decrements stock inside a MongoDB transaction.
