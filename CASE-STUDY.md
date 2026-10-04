# Relic: secondhand looks from your Pinterest board

**Role:** Product, design and build (built with Claude as an AI pair)
**Stack:** HTML, CSS, vanilla JavaScript, one serverless function (Vercel), Claude API
**Live:** [add your link]

## The problem
Pinterest outfits are easy to save and hard to afford, and fast fashion is the usual way to copy them. In India, thrift is huge but scattered: street bazaars, Instagram thrift pages and resale listings, with no easy way to translate an outfit into things you can actually find.

## The idea
Relic turns the outfits you pin into a thrift shopping plan. Describe an outfit or upload a photo and Relic returns the pieces, what to check on each (fabric, cut, condition), where to hunt in your city, a realistic price in rupees and how to bargain.

## Built for Indian shoppers
- Prices and budgets in rupees (₹500 to ₹5,000 per outfit)
- City guides for eight cities, and suggestions for street markets as well as OLX, Facebook Marketplace and Instagram thrift pages
- Plans in English, Hindi or Hinglish
- Climate-aware fabrics, bargaining tips and darzi (tailor) alteration advice

## Key decisions
- **Search links, not fake listings.** Each piece links to live searches on OLX, Facebook Marketplace, Instagram and Google rather than invented product URLs.
- **No invented shop names.** The AI is told to name types of places, and the Guide lists well-known markets that I verified.
- **Server-side API key.** A small function holds the key and rate-limits each visitor.
- **Single-item input.** Typing just "low rise jeans" builds a complete outfit around it, after early testing showed short prompts broke the first version.

## What I learned
Prompt design and output parsing mattered as much as the UI: structured JSON, forgiving parsing and clear error messages. Localisation (currency, markets, language) changed the product far more than visual polish.

## Next
Saved wishlists, price tracking across listings, a community board for finds, and more cities.
