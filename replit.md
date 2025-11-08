# Voice Plans App - Flora Edition

## Overview
A beautiful Flask web application with flora-themed design that converts WhatsApp voice notes into organized, categorized to-do lists with automatic date/time extraction and Google Calendar integration.

## Features
- **Beautiful Flora Design**: Modern, calming green-themed interface with professional aesthetics
- **Smart Categorization**: Tasks automatically organized into "Scheduled" and "Tasks" sections
- **Voice Note Processing**: Receives voice notes via Twilio WhatsApp webhook
- **AI Transcription**: Uses AssemblyAI for accurate English transcription
- **Date/Time Extraction**: AI automatically extracts dates and times from voice notes
- **Google Calendar Sync**: Automatically creates calendar events for scheduled tasks
- **Shareable Links**: Generate unique, beautiful links for each to-do list
- **Interactive UI**: Check off tasks, add new ones, delete, and share with ease

## Tech Stack
- Python 3.11
- Flask (web framework)
- Twilio (WhatsApp integration)
- OpenAI Whisper (audio transcription)
- FFmpeg (audio conversion)

## Environment Variables
The following secrets are configured in Replit Secrets:
- `OPENAI_KEY` - OpenAI API key for Whisper transcription
- `TWILIO_SID` - Twilio Account SID
- `TWILIO_TOKEN` - Twilio Auth Token

## How It Works
1. User sends a WhatsApp voice note to the configured Twilio number
2. Twilio forwards the audio to the `/webhook` endpoint
3. App downloads and converts audio to WAV format using FFmpeg
4. OpenAI Whisper transcribes the audio to text
5. Text is formatted into a to-do list
6. A unique shareable link is generated
7. Link is sent back to user via WhatsApp

## Endpoints
- `/` - Home page with app information and webhook URL
- `/webhook` - POST endpoint for receiving Twilio WhatsApp messages
- `/view/<id>` - View a specific to-do list by ID

## Setup Instructions
1. Configure Twilio WhatsApp Sandbox webhook to: `https://[your-replit-url]/webhook`
2. Ensure all environment secrets are set
3. Run the app on port 5000
4. Send a voice note to your Twilio WhatsApp number

## Current State
- App is running on port 5000
- All API credentials configured
- Ready to receive voice notes via WhatsApp webhook

## Last Updated
November 8, 2025
