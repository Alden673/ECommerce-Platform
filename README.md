# 🛒 Full-Stack E-Commerce Platform

A full-stack e-commerce web application built with **React, Node.js, Express, and MongoDB**, designed to provide a complete online shopping experience with secure authentication, product discovery, shopping cart, checkout, order management, order tracking, and a role-based administration system.

## 🌐 Live Demo

**Live Website:**  
https://e-commerce-platform-nine-gilt.vercel.app/

**GitHub Repository:**  
https://github.com/Alden673/ECommerce-Platform

---

# ✨ Features

## 👤 Customer Features

- User registration and login
- Secure JWT-based authentication
- Password hashing using bcrypt
- Browse products
- Search products
- Filter products by category and brand
- View detailed product information
- View product stock availability
- Add products to shopping cart
- Increase and decrease cart quantities
- Remove products from cart
- Checkout
- Place orders
- View order history
- View individual order details
- Track order status
- Manage user profile

## 👨‍💼 Admin Features

- Secure admin authentication
- Role-based Admin/User access
- Admin dashboard
- View platform statistics
- Product CRUD operations
- Add, edit, and delete products
- Category management
- Brand management
- User management
- View customer orders
- View detailed order information
- Update order status
- Dynamic catalog management

## ⚙️ Backend Features

- RESTful API architecture
- MongoDB database integration
- Mongoose data modeling
- JWT authentication
- bcrypt password hashing
- Protected API routes
- Role-based authorization
- CORS configuration
- API rate limiting
- Security headers using Helmet
- Request logging using Morgan

---

# 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React.js, Vite, Tailwind CSS, React Router, Axios |
| Backend | Node.js, Express.js |
| Authentication | JWT, bcrypt |
| Database | MongoDB, Mongoose |
| Security | Helmet, Express Rate Limit, CORS |
| Deployment | Vercel, Render, MongoDB Atlas |

---

# 🏗️ System Architecture

```text
                    ┌──────────────────────┐
                    │     Customer/Admin   │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   React Frontend     │
                    │   Vite + Tailwind    │
                    └──────────┬───────────┘
                               │
                         REST API / HTTPS
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Express Backend    │
                    │      Node.js         │
                    └──────────┬───────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
       Authentication       Products          Orders
          & Users              API              API
              │                │                │
              └────────────────┼────────────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       MongoDB        │
                    │      Database        │
                    └──────────────────────┘
```

---

# 👤 Customer Workflow

The complete customer journey through the application:

```text
                         CUSTOMER
                            │
                            ▼
                  Open E-Commerce Website
                            │
                            ▼
                  ┌─────────────────────┐
                  │ Existing Account?   │
                  └──────────┬──────────┘
                             │
                   ┌─────────┴─────────┐
                   │                   │
                  YES                  NO
                   │                   │
                   ▼                   ▼
                 Login              Register
                   │                   │
                   └─────────┬─────────┘
                             │
                             ▼
                    JWT Authentication
                             │
                             ▼
                       Home / Products
                             │
                             ▼
                    Search / Filter
                             │
                             ▼
                    Select Product
                             │
                             ▼
                    Product Details
                             │
                             ▼
                       Add to Cart
                             │
                             ▼
                        View Cart
                             │
                   ┌─────────┴─────────┐
                   │                   │
                   ▼                   ▼
             Update Quantity      Remove Item
                   │                   │
                   └─────────┬─────────┘
                             │
                             ▼
                         Checkout
                             │
                             ▼
                     Confirm Order
                             │
                             ▼
                       Place Order
                             │
                             ▼
                     Order Created
                             │
                             ▼
                     Order History
                             │
                             ▼
                     Order Details
                             │
                             ▼
                    Track Order Status
                             │
                             ▼
                         Delivered
```

---

# 🛍️ Shopping Workflow

```text
              Browse Products
                    │
                    ▼
          ┌─────────────────────┐
          │ Search / Filtering  │
          └──────────┬──────────┘
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       Search     Category     Brand
                    Filter      Filter
          │          │          │
          └──────────┼──────────┘
                     │
                     ▼
              Product Details
                     │
                     ▼
                Add to Cart
                     │
                     ▼
                    Cart
                     │
              ┌──────┼──────┐
              ▼      ▼      ▼
           Increase Decrease Remove
           Quantity Quantity Product
              │      │      │
              └──────┼──────┘
                     │
                     ▼
                  Checkout
                     │
                     ▼
                Place Order
                     │
                     ▼
              Order Created
                     │
                     ▼
              Track Order
```

---

# 🔐 Authentication Workflow

```text
                     USER
                      │
                      ▼
               Register / Login
                      │
                      ▼
                  Auth API
                      │
                      ▼
             Validate Credentials
                      │
                      ▼
             Verify Password
                using bcrypt
                      │
                      ▼
                 Generate JWT
                      │
                      ▼
              Return JWT Token
                      │
                      ▼
            Authenticated Requests
                      │
                      ▼
               JWT Middleware
                      │
                      ▼
               Protected Routes
                      │
              ┌───────┴────────┐
              ▼                ▼
             USER             ADMIN
              │                │
              ▼                ▼
        User Features    Admin Features
```

---

# 👨‍💼 Admin Workflow

The complete administrator workflow:

```text
                         ADMIN
                           │
                           ▼
                      Admin Login
                           │
                           ▼
                  JWT Authentication
                           │
                           ▼
                 Admin Role Validation
                           │
                           ▼
                   Admin Dashboard
                           │
          ┌────────────────┼─────────────────┐
          │                │                 │
          ▼                ▼                 ▼
      PRODUCTS           USERS             ORDERS
          │                │                 │
          │                │                 ├── View Orders
          │                │                 │
          │                │                 ├── View Details
          │                │                 │
          │                │                 └── Update Status
          │                │
          │                ├── View Users
          │                │
          │                └── Manage Users
          │
          ├── Add Product
          │
          ├── Edit Product
          │
          └── Delete Product
          │
          ▼
       CATEGORIES
          │
          ├── Add Category
          ├── Edit Category
          └── Delete Category
          │
          ▼
         BRANDS
          │
          ├── Add Brand
          ├── Edit Brand
          └── Delete Brand
                           │
                           ▼
                    Backend REST API
                           │
                           ▼
                       MongoDB
                           │
                           ▼
                  Updated Application Data
                           │
                           ▼
                   Customer Application
```

---

# 🔄 Complete Customer + Admin Workflow

This diagram shows how customers and administrators interact with the same backend and database.

```text
                         ┌───────────────┐
                         │    USERS      │
                         └───────┬───────┘
                                 │
                 ┌───────────────┴───────────────┐
                 │                               │
                 ▼                               ▼
           ┌───────────┐                   ┌───────────┐
           │ CUSTOMER  │                   │   ADMIN   │
           └─────┬─────┘                   └─────┬─────┘
                 │                               │
                 ▼                               ▼
          React Frontend                  Admin Dashboard
                 │                               │
                 └───────────────┬───────────────┘
                                 │
                                 ▼
                       REST API / HTTPS
                                 │
                                 ▼
                    Node.js + Express Backend
                                 │
              ┌──────────────────┼──────────────────┐
              │                  │                  │
              ▼                  ▼                  ▼
       Authentication         Products            Orders
              │                  │                  │
              └──────────────────┼──────────────────┘
                                 │
                                 ▼
                            MongoDB
                                 │
                                 ▼
                       Updated Database Data
                                 │
                                 ▼
                    Express API Response
                                 │
                                 ▼
                       React Frontend
                                 │
                                 ▼
                       Updated UI / Data
```

---

# 🔄 Admin-to-Customer Dynamic Workflow

Admin changes to the catalog and orders are stored in the database and reflected dynamically on the customer side.

```text
ADMIN
  │
  ▼
Admin Dashboard
  │
  ├── Add / Edit / Delete Product
  │
  ├── Manage Categories
  │
  ├── Manage Brands
  │
  └── Manage Orders
  │
  ▼
Express REST API
  │
  ▼
MongoDB
  │
  ▼
Updated Database
  │
  ▼
Customer API Request
  │
  ▼
Updated Product / Catalog / Order Data
  │
  ▼
Customer Frontend
```

---

# 📦 Order Tracking Workflow

```text
Customer Places Order
        │
        ▼
   Order Created
        │
        ▼
      Pending
        │
        ▼
    Processing
        │
        ▼
     Shipped
        │
        ▼
    Delivered
```

The administrator can update the order status, while customers can view the latest status through their order history and order details.

---

# 📁 Project Structure

```text
ECommerce-Platform/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Layout.jsx
│   │   │   ├── ProductCard.jsx
│   │   │   ├── StatCard.jsx
│   │   │   └── Status.jsx
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── CartContext.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── admin/
│   │   │   │   ├── AdminDashboard.jsx
│   │   │   │   ├── AdminProducts.jsx
│   │   │   │   ├── AdminOrders.jsx
│   │   │   │   ├── AdminUsers.jsx
│   │   │   │   ├── AdminCatalog.jsx
│   │   │   │   └── AdminOrderDetails.jsx
│   │   │   │
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Products.jsx
│   │   │   ├── ProductDetails.jsx
│   │   │   ├── Cart.jsx
│   │   │   ├── Checkout.jsx
│   │   │   ├── Orders.jsx
│   │   │   ├── OrderDetails.jsx
│   │   │   └── Profile.jsx
│   │   │
│   │   ├── api.js
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── backend/
│   ├── src/
│   │   ├── middleware/
│   │   │   └── auth.js
│   │   │
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Product.js
│   │   │   ├── Category.js
│   │   │   ├── Brand.js
│   │   │   ├── Cart.js
│   │   │   └── Order.js
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── users.js
│   │   │   ├── products.js
│   │   │   ├── catalog.js
│   │   │   ├── cart.js
│   │   │   ├── orders.js
│   │   │   └── admin.js
│   │   │
│   │   ├── utils/
│   │   │   └── token.js
│   │   │
│   │   ├── seed.js
│   │   └── server.js
│   │
│   ├── package.json
│   └── .env.example
│
├── .gitignore
└── README.md
```

---

# 🚀 Running Locally

## 1. Clone the Repository

```bash
git clone https://github.com/Alden673/ECommerce-Platform.git
cd ECommerce-Platform
```

## 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file using `.env.example` and configure your environment variables.

Start the backend:

```bash
npm start
```

Backend:

```text
http://localhost:5000
```

## 3. Frontend Setup

Open another terminal:

```bash
cd frontend
npm install
```

Create a `.env` file:

```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend:

```bash
npm run dev
```

Frontend:

```text
http://localhost:5173
```

---

# 🔐 Environment Variables

## Backend

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d
CLIENT_URL=http://localhost:5173
ADMIN_EMAIL=your_admin_email
ADMIN_PASSWORD=your_admin_password
```

## Frontend

```env
VITE_API_URL=http://localhost:5000/api
```

> ⚠️ **Security:** Never commit `.env` files, MongoDB credentials, JWT secrets, passwords, or API keys to GitHub.

---

# 🌍 Deployment Architecture

The application is deployed using a cloud-based architecture.

```text
                         USER
                           │
                           ▼
                ┌────────────────────┐
                │  Vercel Frontend   │
                │ React + Vite       │
                └─────────┬──────────┘
                          │
                     HTTPS / API
                          │
                          ▼
                ┌────────────────────┐
                │  Render Backend    │
                │ Node + Express     │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │   MongoDB Atlas    │
                │     Database       │
                └────────────────────┘
```

### Deployment Responsibilities

**Vercel**
- Hosts the React frontend
- Serves the production web application

**Render**
- Hosts the Node.js/Express backend
- Provides REST API endpoints

**MongoDB Atlas**
- Stores users
- Stores products
- Stores categories
- Stores brands
- Stores carts
- Stores orders

---

# 📌 Project Highlights

- Full-stack MERN architecture
- Responsive e-commerce interface
- Secure authentication
- JWT-based authorization
- Role-based Admin/User access
- Dynamic product catalog
- Product search and filtering
- Category management
- Brand management
- Shopping cart functionality
- Checkout and order creation
- Order history
- Order tracking
- Admin dashboard
- Product management
- User management
- Order management
- RESTful backend APIs
- MongoDB database integration
- Production deployment
- Security middleware
- API rate limiting

---

# 🎯 Project Purpose

This project was developed as a practical **full-stack development and internship project** to demonstrate real-world experience in designing, developing, integrating, and deploying a complete e-commerce application.

The project demonstrates practical implementation of:

- Frontend development
- Backend API development
- Authentication
- Authorization
- Database integration
- CRUD operations
- Role-based access control
- Shopping cart management
- Order processing
- Order tracking
- Admin management
- Cloud deployment

---

# 👨‍💻 Author

**Alden Gomez**

Full-Stack Developer

**Technologies:**  
React • Node.js • Express • MongoDB • JavaScript • Tailwind CSS

---

# 🌐 Live Application

### E-Commerce Platform

https://e-commerce-platform-nine-gilt.vercel.app/

### GitHub Repository

https://github.com/Alden673/ECommerce-Platform
