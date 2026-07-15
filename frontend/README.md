# ChurnSense-Ai Frontend

This is the React + Vite frontend for the customer churn prediction dashboard. It provides the user interface for onboarding, customer assessment, prediction results, analytics, and settings.

## What this app does

The frontend allows users to:
- view the landing page and navigate the product
- log in to the dashboard experience
- submit customer assessment data for churn prediction
- view predicted churn risk and recommendations
- browse analytics and historical prediction results
- manage basic app settings and theme preferences

## Tech stack

- React 19
- TypeScript
- Vite
- React Router
- Axios for API communication
- Recharts for charts and analytics
- Tailwind-style styling via the existing UI setup
- Lucide icons and motion utilities

## Prerequisites

Make sure you have:
- Node.js installed
- The backend server running on port 5000

## Local setup

1. Go to the frontend folder:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

The app will usually open at:
- http://localhost:3000

## Environment variables

Create a local environment file if needed and set the API base URL:

```env
VITE_API_BASE_URL=http://localhost:5000/api
```

If this variable is not set, the app will use the default backend URL.

## Useful scripts

- `npm run dev` - start the local development server
- `npm run build` - create a production build
- `npm run preview` - preview the production build locally
- `npm run lint` - run TypeScript checking

## Project structure

- `src/pages/` - route pages such as Landing, Login, Dashboard, PredictionResult, Analytics
- `src/components/` - reusable UI components like Navbar and Sidebar
- `src/context/` - theme, authentication, and data context providers
- `src/services/` - API integration logic
- `src/routes/` - application routing setup

## Notes

The frontend depends on the backend API for prediction results. If the backend is not running, the app may show errors when submitting assessment data.

---

Jiya Saraswat

Frontend Development • UI Design • React + TypeScript • Vite Integration • API Interaction • User Experience
