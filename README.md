# Deltec Estimating App

Electrical estimating web app for Deltec Electrical Ltd.

## Local development

```bash
npm install
node server.js
# Open http://localhost:3000
```

## Deploy to Render.com (free)

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

Your app will be live at `https://your-app-name.onrender.com`

## Environment variables

| Variable | Default | Description |
|---|---|---|
| `APP_USER` | `deltec` | Login username |
| `APP_PASSWORD` | `deltec2024` | Login password |
| `PORT` | `3000` | Server port (auto-set by Render) |

## Notes

- Estimates are saved to `data/estimates.json` on the server
- On Render free tier, the server sleeps after 15 min of inactivity (first request after sleep takes ~30s)
- Upgrade to a paid Render plan ($7/mo) to keep it always-on
