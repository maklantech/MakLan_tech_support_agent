# CT Tech-Pro Assistant - Deployment Guide

## Overview
AI-powered technical assistant for CertainTeed roofing products, backed by the Master Shingle Applicator's Manual (16th Edition).

## Project Structure
```
ct-techpro-app/
├── api/
│   └── chat.js          # Serverless API endpoint (keeps API key secure)
├── public/
│   └── index.html       # Frontend application
├── package.json         # Dependencies
├── vercel.json          # Vercel configuration
└── README.md            # This file
```

## Deployment Steps (Vercel)

### 1. Prerequisites
- GitHub account
- Vercel account (free at vercel.com)
- Anthropic API key

### 2. Push to GitHub
```bash
# Create a new repo on GitHub, then:
git init
git add .
git commit -m "Initial CT Tech-Pro Assistant"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ct-techpro-app.git
git push -u origin main
```

### 3. Deploy to Vercel
1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "Add New Project"
3. Import your GitHub repository
4. Configure environment variables:
   - Click "Environment Variables"
   - Add: `ANTHROPIC_API_KEY` = your Anthropic API key
5. Click "Deploy"

### 4. Get Your Live URL
After deployment, Vercel will give you a URL like:
`https://ct-techpro-app.vercel.app`

## Adding Password Protection (Optional)

### Option A: Vercel Authentication (Team Plan)
In Vercel dashboard: Settings → Security → Password Protection

### Option B: Cloudflare Access (Free)
1. Add your domain to Cloudflare
2. Go to Zero Trust → Access → Applications
3. Create application with email allowlist

### Option C: Simple Password in Code
I can add a login screen to the frontend if needed.

## Updating the System Prompt
Edit `api/chat.js` and redeploy. The system prompt contains all the technical knowledge.

## Adding New Documents (TDS, TIS)
1. Add document links to `CHAPTER_PDFS` in `public/index.html`
2. Update system prompt in `api/chat.js` with new specifications
3. Commit and push - Vercel auto-deploys

## Embedding on Customer Websites (Future)
The app can be embedded via iframe:
```html
<iframe src="https://your-app.vercel.app" width="100%" height="600px"></iframe>
```

For white-label versions, we can create separate deployments with different branding.

## Support
- CertainTeed Technical Services: 800-345-1145
- App Issues: [Your contact info]
