# 🛒 Full-Stack E-Commerce Platform

A full-stack e-commerce web application built with **React, Node.js, Express, and MongoDB**, designed to provide a complete online shopping experience with secure authentication, product discovery, shopping cart, checkout, order tracking, and a role-based administration system.

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
                 ┌─────────────┼─────────────┐
                 │             │             │
                 ▼             ▼             ▼
          Authentication    Products       Orders
             & Users           API           API
                 │             │             │
                 └─────────────┼─────────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       MongoDB        │
                    │      Database        │
                    └──────────────────────┘
