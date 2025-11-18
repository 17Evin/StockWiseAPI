# Inventory Management System

## Overview
A modern web-based inventory management system built with React, Express, and PostgreSQL. Features real-time product tracking, CRUD operations, low stock alerts, and a professional Linear-inspired interface.

## Tech Stack
- **Frontend**: React, Tailwind CSS, Shadcn UI, React Query, Wouter
- **Backend**: Node.js, Express.js
- **Database**: PostgreSQL with Drizzle ORM
- **Architecture**: RESTful API, MVC pattern, DAO pattern

## Project Structure
```
├── client/src/
│   ├── components/
│   │   ├── ui/                    # Shadcn UI components
│   │   ├── app-sidebar.tsx        # Navigation sidebar
│   │   ├── product-form-dialog.tsx
│   │   ├── delete-confirmation-dialog.tsx
│   │   ├── theme-provider.tsx
│   │   └── theme-toggle.tsx
│   ├── pages/
│   │   ├── dashboard.tsx          # Dashboard with stats
│   │   └── products.tsx           # Product listing & management
│   └── App.tsx
├── server/
│   ├── db.ts                      # Database connection
│   ├── storage.ts                 # DAO layer
│   └── routes.ts                  # API endpoints
└── shared/
    └── schema.ts                  # Drizzle schemas & Zod validation
```

## Features
- ✅ Product CRUD operations (Create, Read, Update, Delete)
- ✅ Dashboard with inventory statistics
- ✅ Low stock alerts and status badges
- ✅ Search and filter products
- ✅ Responsive design (mobile, tablet, desktop)
- ✅ Dark mode support
- ✅ Real-time inventory tracking
- ✅ Form validation with Zod
- ✅ PostgreSQL database persistence

## Database Schema
**Products Table:**
- `id` (UUID, primary key)
- `name` (text, required)
- `description` (text, optional)
- `quantity` (integer, required, default: 0)
- `price` (numeric, required)
- `category` (text, optional)
- `sku` (text, required, unique)

## API Endpoints
- `GET /api/products` - Get all products
- `POST /api/products` - Create a new product
- `PATCH /api/products/:id` - Update a product
- `DELETE /api/products/:id` - Delete a product

## Running the Project
1. Database is automatically provisioned
2. Run `npm run dev` to start the application (starts automatically via workflow)
3. Frontend and backend run on the same port via Vite proxy

## Design System
- **Font**: Inter
- **Colors**: Linear-inspired blue primary, neutral grays
- **Components**: Shadcn UI with custom theming
- **Spacing**: Consistent 2/4/6/8 Tailwind units
- **Layout**: Sidebar navigation with main content area
