# React SPA Dashboard (Vite)

This is a small demo React single-page application using **React Router v6** and protected nested routes.

## Features
- Home, Login pages
- Dashboard with nested routes: Profile, Settings, Notifications
- Protected routing (simple localStorage-based fake auth)
- Vite dev server

## Run locally
1. Install dependencies:
   ```bash
   npm install
   ```
2. Start dev server:
   ```bash
   npm run dev
   ```
3. Open http://localhost:5173

## Notes
This project uses a minimal fake authentication for demo purposes (any non-empty username/password will log you in). Do not use this auth mechanism in production.
