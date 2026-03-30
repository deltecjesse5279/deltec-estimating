[README.md](https://github.com/user-attachments/files/26359284/README.md)
# Deltec Estimating App

Electrical estimating web app for Deltec Electrical Ltd.

## Local development

```bash
npm install
node server.js
# Open http://localhost:3000
```

## Deploy to Render.com

1. Push this repo to GitHub
2. Go to render.com → New → Web Service
3. Connect your GitHub repo
4. Set these values:
   - **Build command:** `npm install`
   - **Start command:** `node server.js`
5. Add environment variables:
   - `APP_USER` = your username (default: `deltec`)
   - `APP_PASSWORD` = your chosen password
6. Click Deploy

### ✅ Recommended: Add a PostgreSQL database (prevents data loss on redeploy)

1. In Render dashboard → New → PostgreSQL (free tier available)
2. Once created, copy the **Internal Database URL**
3. In your Web Service → Environment → add:
   - `DATABASE_URL` = (paste the Internal Database URL)
4. Redeploy — the app will auto-create the `estimates` table

Without `DATABASE_URL`, the app falls back to file storage (`data/estimates.json`),
which is wiped on every Render redeploy.

## Environment variables

| Variable       | Default      | Description                          |
|----------------|--------------|--------------------------------------|
| `APP_USER`     | `deltec`     | Login username                       |
| `APP_PASSWORD` | `deltec2024` | Login password                       |
| `DATABASE_URL` | *(none)*     | Postgres URL — enables persistent storage |
| `PORT`         | `3000`       | Server port (auto-set by Render)     |

## What's in this repo

| File/Folder          | Purpose                              |
|----------------------|--------------------------------------|
| `server.js`          | Express backend + estimates API      |
| `public/index.html`  | Full single-page estimating app      |
| `package.json`       | Node dependencies                    |

## Notes

- On Render free tier, the server sleeps after 15 min of inactivity (~30s cold start)
- Upgrade to a paid Render plan ($7/mo) to keep it always-on
