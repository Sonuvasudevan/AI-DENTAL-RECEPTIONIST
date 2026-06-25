# 🦷 AI Dental Receptionist — Aarti

> An AI-powered voice receptionist built specifically for Indian dental clinics.
> Aarti answers every call, books appointments, classifies patient needs, and sends WhatsApp confirmations — 24/7, without a single missed call.

---

## 🚀 Why This Was Built

Every day, hundreds of dental clinics across India miss patient calls simply because the doctor is busy treating someone.

No receptionist = missed calls = lost patients.

Hiring a full-time receptionist costs ₹15,000–₹25,000/month. They take leaves. They make errors. They can't work at 8 AM or 9 PM.

**Aarti was built to solve exactly this.**

She is a warm, human-sounding AI voice agent that:
- Never misses a call
- Never takes a leave
- Never makes a booking error
- Works 24 hours, 7 days a week
- Costs a fraction of a human receptionist

---

## ✨ Features

### 🎙️ Natural Human Conversation
- Speaks warmly like a real Indian receptionist
- Uses natural acknowledgements — "Perfect!", "Got it!", "Sure!"
- Never sounds robotic or like a call center bot
- Adapts to slow speakers, fast speakers, and unclear audio

### 🪥 Smart Appointment Classification
Aarti automatically classifies every patient into the right appointment type:

| Type | Example |
|---|---|
| 🚨 Emergency | Severe tooth pain, swelling, bleeding |
| 🧼 Cleaning | Routine checkup, scaling, whitening |
| 🔧 Treatment | Root canal, extraction, filling, implant |
| 😁 Consultation | Braces, Invisalign, veneers, smile makeover |
| 🔄 Modification | Reschedule or cancel existing appointment |

### 🇮🇳 Built for Indian Patients
- Understands common Indian names perfectly
- If a name is unclear → immediately asks for spelling using **Indian school style** (A for Apple, B for Ball, C for Cat...)
- Never asks for NATO alphabet (Indian patients don't know it)
- Auto-adds +91 country code silently — never asks patient for it
- Recognizes Indian audio mishearing patterns (e.g. "gabby" → cavity, "route canal" → root canal)

### 📱 WhatsApp Confirmation
- Collects 10-digit number naturally — no country code confusion
- Adds +91 silently before sending notification
- Patient receives WhatsApp booking confirmation instantly

### ⏰ Time Validation
- Validates appointment time silently (never speaks the math aloud)
- Adds 30-minute buffer from current time automatically
- Rejects past time slots politely and asks for a new time

---

## 🔁 How It Works — Step by Step

```
1. Patient calls the dental clinic
2. Aarti greets warmly in Hindi/English
3. Collects full name (with Indian spelling support if unclear)
4. Collects WhatsApp number (10 digits, +91 added silently)
5. Understands reason for visit → classifies appointment type
6. Collects preferred date and time → validates silently
7. Confirms booking and sends WhatsApp notification
8. Triggers MakeAutomation webhook with all patient data
```

---

## 🛠️ Tech Stack

| Component | Tool |
|---|---|
| Voice AI Agent | Vapi / Retell AI (or similar voice platform) |
| LLM Brain | Claude (Anthropic) / GPT-4 |
| Automation | Make.com (formerly Integromat) |
| Notification | WhatsApp Business API |
| Appointment Data | Google Sheets / Airtable / CRM |

---

## 📋 Prompt Architecture

The entire behavior of Aarti is controlled through a structured prompt with these sections:

- `[Identity]` — Who Aarti is
- `[Personality]` — How she speaks, banned phrases, natural alternatives
- `[Listening Rules]` — How she handles unclear speech, feedback, silence
- `[Time Validation]` — Silent time checking with 30-min buffer
- `[Name Collection]` — Indian spelling support, no NATO alphabet
- `[WhatsApp Number Collection]` — 10-digit input, +91 silent add
- `[Conversation Order]` — Strict 6-step flow, never skips
- `[Appointment Classification]` — 5 types with decision rules
- `[MakeAutomation]` — Webhook trigger with all confirmed fields

---

## 📦 How to Use This

### Option 1 — Use as a Voice Agent Prompt
1. Copy the full prompt from `prompt.txt` in this repo
2. Paste it into your voice AI platform (Vapi, Retell, Bland AI, etc.)
3. Set `{{now}}` as a dynamic variable injected at call time
4. Connect your Make.com webhook for appointment booking
5. Connect WhatsApp Business API for patient notifications

### Option 2 — Customize for Your Clinic
1. Replace `Bright Smiles Dental Clinic` with your clinic name
2. Replace `Aarti` with your preferred receptionist name
3. Add your clinic's working hours to the time validation section
4. Update the WhatsApp webhook URL in MakeAutomation

---

## 🗂️ Files in This Repo

```
📁 AI-DENTAL-RECEPTIONIST
├── README.md          ← You are here
├── prompt.txt         ← Full Aarti prompt (copy-paste ready)
└── sample-flow.md     ← Example conversation walkthrough
```

---

## 💡 Real World Sales Insight

This was built and tested for independent dental clinics in Bangalore, India.

**Best fit clinics:**
- Solo doctor clinics (1 dentist, no dedicated receptionist)
- Clinics open early morning or late evening with no staff
- High-footfall clinics in IT corridors (Whitefield, Marathahalli, Yeshwanthpur)
- Any clinic where the doctor answers their own calls between patients

**The pitch that opens every door:**
> *"How many calls do you miss every day while treating a patient? What if every single call got answered, appointment booked, and WhatsApp confirmation sent — without hiring anyone?"*

---

## 🤝 Contributing

Feel free to fork this repo, customize it for other medical specialties (dermatology, physiotherapy, ophthalmology) and submit a PR.

---

## 📬 Contact

Built by an **AI Developer / Builder** passionate about making AI accessible to small clinics and local businesses across India.

Connect on [LinkedIn](#) | Star this repo if it helped you ⭐

---

> *"Every missed call is a missed patient. Aarti makes sure that never happens."*
