# AI-Powered Customer Support Automation System using LangGraph

## About the Project

The AI-Powered Customer Support Automation System is a customer service automation solution developed using **LangGraph**, **LangChain**, and **Google Gemini**. The system is designed to automate the handling of customer support requests for ABC Technologies, a SaaS company providing cloud-based business management software.

The application accepts customer queries, identifies the type of issue, routes the request to the appropriate support department, retrieves relevant information from company documents using Retrieval-Augmented Generation (RAG), maintains customer conversation history using SQLite memory, performs human approval for sensitive requests, and generates professional customer responses through a supervisor agent.

This project demonstrates the practical use of modern Generative AI technologies to improve customer support efficiency while reducing response time and operational costs.

---

# Features

- Intent Classification
- Department Routing using LangGraph
- Specialized AI Support Agents
- Retrieval-Augmented Generation (RAG)
- SQLite Conversation Memory
- Human-in-the-Loop Approval
- Supervisor Agent
- Professional Customer Responses
- Modular Project Structure
- Easily Extendable Architecture

---

# Supporting Departments

The system supports four departments:

 Sales - Product information, subscription plans, pricing 
 Technical Support - Installation, application errors, login issues, configuration 
 Billing - Payments, invoices, refunds 
 Account - Password reset, profile update, account activation/deactivation 

---

# High-Risk Requests (needs human approval)

The following requests require human approval before a response is sent:

- Refund Requests
- Subscription Cancellation
- Account Closure
- Compensation Requests
- Escalation to Management

---

# Technologies Required

- Python 3.11
- LangGraph
- LangChain
- Google Gemini
- HuggingFace Embeddings
- ChromaDB
- SQLite
- PyPDF
- Streamlit
- Python Dotenv

---


# Installation

## Step 1

Clone the repository.

```bash
git clone https://github.com/SHIVS-02/Customer-Support-Automation/tree/main
```

Open the project directory.

```bash
cd CustomerSupportAutomation
```

---

## Step 2

Create a virtual environment.

### Windows

```bash
python -m venv venv
```

Activate it.

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## Step 3

Install all required libraries.

```bash
pip install -r requirements.txt
```

---

## Step 4

Create a `.env` file in the project root.

```text
GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
```

Replace the API key with your own Gemini API key.

---

## Step 5

Place the knowledge base documents inside the `documents` folder.

```
CompanyPolicy.pdf
PricingGuide.pdf
TechnicalManual.pdf
FAQ.pdf
```

---

## Step 6

Generate the vector database.

```bash
python rag/ingest.py
```

---

## Step 7

Run the application.

```bash
python app.py
```


---

# RAG

The system uses Retrieval-Augmented Generation to improve response accuracy.

The RAG pipeline performs the following steps:

1. Load PDF documents.
2. Split the documents into chunks.
3. Generate embeddings.
4. Store embeddings in ChromaDB.
5. Retrieve relevant context for customer queries.
6. Pass the retrieved context to the language model before generating a response.

---

# SQLite Memory

The application stores conversation history using SQLite.

Example:

Customer:

```
My name is David.
I have a billing issue.
```

Later:

```
What was my previous issue?
```

The system retrieves the previous interaction from SQLite and responds accordingly.

---

# Human-in-the-Loop

Certain requests cannot be automatically approved.

Examples include:

- Refund Requests
- Subscription Cancellation
- Account Closure
- Compensation Requests
- Escalation Requests

When such requests are detected, the LangGraph workflow pauses until a human supervisor approves or rejects the request.

---

# Supervisor Agent

The Supervisor Agent performs a final review before sending the response.

Responsibilities include:

- Grammar correction
- Policy compliance
- Response improvement
- Hallucination reduction
- Professional tone

---

# Sample Queries

## Query 1

```
What are your pricing plans?
```

Expected Department:

```
Sales
```

---

## Query 2

```
I forgot my account password.
```

Expected Department:

```
Account
```

---

## Query 3

```
My application crashes whenever I upload a file.
```

Expected Department:

```
Technical Support
```

---

## Query 4

```
I need a refund for my annual subscription.
```

Expected Department:

```
Billing
```

Human Approval:

```
Required
```

---

## Query 5

```
What was my previous support issue?
```

Expected Flow:

```
SQLite Memory Recall
```

---

# Future Enhancements

Possible future improvements include:

- Voice-based customer support
- Multi-language support
- Integration with CRM systems
- Email automation
- WhatsApp chatbot integration
- Sentiment analysis
- Live human agent handoff
- Dashboard for support analytics

---

# Learning Outcomes

Through this project, the following concepts are demonstrated:

- LangGraph Workflow Design
- Agentic AI Systems
- Conditional Routing
- Retrieval-Augmented Generation
- Vector Databases
- SQLite Memory
- Human-in-the-Loop AI
- Prompt Engineering
- Large Language Model Integration
- Multi-Agent Systems

---

# Authors

**Project Title:**

AI-Powered Customer Support Automation System using LangGraph

**Developed As Part of:**

Academic Project

---

# License

This project is developed for educational purposes only.
