# Itret Zehra — Portfolio Site

Live site: https://itretzehra-max.github.io/

A personal portfolio site for Itret Zehra, a Statistics graduate and Business Analytics student transitioning into business analysis. Built as part of the FlyRank AI Fluency internship, General AI Fluency track.

## What it does, and who it's for

This is a three-page static portfolio site:

- **Home** (`index.html`) — introduction, a proof statement, and role highlights
- **Work** (`projects.html`) — two case studies with real worked examples and quantified output (see Eval Results below)
- **Contact** (`contact.html`) — a working contact form, CV download, booking link, and social links

It's built for two audiences:
1. **Recruiters / hiring managers** evaluating fit for business analyst roles
2. **Anyone verifying the FlyRank internship work** — the site itself is one of the track deliverables, and its footer links to the FlyRank verification page

## Setup

No build step — this is plain HTML, CSS, and a small amount of JavaScript (for the contact form and analytics beacon).

To run it locally:
1. Clone the repo: `git clone https://github.com/itretzehra-max/itretzehra-max.github.io.git`
2. Open `index.html` directly in a browser, or serve the folder with any static server (e.g. `python3 -m http.server`)

To deploy: push to the `main` branch — GitHub Pages auto-builds and publishes from the repo root.

## Usage examples

- Visit the live site and click through Home → Work → Contact to see the full flow
- Submit the contact form on the Contact page — it sends a real message via Formspree to the site owner's inbox
- Click the FlyRank badge in the footer to reach the internship verification page

## Architecture sketch

```
Browser
  │
  ├─ GitHub Pages (static hosting, HTTPS)
  │     └─ index.html / projects.html / contact.html / style.css / assets/
  │
  ├─ Formspree (contact form backend — receives POST, forwards to email)
  │
  └─ Cloudflare Web Analytics (client-side beacon script — tracks page views/visits, no cookies)
```

No database, no server-side code, no build pipeline — everything is static files plus two small third-party integrations (form handling and analytics), both on free tiers.

## v2 eval results

The two case studies on the Work page were rewritten (v2) after real portfolio feedback flagged that they described approach without evidence. Both now include a concrete worked example with numeric output:

- **AI Risk Register Generator (bias-audit case study):** ran a bias audit on a sample loan-approval dataset — found a 40% vs. 73.3% approval-rate disparity between groups, surfaced as the headline finding
- **AI System Compliance Case Study (risk classifier):** ran a risk classifier on a sample resume-screening tool — output a "High Risk" tier plus 4 concrete mitigations

Both examples are reproducible from the scripts in the `flyrank-project` repo (`projects/bias_audit.py`, `projects/risk_register.py`, `projects/sample_loan_data.csv`).

## Limitations

- **No backend of my own** — the contact form relies entirely on Formspree's free tier; if that service changed its terms or went down, the form would need a new backend
- The site has no server-side logic or database — anything beyond static content and the two third-party integrations above isn't currently supported
- Analytics only tracks aggregate page views/visits (Cloudflare Web Analytics is intentionally cookie-free and doesn't track individual visitors), so there's no per-user behavior data

## What I built with AI, and how

I used Claude throughout — for structuring the case studies, debugging HTML/CSS issues, writing the Formspree integration, and walking through the GitHub Pages / DNS / analytics setup step by step. I made the actual product and language decisions (what to include in each case study, what limitation to disclose, site structure and copy) and verified each change was live and working before moving on — Claude helped me build faster and understand each piece, but I reviewed and tested every change myself.
