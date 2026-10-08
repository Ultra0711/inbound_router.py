## Automated Inbound GTM Routing Webhook Engine

💡The Core Problem This Solves
In high-volume B2B enterprise funnels, speed-to-lead is everything. When a high-intent enterprise executive fills out a "Request a Demo" form, every minute the lead sits unassigned or un-enriched destroys the conversion rate.
Most marketing infrastructure suffers from sync latency—where data gets stuck or delayed between the web form, enrichment APIs, and the CRM.
The Solution: This project is a lightweight, programmatic routing engine written in Python. It acts as an automated webhook receiver that intercepts incoming web form payloads, cleans data noise, evaluates corporate sizing and territory rules, and prepares an instant data hand-off for the CRM in 0.04 seconds.
------------------------------
## 🛠️ System Architecture & Workflow

[Incoming Webhook] ──> [Data Sanitization] ──> [Territory Routing Engine] ──> [Structured CRM Payload]
Raw form data arrives  Filters personal spam  Matches company size & location  Instant database package


   1. Data Sanitization & Extraction: The system normalizes email inputs, strips accidental white space, and isolates the corporate domain while catching and separating generic consumer emails (Gmail, Yahoo, etc.).
   2. Programmatic Territory Routing: Instead of relying on slow, manual routing rules inside a CRM interface, the engine uses code to instantaneously evaluate company size and country matrix rules.
   3. Database Hand-off Ready: The system outputs an instantly readable data object (JSON) designed to update lead fields and alert sales reps without lag.

------------------------------
## 🚀 How to Run and Test This Project
You do not need a complex development environment like VS Code to test this system. You can run it instantly inside your browser.
## Option 1: Quick Browser Execution (Google Colab)

   1. Copy the code from inbound_router.py.
   2. Go to [google.com](https://colab.research.google.com/).
   3. Create a New Notebook, paste the code into a cell, and click the Play (▶) button.

## Option 2: Local Terminal Execution
If you have Python installed on your computer, clone this repository and run the script directly from your terminal:

git clone <your-github-repository-url>
cd <your-repository-folder-name>
python inbound_router.py

------------------------------
## 📊 Sample Output (Verification Test)
When the script processes a mock payload representing a high-intent enterprise lead from Europe, it automatically yields the following instantaneous routing execution:

Programmatic Routing Output Verification:
{
    "status": "success",
    "assigned_to": "Sarah Jenkins (Lead Enterprise AE)",
    "payload_sent_to_crm": {
        "account_domain": "ogury.com",
        "corporate_tier": "Tier_1_Enterprise",
        "routing_target": "Sarah Jenkins (Lead Enterprise AE)",
        "sync_latency_seconds": 0.04
    }
}

------------------------------
## 📈 GTM Impact Metrics

* Data Velocity: Reduces lead assignment latency from minutes/hours to a fraction of a second (0.04s).
* Database Governance: Automatically filters out low-intent public domain noise before it litters enterprise CRM pipelines.
* Rep Efficiency: Guarantees high-value target logos are immediately mapped to the correct regional VP or Account Executive without manual triage.
