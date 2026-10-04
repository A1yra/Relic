# Relic: deploy guide

Static site (`public/index.html`) + one serverless function (`api/plan.js`) that calls Claude with your API key.

## 1. Get an API key
1. Create an account at console.anthropic.com and add billing.
2. Create an API key and set a monthly spend limit.

## 2. Put the code on GitHub
Create a new repo and upload this whole folder (keep `api/`, `public/`, `vercel.json`).

## 3. Deploy on Vercel (free plan works)
1. Sign in at vercel.com with GitHub, click **Add New > Project**, and import the repo.
2. Under **Environment Variables** add:
   - `ANTHROPIC_API_KEY` = your key (never put it in the HTML)
   - optional `PLANS_PER_HOUR` = 5 (plans per visitor per hour)
   - optional `ANTHROPIC_MODEL` = a current model name from Anthropic's docs
3. Click **Deploy**. You get a link like `relic.vercel.app`.

## 4. Custom domain (optional)
Vercel project > Settings > Domains. Buy something like relic.in from a registrar and follow the DNS steps shown.

## 5. Before sharing widely
- The rate limiter is in-memory and best-effort. For strict limits use Upstash Redis or Vercel KV.
- Keep your Anthropic spend limit low at first and watch the usage page.
- Test with and without photos on a phone.
- Check the market names in the Guide tab yourself; they were written from general knowledge.

## Local test
`npm i -g vercel`, add `ANTHROPIC_API_KEY` to a `.env` file, then run `vercel dev`.
