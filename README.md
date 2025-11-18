# modern-web-activity-SPA(18-11-2025)

## Name: GOWSHIK S
## Reg NO: 212223220026

# AIM :
To develop a Single Page Application (SPA) using React and React Router that demonstrates protected nested routing

# Procedure:
1. Project setup

Initialize a Vite + React project (already prepared in the ZIP):

npm init vite@latest react-spa-dashboard --template react

cd react-spa-dashboard

npm install

Install dependencies:

react-router-dom for client routing:

npm install react-router-dom

2. Project structure (key files)
react-spa-dashboard/
├─ package.json
├─ index.html
└─ src/
   ├─ main.jsx            # React entry
   ├─ App.jsx             # Router setup + top-level layout
   ├─ styles.css
   ├─ pages/
   │  ├─ Home.jsx
   │  ├─ Login.jsx
   │  ├─ Dashboard.jsx    # contains <Outlet /> + sidebar links
   │  └─ dashboard/
   │     ├─ Profile.jsx
   │     ├─ Settings.jsx
   │     └─ Notifications.jsx
   └─ utils/
      ├─ auth.js          # demo auth helpers (login, logout, isLoggedIn)
      └─ ProtectedRoute.jsx

3. Routing approach

Use react-router-dom v6 routes in App.jsx.

Routes defined:

/ → Home

/login → Login

/dashboard → ProtectedRoute → Dashboard (nested)

/dashboard/profile → Profile

/dashboard/settings → Settings

/dashboard/notifications → Notifications

Dashboard contains a sidebar with NavLinks to the nested routes and an <Outlet /> to render the current nested page.

4. Protected routing & authentication

src/utils/auth.js implements a minimal fake auth using localStorage:

login(username, password) — saves demo user when both fields non-empty.

logout() — removes demo user.

isLoggedIn() — checks for demo user presence.

ProtectedRoute.jsx checks isLoggedIn():

If not logged in, redirects to /login using <Navigate to="/login" state={{from: location}} replace />.

If logged in, renders children (the dashboard component).

5. Login flow

Login.jsx contains a simple form for username/password.

On submit:

If both fields non-empty, call login() and navigate to /dashboard.

If previously logged in, redirect to dashboard.

6. Styling & UI

Minimal styles.css for layout:

Header with navigation (Home, Dashboard, Login/Logout).

Dashboard layout with sidebar and content card.

Focus is on functionality and routing, not on production-grade styling.

7. Development & run commands

From the project root:

npm install
npm run dev       # starts Vite dev server (usually at http://localhost:5173)
# or to use `npm start` (optional), add a "start": "vite" script to package.json then npm start

8. How to test the protected nested routes

Open browser to http://localhost:5173 — see Home page.

Click Dashboard — should redirect to /login because user is not authenticated.

Go to /login, enter any non-empty username and password → submit.

After login you should be redirected to /dashboard/profile (or /dashboard) and see the dashboard layout.

Click sidebar links to verify nested routes:

/dashboard/profile

/dashboard/settings

/dashboard/notifications

Click Logout — then try visiting /dashboard — you should be redirected back to /login.

# Output:

<img width="1914" height="719" alt="image" src="https://github.com/user-attachments/assets/557adc60-58f1-411c-9b20-ec7bb5980685" />

<img width="1917" height="549" alt="Screenshot 2025-11-18 105632" src="https://github.com/user-attachments/assets/238e2eac-be92-4072-b617-bcae8ea6eb5e">

# Result:
Describe the expected outputs and verification details after running the project.
