# n8n Expression Cheat Sheet
**Life Inspired Learning — AI Automation with n8n for Non-Technical Users**  
*Reference companion for Module 1 — Lesson 1.3: Expressions*

---

## What Is an Expression?

An expression is a piece of dynamic code you write inside double curly braces: `{{ }}`. It tells n8n to calculate or look up a value instead of using a fixed piece of text.

**Fixed value:** `Hello, Sarah` — always says "Sarah"  
**Expression:** `Hello, {{ $json['First Name'] }}` — pulls the actual name from your data

To use an expression in any field, click the field and select "Expression" from the toggle, or click the **lightning bolt icon** to open the Expression Builder.

---

## The Most Common Expressions

### 1. Read a field from the current node's data

```
{{ $json.fieldName }}
```

Use when the field name has no spaces:
```
{{ $json.email }}
{{ $json.name }}
{{ $json.status }}
```

Use bracket notation when the field name has spaces or special characters:
```
{{ $json['First Name'] }}
{{ $json['Email Address'] }}
{{ $json['Follow-up Sent At'] }}
```

**Rule of thumb:** When in doubt, use brackets. They always work.

---

### 2. Read a field from a different node

```
{{ $('Node Name').item.json.fieldName }}
```

Examples:
```
{{ $('Google Sheets Trigger').item.json['row_number'] }}
{{ $('Gmail Trigger').item.json.from }}
{{ $('AI Agent').item.json.output }}
{{ $('Webhook — New Lead').item.json.email }}
```

Use this whenever you need data from a node that isn't the one immediately before the current node.

---

### 3. Current date and time

```
{{ $now.toISO() }}
```
Output: `2026-08-19T14:30:00.000Z` (full ISO format — good for storing in databases)

```
{{ $now.format('MMM D, YYYY') }}
```
Output: `Aug 19, 2026` (human-readable date)

```
{{ $now.format('MMM D, YYYY h:mm A') }}
```
Output: `Aug 19, 2026 2:30 PM` (date + time, human-readable)

```
{{ $now.format('YYYY-MM-DD') }}
```
Output: `2026-08-19` (sortable date format — good for spreadsheet columns)

---

### 4. Conditional (if/else) in an expression

```
{{ condition ? 'value if true' : 'value if false' }}
```

Examples:
```
{{ $json['Notes'] ? 'You mentioned: ' + $json['Notes'] : '' }}
```
→ If Notes is not empty, include it. If it's empty, output nothing.

```
{{ $json['Company'] ? ' from ' + $json['Company'] : '' }}
```
→ Adds "from Acme Corp" if a company is present, otherwise adds nothing.

---

### 5. Combine text and data (string concatenation)

```
{{ 'Hello, ' + $json['First Name'] + '!' }}
```
Output: `Hello, Sarah!`

```
{{ 'Re: ' + $('Gmail Trigger').item.json.subject }}
```
Output: `Re: Question about your pricing`

---

## Expressions Used in This Course

| Where | Expression | What It Does |
|-------|------------|--------------|
| Sales Follow-Up Automator — Gmail | `{{ $json['First Name'] }}` | Pulls first name into email greeting |
| Sales Follow-Up Automator — Sheets Update | `{{ $('Google Sheets Trigger').item.json['row_number'] }}` | Updates the exact row that triggered the workflow |
| Sales Follow-Up Automator — Sheets Update | `{{ $now.format('MMM D, YYYY h:mm A') }}` | Stamps the time the follow-up was sent |
| Sales Follow-Up Automator — Gmail body | `{{ $json['Notes'] ? 'I remember you mentioned: ' + $json['Notes'] + '.' : '' }}` | Adds a personal note if one was captured |
| Customer Support Agent — IF node | `{{ $json.output }}` | Reads the AI Agent's output to check for ESCALATE |
| Customer Support Agent — Slack alert | `{{ $('AI Agent').item.json.output }}` | Shows the escalation reason in Slack |
| Lead Capture — Gmail | `{{ $json.email }}` | Routes the welcome email to the right address |
| Lead Capture — Gmail | `{{ $json.name }}` | Personalizes the welcome email |

---

## The Expression Builder

You don't have to type expressions from memory. n8n has a built-in Expression Builder.

**How to open it:** Click any text field in a node, then click the **lightning bolt icon (⚡)** that appears on the right side of the field.

What you'll see:
- A list of all previous nodes and their fields on the left
- A live preview of your expression output on the right
- Click any field to insert it automatically — no typing required

**Best practice:** Use the Expression Builder when you're learning. It shows you the exact field names and lets you click to insert them, so you never have to guess the syntax.

---

## The 3 Most Common Expression Mistakes

### Mistake 1: Using the wrong node name
```
{{ $('Google Sheet Trigger').item.json['row_number'] }}  ❌
{{ $('Google Sheets Trigger').item.json['row_number'] }}  ✅
```
The node name in the expression must match the node name on the canvas exactly — including spaces, capitalization, and punctuation. Copy it from the node header to be safe.

---

### Mistake 2: Missing brackets for fields with spaces
```
{{ $json.First Name }}  ❌  (breaks — space in field name)
{{ $json['First Name'] }}  ✅
```
Any field name with a space, dash, or special character needs bracket notation.

---

### Mistake 3: Forgetting to enable the Expression toggle
If your expression shows up as literal text like `{{ $json.email }}` instead of the actual email address — check that the field is set to "Expression" mode, not "Fixed Value." Look for the toggle or the lightning bolt icon on the field.

---

## Quick Reference Card

| What you want | Expression |
|---------------|------------|
| Field from current node | `{{ $json.fieldName }}` |
| Field with spaces | `{{ $json['Field Name'] }}` |
| Field from another node | `{{ $('Node Name').item.json.field }}` |
| Today's date (readable) | `{{ $now.format('MMM D, YYYY') }}` |
| Date + time | `{{ $now.format('MMM D, YYYY h:mm A') }}` |
| ISO timestamp | `{{ $now.toISO() }}` |
| Combine text + data | `{{ 'Hello, ' + $json['First Name'] }}` |
| Conditional value | `{{ $json.field ? 'yes' : 'no' }}` |
| If field is empty, show nothing | `{{ $json.field ? $json.field : '' }}` |

---

*For more n8n expression syntax, see the [official n8n expressions docs](https://docs.n8n.io/code/expressions/).*  
*This cheat sheet is a companion to Video 10 — n8n Complete Beginner Course 2026.*
