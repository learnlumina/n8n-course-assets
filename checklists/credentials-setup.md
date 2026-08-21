# Credentials Setup Checklist
### AI Automation with n8n — Life Inspired Learning

Every integration you use in n8n requires a credential. Set these up once — they stay saved in your account and work across all your workflows.

---

## Gmail (Google OAuth2)
- [ ] In n8n: **Settings → Credentials → Add credential → Gmail OAuth2**
- [ ] Click **"Sign in with Google"**
- [ ] Select the Google account you want to use
- [ ] Allow the requested permissions (read, send, labels)
- [ ] Name it clearly: `Gmail — yourname@gmail.com`
- [ ] ✅ Test: create a workflow with a Gmail node and run it manually

**Troubleshooting:** If Google shows a warning about an "unverified app" — click **Advanced → Go to n8n (unsafe)** — this is normal for OAuth apps in development.

---

## Google Sheets (Google OAuth2)
- [ ] In n8n: **Settings → Credentials → Add credential → Google Sheets OAuth2**
- [ ] Use the same Google OAuth flow as Gmail
- [ ] You can use one Google OAuth credential for both Gmail AND Sheets — n8n will prompt you to reuse it

**Tip:** Get your Sheet ID from the URL: `https://docs.google.com/spreadsheets/d/[THIS IS THE ID]/edit`

---

## Slack
- [ ] Go to [api.slack.com/apps](https://api.slack.com/apps) → **Create New App → From scratch**
- [ ] Name it `n8n Automation` — select your workspace
- [ ] Go to **OAuth & Permissions → Scopes → Bot Token Scopes** — add: `chat:write`, `channels:read`
- [ ] Click **"Install to Workspace"** and authorize
- [ ] Copy the **Bot User OAuth Token** (starts with `xoxb-`)
- [ ] In n8n: **Settings → Credentials → Add credential → Slack → paste token**
- [ ] Invite the bot to your channel: in Slack, type `/invite @n8n Automation`
- [ ] ✅ Test: send a test message to your channel

**Get your Channel ID:** Right-click the channel → **"View channel details"** → scroll to bottom — the ID is at the bottom (starts with `C`)

---

## OpenAI
- [ ] Go to [platform.openai.com](https://platform.openai.com) → **API Keys → Create new secret key**
- [ ] Copy the key immediately — you can't view it again after closing the window
- [ ] In n8n: **Settings → Credentials → Add credential → OpenAI → paste key**
- [ ] ✅ Test: add an OpenAI node to a workflow and run a simple prompt

**Tip:** Set a monthly spending limit in OpenAI's billing settings so you never get surprised by a large bill.

---

## Anthropic (Claude)
- [ ] Go to [console.anthropic.com](https://console.anthropic.com) → **API Keys → Create Key**
- [ ] Copy the key (starts with `sk-ant-`)
- [ ] In n8n: **Settings → Credentials → Add credential → Anthropic → paste key**
- [ ] ✅ Test: swap the OpenAI node in any Module 5 workflow with an Anthropic node

---

## HubSpot (for Module 3 CRM workflows)
- [ ] Go to your HubSpot account → **Settings → Integrations → Private Apps**
- [ ] Click **"Create private app"** — name it `n8n`
- [ ] Under **Scopes** — add: `crm.objects.contacts.read`, `crm.objects.contacts.write`
- [ ] Click **"Create app"** and copy the access token
- [ ] In n8n: **Settings → Credentials → Add credential → HubSpot → paste token**

---

## Calendly (for Module 3 meeting workflows)
- [ ] Go to [developer.calendly.com](https://developer.calendly.com) → **Personal Access Tokens → Create Token**
- [ ] Copy the token
- [ ] In n8n: **Settings → Credentials → Add credential → Calendly → paste token**
- [ ] For the webhook trigger: use n8n's Webhook node URL as the Calendly webhook destination

---

## Google Drive (for Module 3 document workflows)
- [ ] Same Google OAuth credential as Gmail/Sheets
- [ ] In n8n, select **Google Drive OAuth2** and reuse your existing Google credential
- [ ] ✅ Test: create a Google Drive node → list files in a folder

---

*Checklist v1.0 | Life Inspired Learning*
