# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- **Start development server**: `npm run dev` or `yarn dev` (runs on http://localhost:5173)
- **Build for production**: `npm run build` or `yarn build` (TypeScript compilation + Vite build)
- **Lint code**: `npm run lint` or `yarn lint` (ESLint with TypeScript rules)
- **Preview production build**: `npm run preview` or `yarn preview`
- **Run E2E tests**: `npx cypress open` or `npx cypress run` (Cypress tests available)

## Architecture Overview

This is a React TypeScript e-commerce application built with modern frontend technologies:

### State Management
- **Redux Toolkit** is used for global state management
- Store configuration: `src/redux/store.ts`
- Four main slices:
  - `authSlice`: User authentication state and login modal
  - `cartSlice`: Shopping cart items and cart visibility
  - `productSlice`: Product data and loading states
  - `homeSlice`: Homepage-specific state
- Redux hooks are centralized in `src/redux/hooks.ts`

### Project Structure
- **Components**: Reusable UI components in `src/components/`
- **Pages**: Top-level route components in `src/pages/`
- **Models**: TypeScript interfaces and types in `src/models/`
- **Hooks**: Custom React hooks in `src/hooks/`
- **Redux**: State management files in `src/redux/`

### Key Features
- **Authentication**: Hardcoded demo login (username: "atuny0", password: "9uQFF1Lh")
- **Cart Management**: Add/remove items, quantity control, persistent state
- **Product Catalog**: Product listing, categories, single product views
- **Protected Routes**: Wishlist and profile pages require authentication
- **Responsive Design**: Tailwind CSS for styling

### Data Source
- Uses DummyJSON API (https://dummyjson.com/) for product data
- No backend - purely frontend demo application

### Authentication System
- Simple localStorage-based authentication
- Login state persists across sessions
- `useAuth` hook for requiring authentication before actions
- `ProtectedRoute` component wraps authenticated pages

### Custom Hooks
- `useAuth`: Handles authentication requirements and login modal
- `useDiscount`: Calculates discounted prices

### Testing
- Cypress E2E tests in `cypress/e2e/`
- Tests cover: home page, products, cart, navbar, single product views
- Base URL configured for localhost:5173

## Development Notes

- Uses Vite for fast development and building
- TypeScript with strict configuration
- ESLint configured for React and TypeScript
- Tailwind CSS for styling with PostCSS
- React Router for navigation
- React Hot Toast for notifications
- React Icons for UI icons