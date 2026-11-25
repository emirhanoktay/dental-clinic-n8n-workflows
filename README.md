<p align="center">
  <img src="docs/banner.png" alt="Dental Clinic Automation" width="100%">
</p>

<p align="center">
  <b>Dental Clinic Automation is a set of five n8n workflows that run a clinic's front desk.</b> An AI receptionist books appointments over WhatsApp/SMS, reminders and follow-ups go out automatically, and the manager gets a daily schedule by email. It is a working reference build, not a packaged product.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/n8n-0F766E?style=for-the-badge&logo=n8n&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Claude-0F766E?style=for-the-badge&logo=anthropic&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/LangChain-0F766E?style=for-the-badge&logo=langchain&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Twilio-0F766E?style=for-the-badge&logo=twilio&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Google_Calendar-0F766E?style=for-the-badge&logo=googlecalendar&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Google_Sheets-0F766E?style=for-the-badge&logo=googlesheets&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Gmail-0F766E?style=for-the-badge&logo=gmail&logoColor=F0FDFA">
  <img src="https://img.shields.io/badge/Redis-0F766E?style=for-the-badge&logo=redis&logoColor=F0FDFA">
</p>

---

## Features

- **AI receptionist ("Teethy")** — Answers patient messages about symptoms, prices and hours via Claude, with Redis chat memory.
- **Calendar booking** — Creates and cancels appointments in Google Calendar and alerts the doctor by Gmail.
- **Appointment reminders** — A scheduled job sends 24-hour reminders and logs them in Google Sheets.
- **Daily clinic report** — Emails the next 24 hours of appointments each morning.
- **Post-treatment follow-up** — Sends check-in messages on days 1, 2 and 3 after a procedure.
- **Global error alerts** — Emails the workflow name and error message when any workflow fails.

## Screenshots

Diagrams rendered from the exported workflow JSON files (not screenshots of the n8n editor). Solid arrows are the main flow, dashed arrows are AI sub-connections.

<p align="center">
  <img src="docs/screenshots/new-patient-registration.png" width="48%">
  <img src="docs/screenshots/appointment-reminder.png" width="48%">
</p>
<p align="center">
  <img src="docs/screenshots/daily-report.png" width="48%">
  <img src="docs/screenshots/post-treatment-followup.png" width="48%">
</p>
<p align="center">
  <img src="docs/screenshots/error-notification.png" width="48%">
</p>

## How It Works

A patient writes to the clinic's WhatsApp or SMS number. Twilio hands the message to the registration workflow, where a Claude agent with Redis memory answers questions and, when the patient agrees on a time, creates the event in Google Calendar and notifies the doctor. Each day a scheduled workflow reads the calendar, matches events to patient records in Google Sheets and sends reminders, while another emails the manager the day's schedule. After a treatment, a follow-up workflow compares dates in the sheet and sends the day 1, 2 and 3 messages. Any failure triggers the error workflow, which emails the details.

## Setup

1. Clone the repo and open your n8n instance.
2. Import the files in `workflows/` via **Add workflow → Import from File**.
3. Create your own credentials (Anthropic, Twilio, Google, Redis) and attach them to the nodes.
4. Point the Google Sheets and Calendar nodes at your own sheet and calendar, and set the error workflow in each workflow's settings.

## Limitations

- Built and tested as a reference; it has not been run in a live clinic.
- Patient data passes through Twilio, Anthropic and Google. Review privacy and consent rules (e.g. KVKK/GDPR) before real use.
- Credentials are not included and must be created by you.

## Contact

<p align="center">
  <a href="https://www.linkedin.com/in/emirhanoktay"><img src="https://img.shields.io/badge/LinkedIn-0F766E?style=for-the-badge&logo=linkedin&logoColor=F0FDFA"></a>
  <a href="https://instagram.com/emirhannoktayy"><img src="https://img.shields.io/badge/Instagram-0F766E?style=for-the-badge&logo=instagram&logoColor=F0FDFA"></a>
  <a href="mailto:emirhanoktayy1@gmail.com"><img src="https://img.shields.io/badge/Gmail-0F766E?style=for-the-badge&logo=gmail&logoColor=F0FDFA"></a>
</p>
