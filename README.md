# n8n-mcp-server-clien
"An n8n-powered Model Context Protocol (MCP) server and client for AI conversational flows, enhanced with Firecrawl for dynamic data integration.
Project Overview
This project provides a robust and flexible implementation of a Model Context Protocol (MCP) server and client, orchestrated using n8n workflows. It leverages the power of n8n for seamless integration and automation, Firecrawl for efficient data processing (e.g., web scraping or content extraction), and the Google Gemini Chat Model for advanced conversational AI capabilities. This setup allows for dynamic interaction with AI models, maintaining context across conversations, and integrating external data sources to enhance AI responses.
Features
•
n8n Workflow Orchestration: Utilizes n8n's visual workflow builder to connect various services and automate the MCP server and client logic.
•
Model Context Protocol (MCP): Implements a system for managing and maintaining conversational context with AI models.
•
Google Gemini Integration: Incorporates the Google Gemini Chat Model for intelligent and context-aware AI interactions.
•
Firecrawl Integration: Integrates Firecrawl for efficient data extraction and processing, enabling the AI to access and utilize external information.
•
Modular Design: The n8n workflow is designed with modularity in mind, allowing for easy expansion and customization of AI capabilities and data sources.
Architecture
The core of this project is an n8n workflow that acts as both an MCP server and client. The workflow typically involves the following key components:
•
When chat message received: This node acts as the entry point for incoming chat messages, triggering the workflow.
•
AI Agent: This central node processes the incoming messages, interacts with the Google Gemini Chat Model, and manages the conversational flow.
•
Simple Memory: Used for storing and retrieving conversational context, ensuring the AI maintains continuity across interactions.
•
Google Gemini Chat Model: The AI model responsible for generating responses based on the input and context.
•
MCP Client (executeTool): This node likely handles the execution of specific tools or actions based on the AI's directives, potentially involving Firecrawl for data retrieval.
Installation and Setup
To set up and run this project, you will need a running instance of n8n and access to the Google Gemini API. Firecrawl integration will require a Firecrawl API key.
Prerequisites
•
n8n: Ensure you have n8n installed and running. You can self-host it or use their cloud service. Refer to the official n8n documentation for installation instructions.
•
Google Gemini API Key: Obtain an API key for the Google Gemini Chat Model. You can find instructions on how to do this in the Google AI Studio documentation.
•
Firecrawl API Key (Optional): If you plan to utilize Firecrawl for data extraction, you will need an API key from Firecrawl.
Workflow Import
1.
Download the n8n Workflow: The n8n workflow for this project will be provided as a .json file. Download it to your local machine.
2.
Import into n8n:
•
Open your n8n instance in your web browser.
•
Click on the Workflows tab in the left sidebar.
•
Click the New button and then select Import from JSON.
•
Upload the downloaded .json workflow file.
3.
Configure Credentials:
•
Once the workflow is imported, you will need to configure the credentials for Google Gemini and Firecrawl (if used).
•
Locate the Google Gemini Chat Model node and the MCP Client node (if it uses Firecrawl) in the workflow.
•
Click on each node and update the respective API keys in the credentials section.
4.
Activate the Workflow: After configuring the credentials, ensure the workflow is activated by toggling the Active switch in the top right corner of the workflow editor.
Usage
Once the n8n workflow is active, the MCP Server and Client system is ready to use. The primary interaction point is typically through a chat interface that sends messages to the 'When chat message received' webhook of the n8n workflow.
Interacting with the MCP System
1.
Send a Chat Message: Send a message to the configured webhook URL of your n8n workflow. This can be done via various methods, such as:
•
A custom frontend application.
•
Another n8n workflow.
•
A simple curl command for testing purposes (refer to n8n webhook documentation for details).
2.
Receive AI Response: The n8n workflow will process your message, interact with the Google Gemini Chat Model, potentially fetch additional information using Firecrawl, and then return a response. The response will be sent back through the configured output of the 'AI Agent' or 'MCP Client' nodes.
Example Interaction
Let's consider an example where the MCP system is designed to recommend cities based on user criteria. A user might send a message like:
"I'm looking for the best cities for career opportunities in tech and a good quality of life."
The n8n workflow would:
1.
Receive the message.
2.
The 'AI Agent' would process this request, potentially using the 'Simple Memory' to recall previous parts of the conversation.
3.
The 'Google Gemini Chat Model' would generate a response, possibly asking for more specific criteria (as seen in the provided screenshot: "To recommend the 'best cities,' I need a bit more information about what criteria are important to you...").
4.
If the AI determines that external data is needed (e.g., current job market trends in tech), the 'MCP Client' node could trigger Firecrawl to scrape relevant information from job portals or economic reports.
5.
The AI would then synthesize this information and provide a tailored recommendation.
Troubleshooting
•
Workflow Not Triggering: Ensure the workflow is active in n8n. Check the webhook URL and ensure your messages are being sent to the correct endpoint.
•
API Key Errors: Double-check that your Google Gemini and Firecrawl API keys are correctly entered in the respective nodes' credentials.
•
No Response from AI: Verify that the Google Gemini Chat Model node is correctly configured and that you have sufficient API quotas.
•
Firecrawl Issues: If Firecrawl is not returning data, check your Firecrawl API key and ensure the target URLs are accessible and the scraping rules are correctly defined.
•
Context Not Maintained: Review the 'Simple Memory' node configuration to ensure it's properly storing and retrieving conversational context.
Contributing
We welcome contributions to this project! If you have suggestions for improvements, bug fixes, or new features, please feel free to:
1.
Fork the repository.
2.
Create a new branch (git checkout -b feature/YourFeature).
3.
Make your changes.
4.
Commit your changes (git commit -m 'Add some feature').
5.
Push to the branch (git push origin feature/YourFeature).
6.
Open a Pull Request.


