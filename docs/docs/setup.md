# Setup Guide

This guide explains the basic steps for testing the workflows in an n8n environment.

## Requirements

You will need:

- An n8n instance
- An Apify account
- A Google account with access to Google Sheets
- A SerpAPI account
- An OpenAI account/API key
- A Vapi account

## Step 1 — Import the Workflows

Import the JSON files from the `workflows` directory into your n8n workspace.

The repository contains two workflows:

1. Lead discovery and filtering
2. AI voice outreach orchestration

## Step 2 — Configure Credentials

Connect your own credentials for the services used by the workflows.

Do not place API keys directly into the GitHub repository.

Use n8n's credential management system wherever possible.

## Step 3 — Configure Google Sheets

Create a lead spreadsheet with fields such as:

- Business Name
- Phone
- City
- State
- Rating
- Review Count
- Website
- Call Status
- Last Called At
- Follow Up Date
- Outcome Summary
- Transcript
- Meeting Booked
- Attempt Count

Update the workflow configuration with your own Google Sheet.

## Step 4 — Configure Lead Discovery

Set the cities or search terms you want the workflow to target.

Review the filtering logic and adjust it to your own lead-generation requirements.

## Step 5 — Configure AI Personalization

Connect your OpenAI credentials and review the prompt used to generate personalized outreach.

Test the generated output before using it in a live campaign.

## Step 6 — Configure Voice Calling

Connect your Vapi configuration.

Review the assistant, phone number, variables, and call behavior before making any live calls.

## Step 7 — Test

Start with a very small number of test leads.

Verify:

- Lead discovery
- Filtering
- De-duplication
- Google Sheets updates
- AI-generated openers
- Call status handling
- Outcome classification
- Follow-up updates

## Production Considerations

Do not immediately run the workflow against a large lead list.

Before production use, consider adding:

- Error handling
- Retry logic
- Rate limiting
- Monitoring
- Logging
- Alerting
- Data retention policies
- Additional validation
- Appropriate consent and calling compliance controls

## Security

Never commit:

- API keys
- Passwords
- Private credentials
- Customer information
- Private lead databases
- Private phone numbers
- Authentication tokens

The workflows in this repository should remain sanitized before publication.
