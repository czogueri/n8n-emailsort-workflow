# n8n-emailsort-workflow
Automatically reviews incoming Gmail messages using an AI agent and marks unimportant emails as "read" to keep your inbox tidy.

## Trigger
- **Type:** Gmail Trigger  
- **Frequency:** Every minute  
- **Filter:** No filters — processes all incoming emails

---

## How it works
1. **Gmail Trigger** — Polls your Gmail inbox every minute for new messages.
2. **AI Agent** — Uses a GPT-4.1-mini model to evaluate the email content based on your personal context:
   - You are an AI automation agency owner.
   - Irrelevant emails: promotions, non-business critical updates.
3. **Mark as Read** — If the AI agent determines the email is *not important*, it marks it as read in Gmail.

---

## Personal Context & Filtering Rules
- **Relevant:** Emails related to business operations, clients, or agency automation projects.
- **Irrelevant:** Promotions, marketing blasts, general newsletters.

---

## Inputs
- New email metadata & snippet from Gmail (subject, snippet, sender, labels).

---

## Outputs
- Marks certain emails as read (no further processing for those).
- Leaves important emails untouched.

---

## Environment / Secrets
- `GMAIL_OAUTH2` — OAuth2 credentials for Gmail API access.
- `OPENAI_API_KEY` — API key for GPT-based classification.

---

## How to Import
1. Export `workflow.json` from this folder.
2. In n8n, click **Import from file** or paste JSON in the workflow editor.
3. Reconnect:
   - Gmail credentials (`gmailOAuth2`)
   - OpenAI credentials (`openAiApi`)
4. Activate the workflow.

---

## Version / Changelog
- **v1.0.0** — Initial version (2025-08-11) — Created by Dozie

---

## Example
**Incoming Email:**  
_Subject:_ "50% Off Your Favorite Tools!"  
_AI Agent Decision:_ Not important → Marked as read.
