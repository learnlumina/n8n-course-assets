# AI Automation with n8n — Course Assets
### Life Inspired Learning | [lifeinspiredlearning.com](https://lifeinspiredlearning.com)

Welcome to the official course asset repo. Everything here is yours to download and use as part of the course.

---

## What's Inside

| Folder | What you'll find |
|---|---|
| `/workflows` | n8n workflow JSON templates — import directly into your n8n instance |
| `/lesson-scripts` | Full lesson outlines and hands-on lab steps (paid course) |
| `/prompts` | Ready-to-use AI prompt library for business automations |
| `/checklists` | Step-by-step setup checklists for each integration |
| `/resources` | Bonus reference materials and automation idea lists |

---

## How to Import a Workflow Template

1. Open your n8n instance (cloud or self-hosted)
2. Click **"Add workflow"** → **"Import from file"**
3. Select the `.json` file from the `/workflows` folder
4. Add your own credentials when prompted (the template won't include yours)
5. Hit **"Execute workflow"** to test it

> **Important:** Workflow templates show you the structure — you still need to connect your own accounts (Gmail, Slack, Google Sheets, HubSpot, OpenAI, etc.) inside each node before they'll run live.

---

## Workflows by Module

### Module 1 — How n8n Thinks
| File | What it does |
|---|---|
| `hello-world-starter.json` | The first workflow you build in the course — manual trigger → a single action, used to learn the canvas |

### Module 2 — Your First 3 Automations
| File | What it does |
|---|---|
| `smart-email-organizer.json` | Reads new Gmail → classifies by type → labels and routes automatically |
| `lead-capture-machine.json` | Form submission → Google Sheets → welcome email → Slack notification |
| `weekly-business-report.json` | Every Monday → pull spreadsheet data → email yourself a KPI summary |

### Module 3 — Connecting Your Business Stack
| File | What it does |
|---|---|
| `crm-contact-sync.json` | New form submission → create/update contact in HubSpot → welcome email + team alert |
| `meeting-lifecycle.json` | New Calendly booking or cancellation → CRM deal update → prep email → team alert |
| `new-client-folder.json` | Deal closed → Google Drive folder created → welcome doc copied in → shared link emailed → team notified |
| `social-content-repurposer.json` | New blog post (RSS) → content team notified on Slack → optional LinkedIn auto-post (advanced, disconnected by default — see notes in the file) |
| `pocket-ai-assistant.json` | Bonus file from the free YouTube "AI Integration" video — a simple chat-form-to-AI-answer workflow, not part of the paid Module 3 lessons but left here as a working bonus template |

### Module 4 — Logic, Filters, and Flow Control
| File | What it does |
|---|---|
| `lead-router-if-node.json` | New lead → IF node checks budget → routes to Slack (high-value) or CRM nurture (everyone else) |
| `bulk-personalized-outreach-loop.json` | Spreadsheet of contacts → loops through in batches of 10 → sends a personalized email to each with a pause between batches |
| `crm-invoice-merge-report.json` | Pulls CRM + QuickBooks data in parallel → merges by matching email → emails a combined summary |
| `error-logging-handler.json` | The course's standard Error Workflow — catches failures from any other workflow, logs them to a sheet, and alerts Slack for non-manual failures |
| `sales-followup-automator.json` | Bonus file from the free YouTube "Sales Follow-Up" video — spreadsheet trigger → follow-up email → row update |

### Module 5 — AI Superpowers
| File | What it does |
|---|---|
| `ai-email-responder.json` | New support email → AI drafts a reply → saves as a draft for human review (never auto-sends) |
| `content-summarizer.json` | New doc in Google Drive → AI summarizes into exec summary/bullets/action items → saves to Notion + Slack |
| `lead-scoring-bot.json` | New CRM entry → AI scores the lead 0-100 with reasoning → updates CRM → alerts Slack if score ≥ 70 |
| `customer-support-agent.json` | Bonus file from the free YouTube "Customer Support" video — an AI Agent with a Google Sheets FAQ tool, referenced directly in Lesson 6.1 as a real-world example of agent behavior before the course formally introduces agents |

### Module 6 — Advanced AI: Agents, Memory, RAG
| File | What it does |
|---|---|
| `research-agent.json` | Give it a company name → agent uses an HTTP tool to research → drafts a personalized outreach email |
| `memory-chatbot.json` | A chat AI Agent that remembers the conversation per user session, with a Google Sheets FAQ tool |
| `rag-knowledge-chatbot.json` | Two flows in one file: (1) ingest your documents into a vector store, chunked and embedded, and (2) a chatbot that answers questions using only your content — notes in the file cover swapping in Qdrant (open source) for production use |

### Module 7 — Full Business Projects (Capstones)
| File | What it does |
|---|---|
| `client-onboarding-full.json` | Contract signed → CRM updated + Drive folder created in parallel → welcome doc + booking link emailed → team notified |
| `social-proof-automation.json` | 5-star review received → Slack alert with approve/reject links → approved reviews auto-post to social + get a thank-you email |
| `invoice-payment-tracker.json` | New invoice → logged → 7-day wait → payment check → AI-drafted reminder if unpaid → second wait/check → Slack escalation if still unpaid |
| `internal-ai-assistant.json` | Internal team chatbot with memory, a knowledge-base tool (reusing the Module 6 vector store), a sales-tracker tool, and a Slack escalation tool — combines every skill from Modules 5-6 into one assistant |

---

## Lesson Scripts (Paid Course)

The `/lesson-scripts` folder contains the full narration script and a hands-on lab for every lesson in the paid course — 8 modules, 31 lessons in total. Each file includes learning objectives, timestamped segments, an FAQ block, and step-by-step lab instructions with a "what done looks like" checkpoint.

---

## Prompts Library

The `/prompts` folder contains a tested business AI prompt library that works inside n8n's AI nodes. Covers email drafting, lead scoring, content summarization, customer support, and more.

---

## Checklists

Setup and reference checklists used throughout the course:
- `credentials-setup.md` — connecting Gmail, Slack, Sheets, HubSpot, Calendly, OpenAI, and more
- `n8n-cloud-setup.md` — getting started on n8n Cloud
- `self-hosting-railway.md` — deploying and migrating to a self-hosted instance on Railway
- `security-best-practices.md` — credential discipline, access control, sensitive data, and webhook security
- `video10-quick-start.md` — quick-start companion for the free YouTube capstone video

---

## Get the Full Course

The templates here go with the full course — where we build every one of these automations together, step by step.

👉 **[Enroll at lifeinspiredlearning.com](https://lifeinspiredlearning.com)**

You'll get:
- 8 modules and 31 lessons of hands-on video instruction
- Every workflow explained in detail before you build it
- AI agent, memory, and RAG modules not available anywhere else for non-technical users
- 4 full capstone business projects combining every skill in the course
- Community access and Q&A

---

## Questions or Issues?

If a template isn't working or you have a question about setup, post in the course community or open a GitHub Issue here with:
- Which workflow file
- What error message you're seeing
- Which n8n version you're running

---

*Made with ❤️ by Life Inspired Learning*
