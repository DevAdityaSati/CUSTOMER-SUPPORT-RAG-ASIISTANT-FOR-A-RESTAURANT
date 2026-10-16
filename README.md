# 🍽️ RAG Restaurant Support Assistant

An AI-powered restaurant support assistant built using **n8n, OpenAI, and Pinecone Assistant**. The system uses Retrieval-Augmented Generation (RAG) to answer customer questions using restaurant-specific knowledge, including menu items, prices, operating hours, and cancellation policies.

## 🚀 Project Overview

Restaurant customers often need quick answers about menus, prices, opening hours, and restaurant policies. Answering these repetitive questions manually can consume staff time.

This project automates restaurant support using an AI agent connected to a knowledge retrieval system. Customers can ask questions in natural language, and the assistant retrieves relevant restaurant information to generate context-based answers.

The project demonstrates how RAG and AI agents can be combined with workflow automation to build a practical customer support solution.

## ✨ Features

- **AI-Powered Customer Support:** Answers restaurant-related questions through a conversational interface.
- **Retrieval-Augmented Generation (RAG):** Uses relevant restaurant knowledge to ground responses.
- **Pinecone Assistant Integration:** Retrieves relevant information from the configured restaurant knowledge base.
- **Menu Information:** Answers questions about available dishes and their prices.
- **Restaurant Information:** Provides information about operating hours and restaurant policies when available in the knowledge base.
- **AI Agent Workflow:** Connects the user's query, retrieval tools, and response generation through n8n.
- **Automated Responses:** Reduces the need for manual responses to repetitive customer enquiries.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and AI agent orchestration |
| OpenAI | AI-powered response generation |
| Pinecone Assistant | Restaurant knowledge retrieval |
| RAG | Grounds responses in relevant external knowledge |
| HTTP/API integration | Connects the workflow to the configured Pinecone service |

## 🧠 What Is RAG?

Retrieval-Augmented Generation (RAG) is an approach that allows an AI model to use relevant information from an external knowledge source when answering questions.

Instead of relying only on its general training knowledge, the system retrieves information relevant to a user's query and uses it to generate a more context-specific response.

In this project, the restaurant knowledge base provides information that helps the assistant answer questions about the restaurant.

## ⚙️ How the Project Works

The workflow follows these steps:

1. **User Query:** A customer submits a question through the n8n chat interface.
2. **AI Agent:** The n8n AI Agent processes the request and uses the configured retrieval tool.
3. **Pinecone Retrieval:** Pinecone Assistant retrieves relevant information from the restaurant knowledge base.
4. **Context Processing:** The retrieved information is made available to the response-generation step.
5. **Response Generation:** OpenAI generates a natural-language answer using the relevant context.
6. **Final Answer:** The assistant returns the answer to the customer through the chat workflow.

## 🔄 Workflow Architecture

```text
Customer Question
       |
       v
n8n Chat Trigger
       |
       v
    AI Agent
       |
       v
Pinecone Assistant
(Retrieve Restaurant Knowledge)
       |
       v
Retrieved Context
       |
       v
OpenAI Response Generation
       |
       v
Final Answer to Customer
```

*This diagram represents the logical workflow. The exact node connections depend on the configured n8n implementation.*

## 💬 Example Queries

The assistant can handle questions such as:

- What time does the restaurant open?
- What vegetarian dishes are available?
- What is the price of paneer tikka?
- What is the restaurant's cancellation policy?
- Can you tell me about the restaurant's menu?

The responses depend on the information available in the configured restaurant knowledge base.

## 📚 Knowledge Base

The assistant uses restaurant-related information as its knowledge source, such as:

- Menu items and descriptions
- Food prices
- Restaurant opening and closing hours
- Cancellation policies
- Other restaurant-specific information

The knowledge source must be configured in Pinecone Assistant for the assistant to retrieve relevant information.

## 🔧 Setup and Configuration

### Prerequisites

Before recreating this project, you will need:

- An [n8n](https://n8n.io/) account or self-hosted n8n instance
- An [OpenAI Platform](https://platform.openai.com/) account and API credentials
- A [Pinecone](https://www.pinecone.io/) account
- Restaurant information to use as the knowledge base

### Step 1: Configure Pinecone Assistant

1. Sign in to Pinecone.
2. Create or select the Assistant used for the restaurant knowledge base.
3. Configure the restaurant's source documents or information.
4. Verify that the assistant can retrieve relevant information for sample queries.

### Step 2: Configure OpenAI

1. Set up the required OpenAI credentials.
2. Select the model used by your workflow.
3. Connect the credentials to the appropriate n8n node.

### Step 3: Import or Build the n8n Workflow

1. Create a workflow in n8n.
2. Add a chat trigger to receive user questions.
3. Configure an AI Agent node.
4. Connect the required OpenAI model.
5. Configure the Pinecone Assistant retrieval integration using the appropriate node or HTTP request.
6. Connect the retrieval and response-generation steps according to your workflow.

### Step 4: Test the Assistant

Try sample questions about menu items, prices, operating hours, and policies.

Check that the assistant retrieves relevant information and does not invent unsupported restaurant details.

*Exact configuration steps may vary depending on the Pinecone Assistant and n8n integrations used in your implementation.*

## 🔐 Security and Best Practices

- Never upload API keys, passwords, access tokens, or private credentials to GitHub.
- Remove credentials and sensitive execution data before sharing an n8n workflow export.
- Use environment variables or secure credential storage for API secrets.
- Avoid including confidential restaurant documents or customer information in a public repository.
- Test retrieval quality with different types of questions.
- Ensure responses remain grounded in the retrieved knowledge and acknowledge when information is unavailable.

## 🔮 Future Improvements

Potential enhancements include:

- Automatically updating menu items and prices through an API workflow.
- Adding multilingual customer support.
- Supporting restaurant reservations and order enquiries.
- Integrating customer support with messaging platforms.
- Adding fallback responses and escalation to human staff.
- Improving retrieval quality and testing answer accuracy.

## 🎯 Learning Outcomes

Through this project, I explored:

- Building AI agent workflows using n8n
- Applying Retrieval-Augmented Generation to a practical use case
- Integrating Pinecone Assistant with an AI workflow
- Using OpenAI for context-based response generation
- Connecting services through APIs
- Designing automated customer support systems

## 👨‍💻 Author

**Devaaditya Zade**

GitHub: [Add your GitHub profile URL]( https://github.com/DevAdityaSati)

## 📄 License

This project is available for learning and demonstration. Add a license file if you intend to specify permissions for reuse, modification, and distribution.
