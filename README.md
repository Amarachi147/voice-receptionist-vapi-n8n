# Voice Receptionist — AI Phone Booking Assistant (Vapi + n8n)

A phone-callable AI receptionist that handles patient calls end-to-end — triage, hospital FAQs, and appointment booking — without a human picking up.

## How it works
- **Voice frontend:** Vapi handles the phone number and voice conversation
- **Backend:** an n8n workflow exposed as an MCP server, called by Vapi as a set of tools
- **Triage-first:** the assistant's system prompt prioritizes urgent cases before collecting booking details

## Tools available to the assistant
- **Get current date** — keeps the AI aware of today's date for accurate scheduling
- **Check availability** — queries Google Calendar for open appointment slots (with time-window filtering to prevent double-booking)
- **Create booking** — books the appointment directly on Google Calendar
- **Knowledge base retrieval** — Pinecone vector store lets the assistant answer general hospital FAQs accurately

## Demo
Built for a fictional hospital ("Lekki Grace Hospital") to showcase the system without misrepresenting a real business.

## Stack
Vapi · n8n (MCP Server Trigger) · OpenAI · Pinecone · Google Calendar API

## Files
- `mcp-workflow.json` — the n8n MCP server workflow (exported), importable into your own n8n instance
- Vapi assistant configuration (system prompt) — see below
