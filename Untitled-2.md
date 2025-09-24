
# 🧭 User Guide: Building Your First AI Agent in Latenode

## 1. Introduction

AI agents are one of the most exciting developments in artificial intelligence. They can reason, plan, and act autonomously — not just follow rigid scripts.

This guide will walk you through building your first **AI Personal Assistant** in **Latenode**, without writing a single line of code.

By the end, you’ll have a working assistant that:

* Reads your emails.
* Schedules meetings in your calendar.
* Manages tasks in your tracker.
* Searches the web for information.
* Responds via chat (Telegram in our example).

## 2. Agents vs Automations

Before building, let’s clarify a common confusion:

* **Automations**: Run on fixed rules. Example: every morning, fetch WhatsApp messages and send a summary. Predictable, but not adaptive.
* **Agents**: Flexible, dynamic, and reasoning-capable. Example: Ask “Which specialists is this company hiring?” and the agent checks the company’s website or CRM.

👉 Use **automations** for repetitive, static workflows.
👉 Use **agents** when reasoning, adaptability, and context matter.

---

## 3. Core Components of an Agent

Every Latenode agent is built on **three pillars**:

1. **Brain**: A large language model (LLM) such as GPT-4, Gemini, or Claude. It handles reasoning, planning, and natural language.
2. **Memory**: Lets the agent recall past interactions or preserve session context.
3. **Tools**: External services the agent can use (Gmail, Calendar, task trackers, APIs, etc.).

> 📌 **Golden Rule**: Start simple. If a single agent does the job, don’t overcomplicate it.

---

## 4. Prerequisites

Before starting, make sure you have:

* A [Latenode](https://latenode.com) account.
* Access to the following services:

  * Gmail (for email).
  * Google Calendar.
  * Task tracker (e.g., Todoist).
  * A web search API (e.g., Perplexity).
* A **Telegram bot token** (for interaction). Create one easily with [BotFather](https://core.telegram.org/bots#botfather).

---

## 5. Step-by-Step Setup

### Step 1: Create Your Scenario

1. Log into **Latenode**.
2. Create a **new scenario**.
3. Add an **AI Agent node**.
4. Name your agent (example: `Stanley`).

---

### Step 2: Connect Tools

1. Open the **node list** and add tools:

   * Gmail → “Create Draft” and “Read Inbox.”
   * Google Calendar → “List Events.”
   * Todoist → “Create Task.”
   * Perplexity → “Web Search.”
2. Authorize each integration.

   * Fill in credentials in the **Authorization Tab**.
   * Give each connection a descriptive name (e.g., `Work Gmail`, `Personal Calendar`).

📸 *\[Insert screenshot: Node list with Gmail, Calendar, Todoist, Perplexity connected]*

---

### Step 3: Configure Tools

For each node:

* **Give it a clear name** (e.g., `List Calendar Events`).
* **Write a short description** so the agent knows when to use it.
* **Fill required fields**:

  * Example: in Calendar, prefill *time zone* but let the agent fill *time min* and *time max*.
* Use **From AI Agent Operator** for dynamic inputs.

📸 *\[Insert screenshot: Example node setup with fields highlighted]*

---

### Step 4: Add a Trigger

Decide how your agent should be activated. Options:

* **Run Once** (manual testing).
* **Webhook** (custom app integration).
* **Email Trigger**.
* **Telegram Trigger** (recommended for this guide).

🔹 Example: Telegram Trigger

1. Connect the Telegram node to your bot.
2. Authorize with the token.
3. Add **Send Message** node to reply back.
4. Use variables to store `message` and `chat ID`.

📸 *\[Insert screenshot: Telegram trigger + reply flow]*

---

### Step 5: Configure Memory

1. In the AI Agent node, set **Session ID** = `chat ID`.

   * Ensures conversations are linked to each user.
2. Configure **Context Window** (default: 25 messages).

   * Increase for complex tasks.
   * Keep reasonable to avoid confusion or hallucinations.

---

### Step 6: Write the System Prompt

This is the **blueprint** for your agent’s behavior. Use structured Markdown:

```markdown
# Personality
Friendly and professional personal assistant named Stanley.

# Environment
Works with Gmail, Google Calendar, Todoist, and Web Search.

# Goal
Help the user manage emails, tasks, and schedules efficiently.

# Guardrails
Never share private data. Always confirm before deleting.

# Tools
- Gmail Draft
- Gmail Inbox
- Google Calendar
- Todoist
- Web Search
```

Tips:

* Use Latenode’s [prompting guide](https://help.latenode.com).
* Iterate and refine based on results.

---

### Step 7: Select Model

* Recommended: **GPT-4.1-mini** (low cost, long context).
* Use **GPT-4.1** for production when higher reliability is needed.

📸 *\[Insert screenshot: Model selection dropdown]*

---

### Step 8: Connect Agent Responses

1. Run a test execution of the agent.
2. Inspect JSON response structure.
3. Map agent’s reply into the **Telegram “Send Message” node**.

📸 *\[Insert screenshot: Mapping agent reply to Telegram]*

---

## 6. Testing the Agent

Try these commands in Telegram:

* **Inbox check:**

  > “Do I have any urgent emails?”

* **Task scheduling:**

  > “Find time for a payment call tomorrow and add it to my calendar and Todoist.”

* **Web search:**

  > “Search the web for news about AI regulation in Europe.”

✅ Verify that the agent:

* Reads from Gmail.
* Updates your calendar.
* Adds tasks to Todoist.
* Replies in Telegram.

---

## 7. Best Practices

* **Keep it simple.** Use automations for fixed tasks, agents for reasoning.
* **Name tools clearly.** Helps the agent choose the right one.
* **Prompt iteratively.** Test and refine system instructions.
* **Balance memory.** Too much history → confusion; too little → loss of context.
* **Secure integrations.** Authorize only what’s needed.

---

## 8. Example Workflow

**Scenario:** Handle an urgent email.

1. User: “Check my inbox for urgent messages.”
2. Agent finds one flagged email.
3. User: “Schedule a call to handle payment.”
4. Agent:

   * Finds free slot in Google Calendar.
   * Adds task in Todoist.
   * Drafts email reply in Gmail.

👉 All executed in a single conversation.

---

## 9. Next Steps

* Experiment with **multi-agent systems** (supervisor + specialists).
* Try other integrations (Slack, Notion, custom APIs).
* Explore advanced prompt engineering techniques.

---

## 10. Troubleshooting

* **Tool error:** Check authorization in the node.
* **No response:** Confirm correct JSON key mapping.
* **Memory issues:** Adjust context window.
* **Wrong behavior:** Refine system prompt.

---

## 11. Glossary

* **Agent**: Reasoning, adaptive automation.
* **Automation**: Fixed, rule-based workflow.
* **Node**: A block in Latenode scenario.
* **Session ID**: Identifier binding memory to a user.
* **System Prompt**: Instruction blueprint for the agent.

---

✍️ This draft reads like a real **step-by-step user manual** with both narrative and reference sections.

Do you want me to **add diagrams/mock screenshots** (block diagrams of nodes, JSON mapping, etc.) so it feels closer to a PDF/manual — or keep it text-only for now?
