# Metro-X

Metro-X is connected to the Supabase backend in `DaveAust1n's Project`.

## Backend connection
- Supabase project: `xfguwqqhfktnbfsipyor`
- Supabase URL: `https://xfguwqqhfktnbfsipyor.supabase.co`
- API Edge Function: `https://xfguwqqhfktnbfsipyor.supabase.co/functions/v1/api`
- Frontend auth: Supabase Auth
- API authentication: Supabase access token in `Authorization: Bearer ...`

The local `.env.local` file contains the Supabase publishable key needed by the frontend. It is ignored by Git via `*.local`.

## Current API integration
- Auth: login, signup, session restore, logout, password reset
- Posts: list, get, create, update, schedule, cancel, delete
- X accounts: list and disconnect

The deployed `api` Edge Function currently returns data wrapped as `{ data: ... }`, and the frontend services have been updated to unwrap that response correctly.

## Important limitation
X OAuth account connection and actual X publishing are not implemented in the deployed Edge Function yet. Those endpoints intentionally return `501 Not Implemented` until the X OAuth/publishing layer is added.

## Run locally

```bash
npm install
npm run dev
```

If the project is moved to a new environment, recreate the three Vite variables from `.env.example`.
