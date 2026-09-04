# Teacher Nelly's Young Learners Academy — Final Setup

## Public website
- `index.html` is the public academy.
- Navigation is now: **Home | Learn | Practice | Games | Exams | Parent**.
- The public site does not contain an admin portal.
- Games are available to all visitors/classes and are not restricted by parent class access.

## Parent class access
- A parent registers a child with a phone number and class.
- After registration, the current parent session is restricted to the registered class level(s).
- A parent can use **Parent Access** with the same phone number + registered child name to restore access on another visit.
- If the same phone number has multiple registered children, the parent can access the class levels associated with that phone number.
- The curriculum does not show an **All Classes** option in parent mode.
- Opening a lesson outside the parent's registered class is blocked in the page logic.

## Netlify environment variables
Create these in Netlify Project configuration → Environment variables:

- `ADMIN_OWNER_USERNAME` — your chosen owner username
- `ADMIN_OWNER_PASSWORD` — a new strong password (10+ characters)
- `SESSION_SECRET` — a long random secret string

Do not put these values inside HTML, JavaScript, or GitHub.

## Deploy
Deploy the whole project folder, including:
- `index.html`
- `admin.html`
- `netlify.toml`
- `package.json`
- `netlify/functions/academy-api.mjs`

After changing environment variables, redeploy the site.

- The Admin Accounts tab lets the owner add staff administrators, reset staff passwords, and remove staff. The Security tab changes the signed-in admin password.
- The dashboard uses the server session cookie; keep `SESSION_SECRET` configured in Netlify.
