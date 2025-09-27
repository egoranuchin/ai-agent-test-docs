# Building Your First Agent (Step by Step)

We’ll build a personal assistant agent as an example. For that, we'll follow the steps in this recommended order:

1. Add an AI Agent node;
2. Connect the tools;
3. Configure the tools;
4. Decide on the environment;
5. Fine-tune the agent.

## Prerequisites

- Logged-in account with the Latenode platform;
- Appropriate amount of credits enough for performing the actions with AI agents.

## Step 1: Add an AI Agent

First, let's create an AI Agent node:

1. Open the Latenode platform's web interface on the [**Scenarios tab**](app.latenode.com/scenarios) and click the ***Create a new scenario button***.
2. On the new scenario's view, via the ***Edit*** button in the breadcrums navigation element, rename the scenario to `AI-Agent Personal Assistant` or any other perferred name.
3. Create an AI Agent node through clicking the ***Add a Node to Begin... button*** -> in the **Choose an app** window, select the ***AI Agent...*** option -> **AI Agent** action.
4. In the opened **AI Agent** window, click the name of the agent and set it to a preferred value (for example `Stanley`).

## Step 2: Connect the Tools

Now that we've created the AI Agent node, we can connect it to the tools it will use to perform as a personal assistant. We'll use the following integrations:

- Gmail and Google Calendar to manage emails and schedule events,
- Todoist to track and create work items,
- Perplexity for web search.

1. On the created scenario's view, click the ***Add Node*** button at the bottom of the screen.
2. On the **Choose an app** window, search for the ***Gmail*** node via the search bar.
3. Add nodes for the **Create Draft** and **Find Email** actions.
4. By clicking and dragging a connection link from the new node's connection elements and releasing it on the AI Agent's node's connection element, create connections with the new nodes.
5. In the same manner, add and connect the **List Events** and **Create Event** action nodes for the Google Calendar.
6. Add and connect the **List Uncompleted Tasks** and **Create Task** action nodes for the Todoist.
7. Add and connect the **Create Chat Completion** action node for the AI: Perplexity.

## Step 3: Configure Tools

Some nodes show a triangle warning ("Please complete the setup of this node”). That means we need to set them up before using them. Open each node with the warning and fill in the required fields:

1. The first required field is **Connection**. Authorize each integration by clicking the ***Sign In*** button and save the changes with the ***Save*** button.

    :::note

    Alternatively, you can add the required authorizations on the **Authorizations** tab. Click the ***New authorization*** button and look up the the configured integration through the search bar. Rename your authorizations to keep easy track of them.

    :::

1. Name your action nodes to keep easy track of them:

    1. Open the node's menu by clicking it;
    2. Click the **Name** field at the top of the window and enter a suitable value, so that the AI Agent could tell what the tool is for even by its name alone.

1. Tweak the **Tool Description** and **User Prompt** fields to match the desired behavior of the tool. For example, for the **Perplexity web_search** node's **Tool Description** field you can use the following snippet:

    ```text
    Perplexity AI-powered search engine delivering accurate, concise answers and context
    ```

    For the **User Prompt** field, use the following:

    ```text
    fromAIAgent(User Prompt; Your new question prompt)
    ```

Once changes are done, click the ***Save*** button to save them.

1. For some other action nodes you'd have to follow a slightly different approach configuring them, for example Google Calendar's action nodes require authorization and choosing the Calendar ID for the Agent to access. One of the possible Tool Descriptions for the Google Calendar node could include the following:

```text
Retrieves events from Google Calendar within the specified window
```

1. Prefill static fields (like time zone) and let the agent fill dynamic fields (time min, time max).

Repeat this for all tools with a warning.

## Step 4: Decide on the environment

Every Latenode scenario starts with a trigger. Options: Run Once, Webhook, Email, Telegram.

Example: use Telegram:

- Create a Telegram bot with BotFather.
- Get token.
- Authorize token in Latenode.
- Add trigger node and “Send Message” reply node.
- Store message and chat ID in variables.

## Step 5: Fine-tune the agent

- Set Session ID = chat ID so memory binds to each user.
- Adjust context window (default: 25 messages).
- Larger windows keep more context, but too much may confuse the model.

## Step 6: Write System Prompt

- The system prompt is the most important part.
- Use structured Markdown:

  - **Personality** - Who the agent is.
  - **Environment** - Where the agent runs.
  - **Goal** - What the agent tries to achieve.
  - **Guardrails** - What the agent should not do.
  - **Tools** - List of available tools.

- You can add sections like workflow, user context, or current time.
- Use examples from Latenode’s documentation.
- Expect to iterate and refine over time.

## Step 7: Choose Model

- For tasks with larger context and tool use, versatile models work best.
- Example: GPT-4.1 or GPT-4.1-mini.
- Start with mini for testing (cheaper).

## Step 8: Connect Responses

- Run test execution.
- Inspect JSON output.
- Map agent response into the Telegram reply node.

## Testing the Assistant

Now test your agent:

- Ask it to check your inbox.
- Let it find urgent emails.
- Tell it to schedule a call and add it to your task tracker.

👉 You’ll see the agent using Gmail, Calendar, and Todoist together, completing the workflow in one request.
