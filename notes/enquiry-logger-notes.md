# Task 3: Enquiry Logger (n8n workflow)

## What I built
A workflow that receives an enquiry and automatically saves it and alerts me:
Webhook → Edit Fields → Google Sheets (append row) → Telegram message

## How each node works
- **Webhook:** the entry point. It waits for a POST request with name, phone and message.
- **Edit Fields:** picks the fields I need and adds a timestamp.
- **Google Sheets (Append):** adds one new row per enquiry.
- **Telegram:** sends me an instant alert so I never miss a lead.

## What I learned
- Test URL vs Production URL: the Test URL works for one request after clicking "Listen for test event". The Production URL needs the workflow to be Active.
- Google Cloud OAuth setup: project, APIs, consent screen, test user, OAuth client. It was the hardest part.
- Field names must match exactly. In one test I sent `email` but the workflow reads `phone`, so the phone cell came out empty. The workflow did not crash, so silent mismatches are easy to miss.
- Green nodes only prove the flow ran, not that the data is correct. Always check the output.

## Real-world use
Small businesses (salons, clinics, shops) can use this to capture enquiries from a website form and get alerted instantly.

## Files
- Workflow: `workflows/enquiry-logger.json`
- Screenshots: `screenshots/`
