# IntelliMail AI: Smart Institutional Communication

An automated email classification and response system built for educational institutions using **n8n**, **Google Gemini LLM**, and the **Gmail API**. Designed specifically for institutions like DYPCET, Kolhapur to streamline Training & Placement (T&P) communications, administrative inquiries, and student support.

## 🚀 Key Features

* **Automated Ingestion & Trigger:** Listens to incoming institutional emails in real-time via Gmail API triggers.

* **AI-Powered Classification:** Uses Google Gemini LLM to analyze email intent and categorize messages into structured tags (`GENERIC`, `NON_GENERIC`, priority inquiries, etc.).

* **Conditional Routing:** Intelligently routes incoming emails based on classification results (e.g., direct auto-reply for FAQs vs. draft generation for corporate placement proposals).

* **Human-in-the-Loop Review:** Automatically creates secure Gmail drafts for complex corporate queries (`NON_GENERIC`) requiring administrative inspection before sending.

* **Scalable Workflow Engine:** Built entirely on visual workflow automation using **n8n**.

## 🛠️ System Architecture & Workflow

The system operates on an automated 4-stage pipeline:

1. **Trigger:** New email arrives in the designated institutional inbox.

2. **AI Processing:** The message body and metadata are passed to Google Gemini via n8n HTTP Request/Node nodes for intent recognition and classification.

3. **Conditional Branching:** The workflow checks classification tags using switch/if nodes.

4. **Action Dispatch:** Sends an automated response or saves a review draft in Gmail.

*(Refer to your project report for the full n8n workflow diagram.)*

## 📋 Tech Stack

* **Workflow Automation:** n8n

* **Artificial Intelligence:** Google Gemini LLM API

* **Email Integration:** Gmail API

* **Backend / Scripting:** Node.js (internal n8n execution environment)

## ⚙️ Installation & Setup (Local n8n Deployment)

1. **Clone the Repository:**

   ```
   git clone https://github.com/your-username/IntelliMail-AI.git
   cd IntelliMail-AI
   
   ```

2. **Run n8n Locally (via Docker or npm):**

   ```
   npx n8n
   
   ```

   *(Or spin up using Docker Compose if using a self-hosted instance).*

3. **Import Workflows:**

   * Open your n8n dashboard (`http://localhost:5678`).

   * Import the workflow JSON file provided in the repository (`workflows/intellimail_workflow.json`).

4. **Configure Credentials:**

   * Set up your **Google Gemini API Key** in n8n credentials.

   * Authenticate your **Gmail OAuth2 account** for reading and sending/drafting emails.

## 📷 Sample Demonstration

| **Incoming Corporate Proposal** | **AI Classification & Draft Generation** | 
| *TechInnovations Solutions (SDE-1 / ₹7.5 LPA)* | *Classified as `NON_GENERIC` & Saved as Review Draft* | 

## 🔮 Future Scope

* **Multilingual Support:** Integration of regional languages (Marathi & Hindi) for local stakeholders.

* **Advanced Sentiment Analysis:** Priority queuing for urgent or distressed student messages.

* **ERP Integration:** Real-time database fetching from college portals for dynamic answers.

* **Multi-Channel Expansion:** Expanding from Gmail to WhatsApp Business official channels.

## 📜 License

This project is developed as part of academic curriculum requirements for DYPCET, Kolhapur. Feel free to use and modify for educational purposes.