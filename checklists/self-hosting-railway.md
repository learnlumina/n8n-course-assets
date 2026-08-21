# Self-Hosting n8n on Railway — Setup Checklist
### AI Automation with n8n — Life Inspired Learning

Use this checklist when you're ready to move off n8n Cloud's usage limits
and run your own instance for free (or near-free) on Railway.

---

## Step 1 — Create Your Railway Account
- [ ] Go to [railway.app](https://railway.app) and sign up (GitHub login is fastest)
- [ ] Verify your email
- [ ] Note the free tier's monthly usage credit — enough to run a small n8n
      instance comfortably for most solo/small-business use

## Step 2 — Deploy n8n
- [ ] From the Railway dashboard, click **New Project → Deploy a Template**
- [ ] Search for the official **n8n** template and select it
- [ ] Confirm the deployment region (pick one close to you or your customers)
- [ ] Click **Deploy** and wait for the build to finish

## Step 3 — Set Required Environment Variables
- [ ] `N8N_ENCRYPTION_KEY` — generate a long random string and save it somewhere
      safe (losing this means losing access to all saved credentials)
- [ ] `N8N_HOST` — your Railway-provided domain (or custom domain, see Step 5)
- [ ] `N8N_PROTOCOL` — set to `https`
- [ ] `WEBHOOK_URL` — must match your public domain exactly, or webhook-based
      triggers (Lesson 2.2 and beyond) will silently fail
- [ ] `GENERIC_TIMEZONE` — set to your business's timezone so Schedule
      Triggers fire at the time you expect

## Step 4 — First Login and Owner Account
- [ ] Open your Railway-provided URL
- [ ] Create the instance owner account (this becomes your admin login)
- [ ] Confirm you can create a new workflow and see the node panel

## Step 5 — Point a Custom Domain (Optional but Recommended)
- [ ] In Railway, go to your service → **Settings → Domains → Custom Domain**
- [ ] Add your domain (e.g., `automate.yourbusiness.com`)
- [ ] Update your DNS provider with the CNAME record Railway gives you
- [ ] Wait for DNS propagation (usually under an hour) and confirm HTTPS works

## Step 6 — Backups
- [ ] Confirm Railway's automatic volume backups are enabled for your project
- [ ] Additionally, export your workflows periodically (Workflows → Download)
      as a manual backup independent of the platform
- [ ] Store the `N8N_ENCRYPTION_KEY` value in a password manager, not just in
      Railway's environment variables — you'll need it if you ever migrate
      instances

## Step 7 — Re-Point Your Webhooks
- [ ] Update any external tool (forms, Calendly, your e-signature tool) that
      was pointed at your n8n Cloud webhook URLs to use your new self-hosted
      domain instead
- [ ] Re-test each affected workflow end-to-end after the switch

## Step 8 — Keep n8n Updated
- [ ] Check Railway's deployment settings for auto-redeploy on new n8n
      releases, or set a recurring monthly reminder to manually check for
      updates
- [ ] Review release notes before updating a production instance — test in a
      second, non-production Railway project first if you're running
      business-critical automations
