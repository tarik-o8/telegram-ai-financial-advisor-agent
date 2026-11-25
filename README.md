# AI Personal Finance Advisor Agent (Telegram Bot)

An intelligent, bilingual (**English & Bangla**) conversational AI Financial Advisor built with **n8n**, **Groq AI (`openai/gpt-oss-120b`)**, and **Telegram Bot API**. Equipped with **Conversational Memory** and a **Calculator Tool**, it provides structured budgeting, saving, and risk-aware investment education in real time.

## Workflow Architecture

![n8n Telegram AI Agent Architecture](./workflow.png)

## Key Features & Architecture

1. **Telegram Trigger:** Captures incoming user messages in real time via Telegram webhook.
2. **AI Agent (`@n8n/n8n-nodes-langchain.agent`):** Orchestrates reasoning, tool usage, and strict financial safety/compliance guardrails using structured system prompting.
3. **Groq Chat Model (`openai/gpt-oss-120b`):** Delivers ultra-fast LLM inference capable of understanding and responding naturally in both English and Bangla.
4. **Simple Memory (Window Buffer):** Maintains session-based chat history (`v2-{{chat.id}}`) so the agent remembers previous context during multi-turn financial discussions.
5. **Calculator Tool:** Enables accurate mathematical calculations for budgeting, savings goals, and financial breakdowns without LLM math hallucinations.
6. **Automated Telegram Reply:** Sends cleanly formatted responses back to the user's Telegram chat.

## Sample Interaction

**User (Telegram):**
> *"Can you advise me about investing?"*

**AI Financial Advisor Response:**
> Provides a structured breakdown covering **Direct Answer**, **Explanation**, **Potential Benefits**, **Risks & Considerations**, and **Practical Next Steps**, along with an educational disclaimer.

## Tech Stack
- **Automation & Agent Framework:** n8n (LangChain AI Agent Node)
- **LLM Engine:** Groq AI (`openai/gpt-oss-120b`)
- **Memory & Tools:** Window Buffer Memory, Calculator Tool
- **Messaging Channel:** Telegram Bot API

## How to Use This Workflow
1. Download the `workflow.json` file from this repository.
2. Open your **n8n** workspace and create a new workflow.
3. Click the top-right menu (`...`) ➔ **Import from File** and upload `workflow.json`.
4. Connect your **Telegram Bot API** and **Groq API** credentials to activate.
