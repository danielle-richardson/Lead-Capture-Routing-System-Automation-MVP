# Lead Capture & Routing System (MVP)

## Overview
This project is a **demo lead automation system** built in [Make.com](https://www.make.com/).  
The goal is to show how leads can be captured, cleaned, deduplicated, and routed automatically — reducing manual work and giving instant visibility into “hot” opportunities.

**Project Flow:**  
1. A lead fills out a Google Form.  
2. The data goes into a Google Sheet (Leads_Raw).  
3. Make normalizes the data and generates a dedupe key (email).  
4. If the email already exists → the row is updated.  
5. If it’s new → a row is appended to Leads_Clean.  
6. If the lead is “hot” (budget > $5k) → an instant email alert is sent.  
7. The Leads_Clean sheet becomes the **reporting source of truth**.

---

## Workflow Diagram
- Form → Sheets (Leads_Raw) → Normalize & Dedupe → Update/Append (Leads_Clean) → Router (Hot/Normal) → Email Alert
(Add Image)


---

## Features Built
- Lead capture (Google Form → Google Sheets)
- Normalize & dedupe by email
- Update existing records or append new
- Hot lead routing (budget/campaign rules)
- Email alerts for hot leads

---

## Demo (Screenshots)
- Google Sheet (Leads_Clean tab with deduped rows)  
- Example “🔥 Hot Lead Alert” email  
(Add Image)

---

## How It Works
- **Trigger:** Watch new rows in Leads_Raw (Google Sheets)  
- **Normalization:** Create variables (trim spaces, lowercase email, add dedupe_key, timestamp)  
- **Dedupe:** Search Leads_Clean for email  
  - If found → Update Row (refresh notes, last_updated_at)  
  - If not → Add Row (insert normalized fields)  
- **Scoring:** Simple budget/campaign rules  
- **Routing:** Hot → Email alert; Normal → No alert  

---

## Future Enhancements
- Weekly digest (scheduled email with total leads, hot/warm/cold, top sources)  
- Error logging to Error_Log tab with Slack/email alerts  
- Looker Studio dashboard connected to Leads_Clean  

---

## Notes
- This is a **minimum viable build** (MVP) meant to demonstrate automation logic.  
- Rules (budget thresholds, campaign tags) can be expanded.  
