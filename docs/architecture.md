# Architecture

This project demonstrates a two-workflow n8n architecture for roofing lead generation and AI-assisted outbound outreach.

## Workflow 1 — Lead Discovery

The lead discovery workflow follows this process:

Target Cities
↓
Apify / Google Places
↓
Filter Businesses
↓
Check Phone Availability
↓
Check Existing Leads
↓
De-duplicate
↓
Google Sheets

The purpose is to create a clean lead list before any outreach takes place.

The workflow can be configured to target specific cities and identify businesses that match the campaign criteria.

## Workflow 2 — AI Outreach

The outreach workflow follows this process:

Google Sheets
↓
Select Eligible Lead
↓
Check Local Calling Hours
↓
Research Competitor
↓
Generate Personalized Opener
↓
Vapi Voice Call
↓
Check Call Status
↓
Classify Outcome
↓
Update Google Sheets
↓
Continue to Next Lead

## Main Components

### n8n

n8n acts as the central orchestration layer connecting the different services and controlling the workflow logic.

### Apify

Apify is used as the lead discovery/data collection component.

### Google Sheets

Google Sheets acts as the lead database for storing prospects, call status, outcomes, follow-ups, and other campaign information.

### SerpAPI

SerpAPI is used for search-based competitor research before outreach.

### OpenAI

OpenAI is used for generating personalized opening lines and classifying call outcomes.

### Vapi

Vapi handles the AI voice calling portion of the workflow.

## Design Principles

The system separates lead discovery from outreach.

This makes it possible to replenish the lead database independently from the outreach process.

The workflow also includes safeguards such as:

- Lead de-duplication
- Local calling-hour checks
- Call-status polling
- Outcome classification
- Follow-up tracking
- Delays between calls

## Important Note

This repository is a sanitized reference implementation.

Before deploying a similar workflow in production, review API limits, error handling, data protection, calling regulations, privacy requirements, and other requirements applicable to the specific use case.
