
# 🛍️ Headless E-commerce Platform

A modern, flexible, and scalable headless commerce solution built with React, Next.js, Node.js, and Stripe. Designed as an alternative to traditional platforms like Shopify or WooCommerce, this architecture gives you full control over the customer experience and backend logic.

---

## ✨ Features

- 🛒 **Product Catalog**: Display products with search, filters, and categories
- 🧾 **Stripe Checkout Integration**: Secure, responsive checkout via Stripe
- 📦 **Cart System**: Add/remove products, view totals, checkout
- 👨‍💼 **Admin Panel**: Role-based access to manage products and view orders
- 📋 **Order Tracking**: Users can view order history and status
- 🔍 **Search & Filtering**: Full-text search and filters by category, price, tags
- 💳 **Secure Payments**: Stripe webhooks for real-time payment and order status
- 📊 **Dashboard**: Admin analytics for sales, orders, and inventory
- 🌐 **Headless API Design**: Use REST endpoints for full decoupling between backend and frontend

---

## 🗂️ Project Structure

```
headless-ecommerce-platform/
├── backend/                # Node.js + Express + MongoDB API
│   ├── controllers/        # Logic for products, orders, admin
│   ├── models/             # Mongoose models (Product, Order, User)
│   ├── routes/             # REST API endpoints
│   ├── middleware/         # JWT auth, error handlers
│   ├── utils/              # Stripe helpers, data validators
│   └── server.js           # API entry point
│
├── frontend/               # Next.js + React Storefront
│   ├── public/             # Static assets
│   ├── src/
│   │   ├── components/     # UI components (ProductCard, Navbar, etc.)
│   │   ├── pages/          # Next.js pages: /products, /cart, /checkout
│   │   ├── store/          # Zustand store for cart and auth state
│   │   ├── utils/          # Stripe integration, API fetchers
│   │   ├── App.jsx         # Application wrapper
│   │   └── main.jsx        # Root entry
│
├── README.md               # Project setup, flow, and author info
└── package.json            # (Optional) workspace-wide config
```

---

## 🚀 Setup Instructions

### 1. Clone & Navigate
```bash
git clone https://github.com/your-repo/headless-ecommerce-platform.git
cd headless-ecommerce-platform
```

### 2. Backend Setup
```bash
cd backend
npm install
# Create a .env file:
# MONGO_URI=mongodb://localhost:27017/ecommerce
# JWT_SECRET=supersecret
# STRIPE_SECRET_KEY=sk_test_xxxx
# FRONTEND_URL=http://localhost:3000
node server.js
```

### 3. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

---

## 🔁 Code Flow

### 🔐 Authentication
- JWT-based authentication
- Role: `admin` and `customer`
- Middleware `auth.js` protects sensitive routes (e.g. order list, product edit)

### 📦 Product Catalog
- Products fetched from `/api/products`
- Search via query param
- Admin can add/edit/delete products through dashboard

### 🛒 Cart + Stripe Checkout
- Zustand used to store cart state across pages
- Checkout initiates Stripe session via `/api/checkout`
- Stripe redirects to hosted checkout and then back to success page
- Stripe webhooks notify backend on successful payment

### 📋 Orders
- Orders are created after Stripe checkout completes
- Each order stored in DB with reference to user
- Users can view order history and admins can see all orders

---

## 🧪 Seed/Test Data

- On backend init, test products and users can be seeded
- Run:
```bash
node utils/seed.js
```

---

## 📧 Author Information

**Author**: Ravi Chauhan  
**Email**: ravischauhan007@gmail.com  
**Contact**: +91 97222 73666

---

## 📘 License

This project is open source and can be freely used or extended for personal, educational, or commercial purposes.

---

Happy Selling! 🚀
