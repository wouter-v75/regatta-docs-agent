# ⛵ Regatta Abstract Agent

AI-powered tool that reads Notice of Race, Sailing Instructions, Amendments and Notices and produces a structured abstract — with optional year-on-year rule change comparison.

## Deploy to Vercel (5 minutes)

### 1. Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/regatta-agent.git
git push -u origin main
```

### 2. Import to Vercel

1. Go to [vercel.com/new](https://vercel.com/new)
2. Import your GitHub repo
3. Click **Deploy** (no build settings needed)

### 3. Add your Anthropic API key

1. In your Vercel project → **Settings → Environment Variables**
2. Add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-...` (your key from [console.anthropic.com](https://console.anthropic.com/settings/keys))
3. Click **Save**, then **Redeploy**

Your app is live at `https://your-project.vercel.app` 🎉

---

## Project structure

```
regatta-agent/
├── api/
│   └── analyse.js      ← Serverless proxy (keeps API key secret)
├── public/
│   └── index.html      ← Full frontend
├── vercel.json         ← Routing config
└── package.json
```

## Features

- Upload PDF, TXT, DOC files (NOR, SI, Amendments, Notices)
- Extracts: Rules, Schedule, Scoring, VHF channels, OCS rules, Penalty turns
- Every finding cited with exact section reference (e.g. SI 3.1)
- Upload last year's SIs to get a **year-on-year rule change diff** (NEW / MODIFIED / REMOVED)
- Print / Save as PDF button
