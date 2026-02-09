# Project Blueprint: Phase 1 - Proof of Concept

## Phase 1 Goal
Create a functional, end-to-end pipeline that processes **one single data source (Congress.gov Bills)** and produces **one single, valuable output (Sponsor + Top Contributors)**. This proves the core concept and establishes our development rhythm.

## Phase 1 Tech Stack
*   **Language:** Python 3.11+
*   **Data Orchestration:** Simple cron-scheduled scripts → Evolving to Apache Airflow.
*   **Database:** SQLite (Initial) → PostgreSQL (Scale).
*   **External APIs:** Congress.gov, OpenSecrets.org.
*   **Version Control:** GitHub (here).
*   **Communication:** Discord/Matrix (TBD).

## Phase 1 Milestones
1.  **[MILESTONE 0] Environment Setup:** Establish GitHub org, create this doc. **DONE.**
2.  **[MILESTONE 1] Congress.gov Scraper:** A Python script that authenticates with the API, fetches the latest bills, and stores them in a SQLite DB. **TARGET: Week 1.**
3.  **[MILESTONE 2] OpenSecrets Integration:** A script that reads a bill's sponsor from our DB, queries OpenSecrets for their top contributing industries, and stores the result. **TARGET: Week 2.**
4.  **[MILESTONE 3] Human-in-the-Loop Interface:** A simple command-line or web tool that presents a new bill and its sponsor data, and allows a trusted user to write a plain-English summary. This summary is stored as our first "ground truth" training data. **TARGET: Week 3.**
5.  **[MILESTONE 4] Public Data Dump & Website:** A static, public JSON file (or simple webpage) updated daily with the processed data for the last 10 bills. This is our first "transparency product." **TARGET: Week 4.**

## Immediate Next Actions
1.  Set up a Python virtual environment for development.
2.  Sign up for API keys:
    *   [Congress.gov API](https://api.congress.gov/sign-up/)
    *   [OpenSecrets API](https://www.opensecrets.org/api/admin/index.php?function=signup)
3.  Create a new repository for the **ingestion pipeline** code.
4.  Write `congress_scraper_v1.py`.

## Repository Structure Plan
We will use a multi-repo structure for clear separation of concerns:
*   `manifesto` (THIS REPO): High-level docs, mission, public log.
*   `data-ingestion`: All scrapers, API clients, and database schemas.
*   `analysis-core`: The AI/ML models, fine-tuning scripts, and impact logic.
*   `frontend`: The public website and dashboard.
*   `operations`: DevOps, deployment, and infrastructure-as-code.

---
*This is a living document. It will be updated as we make decisions and hit obstacles.*
