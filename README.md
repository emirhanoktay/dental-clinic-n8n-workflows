<img width="4000" height="2000" alt="al cil" src="https://github.com/user-attachments/assets/88b2dd00-421b-4af2-a26d-d1068fea52ae" />


# 🦷 Dental Clinic Automation & AI Suite

A production-ready collection of **n8n workflows** designed to automate dental clinic operations, patient relationship management (CRM), appointment scheduling, and administrative reporting using AI agents and third-party APIs.

---

## 🚀 Included Workflows & Architecture

### 1. New Patient Registration (`/workflows/new-patient-registration.json`)
* **What it does:** An AI-powered receptionist named **"Teethy"** that handles inbound patient messaging via WhatsApp/SMS through Twilio.
* **Key Features:** 
  - **Smart conversation engine:** Conducts natural conversations regarding symptoms, pricing, and clinic hours via Claude.
  - **Real-time schedule sync:** Automatically books or cancels appointments in Google Calendar.
  - **Instant failure alerts:** Sends immediate cancellation alerts to doctors via Gmail.
* **Tech Stack:** Anthropic Claude (LLM), Twilio, Google Calendar, Redis (Chat Memory), Gmail.

### 2. Appointment Reminders (`/workflows/appointment-reminder.json`)
* **What it does:** A scheduled background job that checks upcoming calendar events and dispatches 24-hour reminder messages to patients.
* **Key Features:**
  - **Autonomous background tasks:** Automatically cross-references calendar events with patient records stored in Google Sheets.
  - **Dynamic data logging:** Logs notification statuses to keep track of communication history.
* **Tech Stack:** Schedule Trigger, Google Calendar, Google Sheets, Twilio (WhatsApp/SMS).

### 3. Daily Clinic Report (`/workflows/daily-report.json`)
* **What it does:** Generates and emails a structured daily schedule summary to the clinic manager or doctor every morning.
* **Key Features:**
  - Fetches all scheduled events for the upcoming 24 hours.
  - **Custom data transformation:** Parses and formats event times and details cleanly using custom JavaScript code.
* **Tech Stack:** Schedule Trigger, Google Calendar, JavaScript Code Node, Gmail.

### 4. Post-Treatment Follow-up (`/workflows/post-treatment-followup.json`)
* **What it does:** Automatically tracks patient treatment dates from a database and sends personalized check-in messages on the 1st, 2nd, and 3rd days following a procedure.
* **Key Features:**
  - **Milestone tracking:** Dynamic date-diff calculations to trigger milestone-based care messages.
  - Automated multi-day conditional messaging via WhatsApp.
* **Tech Stack:** Schedule Trigger, Google Sheets, JavaScript Code Node, Twilio.

### 5. Global Error Notification (`/workflows/error-notification.json`)
* **What it does:** A robust error-handling mechanism that catches failures across any workflow in the suite.
* **Key Features:**
  - **Zero-downtime protection:** Instantly alerts administrators via email with the exact workflow name and error message when something goes wrong.
* **Tech Stack:** Error Trigger, Gmail.

---

## 🛠️ Tech Stack & Integrations
* **Automation Engine:** n8n
* **AI & LLMs:** Anthropic Claude (Sonnet) via LangChain
* **Messaging & Communication:** Twilio (WhatsApp & SMS API)
* **Database & Memory:** Google Sheets & Redis
* **Productivity & Workspace:** Google Calendar API & Gmail API

---

## 📦 How to Import & Use

1. Clone or download this repository.
2. Import any JSON file from the `workflows/` directory into your n8n instance.
3. Configure your own credentials:
   - Twilio API
   - Anthropic (Claude) API
   - Google Calendar, Sheets, and Gmail OAuth2 APIs
   - Redis Account
4. Activate your workflows and update the webhook endpoints accordingly.


