# Security and Best Practices Checklist
### AI Automation with n8n — Life Inspired Learning

Run through this checklist once your automations start touching real
customer data, real money, or real credentials — not just while you're
still learning on scratch workflows.

---

## Credentials
- [ ] Never hardcode a password, API key, or token directly into a node's
      parameters — always use the Credentials vault (Lesson 1.3)
- [ ] Name every credential by purpose, not just by app
      (`Gmail - Support Inbox`, not `Gmail account 3`)
- [ ] Set a monthly spend limit on every AI provider (OpenAI, Anthropic) —
      Lesson 5.1
- [ ] Revoke and recreate any credential immediately if a team member with
      access leaves, or if you suspect it may have been exposed

## Access Control
- [ ] Decide, in writing, who on your team should have access to which
      workflows — not everyone needs edit access to everything
- [ ] On n8n Cloud/Enterprise plans with project or role-based permissions,
      use them rather than sharing one shared login
- [ ] Keep the instance owner account's login credentials known to more than
      one trusted person (a single point of failure on account access is a
      real business risk)

## Sensitive Data
- [ ] Before building a workflow that touches customer PII (names, emails,
      payment info, health data, etc.), ask: does this data need to flow
      through this specific node, or can it be filtered out earlier?
- [ ] Review execution data retention settings (Lesson 1.4) — consider a
      shorter retention window for workflows handling sensitive data
- [ ] Avoid logging sensitive fields into Slack messages or shared sheets
      unless genuinely necessary for the business process
- [ ] If a workflow calls an external AI API, be aware that data sent to
      that API is subject to THAT provider's data policies — check whether
      your plan/provider offers a no-training-on-your-data guarantee if this
      matters for your business

## Webhooks
- [ ] Never share a workflow's Test URL publicly — only the Production URL,
      and only once the workflow is Active and tested
- [ ] For any webhook that triggers a real action (Lesson 7.2's approval
      links are a good example), consider adding a secret token check so the
      URL can't be discovered and triggered by an outsider
- [ ] Periodically review your active workflows for webhook URLs that are no
      longer needed and deactivate them

## AI-Specific
- [ ] Every AI prompt that produces business-facing output (an email, a
      customer message) should include explicit boundaries against
      fabricating information (Lesson 5.1's prompt-writing habits)
- [ ] Keep human-in-the-loop review (draft, not auto-send) on any AI output
      reaching a customer directly, unless you have a strong, tested reason
      not to
- [ ] Review AI Agent tool permissions (Module 6) the same way you'd review
      an employee's access — only give an agent the tools it genuinely needs

## Ongoing Habits
- [ ] Run the weekly Executions health-check habit from Lesson 1.4
- [ ] Revisit this checklist every quarter as your automation library grows
      — what was low-stakes when you built it may not still be, once it's
      handling real volume
