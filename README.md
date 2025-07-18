🚀 MCP Server & Client with n8n, Google Gemini, and Firecrawl
An n8n-powered Model Context Protocol (MCP) server and client for AI conversational flows — enhanced with Firecrawl for dynamic data integration and the Google Gemini Chat Model for intelligent responses.

🧩 Project Overview
This project delivers a robust and flexible implementation of an MCP server and client, orchestrated using n8n workflows. It enables:

Seamless conversational context handling

Intelligent AI interactions via Google Gemini

Real-time web data access via Firecrawl

End-to-end automation using n8n

✨ Features
🛠 n8n Workflow Orchestration
Automates and connects various services using n8n’s visual builder.

💬 Model Context Protocol (MCP)
Manages and preserves conversational context with AI models.

🧠 Google Gemini Chat Model
Integrates Gemini for context-aware conversational intelligence.

🌐 Firecrawl Integration
Enables real-time web scraping and external data utilization.

🧱 Modular Design
Easily extensible workflows to integrate new tools and data sources.

🏗 Architecture
At its core, this project is an n8n workflow acting as both an MCP server and client. Key components include:

Webhook Trigger: "When Chat Message Received"
Entry point for incoming messages.

🧠 AI Agent Node
Processes input, interacts with Gemini, and controls the conversation flow.

💾 Simple Memory Node
Stores and retrieves chat context for maintaining conversation continuity.

🤖 Google Gemini Chat Model Node
Generates AI responses with contextual understanding.

🧰 MCP Client (executeTool)
Executes tools like Firecrawl based on AI instructions for dynamic data fetching.

⚙️ Installation & Setup
To run the system, you’ll need:

🔧 Prerequisites
n8n (self-hosted or cloud): n8n installation guide

Google Gemini API Key: Obtain from Google AI Studio

(Optional) Firecrawl API Key: Get from Firecrawl

📥 Workflow Import Instructions
Download the Workflow JSON
Get the .json workflow file from this repo.

Import into n8n

Open your n8n instance.

Navigate to the Workflows tab.

Click New → Import from JSON.

Upload the downloaded file.

Configure Credentials

Add your Google Gemini and Firecrawl API keys.

Open the respective nodes and paste the API keys in the Credentials section.

Activate the Workflow
Toggle the Active switch in the top right corner.

💬 Usage
Once the workflow is active, you can interact via the configured webhook.

🔄 Interaction Flow
Send a Chat Message
Message the webhook URL using:

A custom frontend

Another n8n workflow

A simple curl command (see n8n webhook docs)

Receive an AI Response
n8n processes the message via:

AI Agent → Context management and Gemini processing

MCP Client → Firecrawl data fetching (if required)

Response returned to the sender/output endpoint.

🧪 Example Interaction
User Message:

"I'm looking for the best cities for career opportunities in tech and a good quality of life."

Workflow Steps:

Message hits webhook.

AI Agent processes request using memory/context.

Google Gemini generates an initial response or request for more info.

If external data is needed, Firecrawl scrapes relevant job data.

AI synthesizes a recommendation like:

"Based on tech job growth and quality of life metrics, consider Austin, Berlin, or Bangalore."

