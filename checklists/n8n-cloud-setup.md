# n8n Cloud Setup Checklist
### AI Automation with n8n — Life Inspired Learning

Use this checklist the first time you set up your n8n Cloud account.

---

## Step 1 — Create Your Account
- [ ] Go to [n8n.io](https://n8n.io) and click **"Get started free"**
- [ ] Sign up with your email (or Google account)
- [ ] Verify your email address
- [ ] Choose the **Starter** plan (free trial — no card needed to start)

## Step 2 — Explore the Interface
- [ ] Click **"New workflow"** to open the canvas
- [ ] Find the **"+"** button — this is how you add nodes
- [ ] Open the node panel on the left side — browse the integration list
- [ ] Click the **"Settings"** gear icon (top right) — note where your credentials are stored
- [ ] Find **"Executions"** in the left sidebar — this is your workflow history

## Step 3 — Add Your First Credential
- [ ] Click **Settings → Credentials → Add credential**
- [ ] Search for "Gmail" and select **Gmail OAuth2**
- [ ] Click **"Sign in with Google"** and authorize access
- [ ] Name it clearly: "My Gmail — [your address]"
- [ ] Save and confirm the credential appears in your list

## Step 4 — Run a Test Workflow
- [ ] Download `lead-capture-machine.json` from the `/workflows/module-2/` folder in this repo
- [ ] In n8n: click **"+"** → **"Import from file"** → select the JSON file
- [ ] Open each node and update the placeholder values (Sheet ID, email, Slack channel)
- [ ] Click **"Test workflow"** to run it manually
- [ ] Check the **Output panel** on each node to see data flowing through

## Step 5 — Activate a Live Workflow
- [ ] Once tested and happy, toggle the **"Active"** switch (top right of canvas) to ON
- [ ] Confirm the workflow appears as **"Active"** in your workflow list
- [ ] Test it end-to-end by triggering the real event (e.g., submit your form)
- [ ] Check **Executions** to confirm it ran successfully

---

## Useful Links
- n8n documentation: [docs.n8n.io](https://docs.n8n.io)
- n8n community forum: [community.n8n.io](https://community.n8n.io)
- Full course: [lifeinspiredlearning.com](https://lifeinspiredlearning.com)
