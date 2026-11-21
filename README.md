
AI-Powered Automated Resume Scanner (n8n + Groq + Google Workspace)

An end-to-end automated recruitment workflow built with n8n and Groq AI that streamlines candidate screening. It automatically extracts text from uploaded PDF resumes, evaluates candidates against job criteria using an LLM, logs shortlisted applicants into Google Sheets, and sends automated email responses via Gmail.
Form Submission (PDF)
Extract Text from PDF
Basic LLM Chain + Groq Chat Model
Code in JavaScript
If Condition
Google Sheets: Append Row
Gmail: Shortlist / Interview Email
Gmail: Polite Rejection Email
Evaluates & scores resume
Cleans & structures JSON output
Checks qualification threshold
True
False
<img width="767" height="455" alt="image" src="https://github.com/user-attachments/assets/161045ea-5b53-4153-9fb7-01ec2e194cab" />
<img width="575" height="271" alt="image" src="https://github.com/user-attachments/assets/25694164-590a-466f-aeb8-adc3789df5aa" />

How It Works

1. Resume Intake (On form submission): Captures applicant details and uploaded PDF resumes through an n8n web form.
2. PDF Parsing (Extract from File): Converts binary PDF documents into clean, machine-readable plain text.
3. AI Evaluation (Basic LLM Chain + Groq Chat Model): Analyzes extracted resume text at high speed using Groq inference, scoring candidate fit and extracting structured fields (Name, Email, Skills, Score, and Summary).
4. Data Sanitization (Code in JavaScript): Strips markdown artifacts from the raw LLM response and parses it into reliable JSON key-value pairs.
5. Automated Routing (If): Evaluates the candidate's score/status against a defined threshold to split qualified applicants from non-matches.
6. CRM Logging & Outreach (Google Sheets & Gmail):
	• Qualified Candidates: Appended automatically to a central RESUME SCANNER tracking spreadsheet, followed by an automated shortlist/next-steps email.
	• Unqualified Candidates: Receive an immediate, polite status update via Gmail
  
Tech Stack

• Orchestration: n8n (Self-Hosted / Docker)
• AI Inference: Groq Chat Model (LangChain Integration)
• Data Parsing: JavaScript (n8n Code Node)
• Database / Tracking: Google Sheets API
• Email Automation: Gmail OAuth2 API

Setup & Installation


1. Prerequisites

• A running n8n instance (Docker or npm)
• A Groq API Key
• A Google Cloud Project with Google Sheets API, Google Drive API, and Gmail API enabled (OAuth 2.0 Credentials)

2. Import the Workflow

1. Download the RESUME_SCANNER.json file from this repository.
2. Open your n8n dashboard and click Create Workflow.
3. Click the ... menu in the top-right corner and select Import from File.
4. Upload RESUME_SCANNER.json.

3. Configure Credentials

1. Groq Chat Model: Add your Groq API key.
2. Google Sheets (Append row in sheet): Connect your Google OAuth2 account and select your target spreadsheet and sheet tab.
3. Gmail (Send a message & Send a message1): Connect your Gmail OAuth2 account and customize the email templates.

4. Activate

Toggle the workflow status to Active / Published and share the Form Trigger's Production URL to start accepting resumes.

Security Note

All sensitive API keys, OAuth Client IDs, and personal credentials are stripped from the exported .json workflow file. Ensure you configure your own credentials locally before activating the workflow.
