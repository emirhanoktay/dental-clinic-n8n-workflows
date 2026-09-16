# 🦷 Dental Clinic AI Assistant & Automation Suite

An advanced, production-ready **n8n workflow** designed for dental clinics to automate patient interactions, appointment bookings, cancellations, and notifications using Large Language Models (LLMs).

---

## 🚀 What This Workflow Does (`New Patient Registration`)

This automated AI receptionist named **"Teethy"** handles inbound patient messaging via WhatsApp/SMS through Twilio, guiding them through a natural conversation flow:

1. **Inbound Trigger:** Listens for incoming patient messages via Twilio (`Twilio Trigger`).
2. **AI Agent & LLM Integration:** Powered by Claude (Anthropic), the AI agent manages the conversation context, pricing information, and clinic working hours.
3. **Smart Conversation Flow:**
   - Asks for the patient's complaint/symptom.
   - Requests preferred day and time slots.
   - Collects personal details (First Name, Last Name, Phone Number).
4. **Calendar & Notification Management:**
   - Automatically creates or deletes appointments in **Google Calendar**.
   - Sends cancellation or booking notifications to the doctor via **Gmail**.
5. **Session Memory:** Uses **Redis Chat Memory** to track conversation states seamlessly across multiple interactions per user.

---

## 🛠️ Tech Stack & Integrations
* **Automation Engine:** n8n (Self-hosted / Cloud)
* **AI Model:** Anthropic Claude Sonnet via LangChain AI Agent nodes
* **Messaging:** Twilio (WhatsApp / SMS API)
* **Database & Memory:** Redis
* **Productivity & Sync:** Google Calendar API & Gmail API

---

## 📦 How to Import & Use

1. Download the [`new-patient-registration.json`](./workflows/new-patient-registration.json) file from the `workflows/` directory.
2. Open your n8n dashboard and import the JSON file.
3. Configure your own credentials:
   - **Twilio API**
   - **Anthropic (Claude) API**
   - **Google Calendar OAuth2 API**
   - **Redis Account**
   - **Gmail OAuth2 API**
4. Activate your workflow and link your Twilio webhook endpoint!
