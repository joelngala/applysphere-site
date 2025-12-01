# applysphere-site
Applysphere site
ApplySphere - AI-Powered Job Application Automation

Overview

ApplySphere uses Gemini Vision AI to automatically fill job applications on Greenhouse. The system:

Collects your profile once
Generates ONE master resume + cover letter PDF from your profile
Searches for Greenhouse jobs
Uses YOUR ApplySphere-generated resume + cover letter for ALL applications
Auto-fills applications using Vision AI with Greenhouse optimizations
Stops before submit for your review
Project Structure

ApplySphere1.0/
├── backend/               # Rust API server (port 3030)
│   ├── src/
│   │   ├── main.rs                    # Main API server
│   │   ├── lib.rs                     # Module declarations
│   │   ├── models.rs                  # Data structures
│   │   ├── database.rs                # SQLite operations
│   │   ├── application_tracker.rs     # Application storage
│   │   ├── browser_automation.rs      # Chrome launcher
│   │   ├── gemini.rs                  # Gemini API client
│   │   ├── job_search.rs              # Google Custom Search
│   │   ├── resume_generator.rs        # ATS resume generation
│   │   └── pdf_generator.rs           # PDF creation
│   └── Cargo.toml
├── src/                   # React frontend (Tauri)
│   ├── App.tsx                        # Main app
│   ├── components/
│   │   ├── OnboardingForm.tsx         # Profile collection
│   │   ├── ResumeView.tsx             # Resume + attached jobs
│   │   └── ApplicationsView.tsx       # Tracker
│   └── styles/
├── src-tauri/             # Tauri backend
│   ├── src/
│   │   └── lib.rs                     # Tauri commands
│   └── Cargo.toml
├── extension/             # Chrome extension
│   ├── manifest.json
│   ├── popup/
│   │   └── popup.html                 # Extension UI
│   ├── scripts/
│   │   ├── service-worker.js          # Background orchestrator
│   │   ├── content-script.js          # Page interaction
│   │   └── platform-detector.js       # Greenhouse detection
│   └── icons/
└── .env                   # API keys (create from .env.example)
Prerequisites

Node.js (v18+)
Rust (latest stable)
Chrome browser
API Keys:
Google Gemini API key
Google Custom Search API key + Engine ID
