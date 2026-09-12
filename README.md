# AI Content Summarization Automation with n8n

An AI-powered workflow built with **n8n** that automatically summarizes
user-submitted text using the **Groq API** and stores the result in
**Google Sheets**.

## Overview

This project demonstrates how to connect an AI API with an automation
workflow and add basic error handling.

### Workflow

``` text
n8n Form
   ↓
Prepare Text
   ↓
Groq AI
   ↓
Google Sheets
```

### Error Handling

``` text
Workflow Error
     ↓
Error Trigger
     ↓
Google Sheets
     ↓
Error Log
```

## Features

-   Collects text through an n8n Form
-   Sends the text to Groq AI
-   Generates a short summary and 3 key points
-   Automatically saves results to Google Sheets
-   Logs workflow errors in a separate sheet
-   Uses n8n for end-to-end workflow automation

## Technologies Used

-   **n8n** - Workflow automation
-   **Groq API** - AI text summarization
-   **Google Sheets** - Result and error storage
-   **HTTP Request** - API integration

## Main Workflow Nodes

1.  **n8n Form Trigger**
    -   Receives the text submitted by the user.
2.  **Prepare Text**
    -   Prepares the submitted text for the AI request.
3.  **Groq AI Summarizer**
    -   Sends the text to the Groq API.
    -   Returns a concise summary and key points.
4.  **Google Sheets**
    -   Saves the date, input text, AI summary, and status.

## Error Handling Workflow

The project uses an **Error Trigger** workflow to handle failed
executions.

When an error occurs:

-   The error workflow is triggered.
-   Error information is captured.
-   The error is stored in the Google Sheets `Errors` sheet.

## Google Sheets Structure

### Sheet1

  Date        Input Text       AI Summary             Status
  ----------- ---------------- ---------------------- ---------
  Automatic   Submitted text   AI-generated summary   Success

### Errors

  Date        Workflow        Error
  ----------- --------------- ---------------
  Automatic   Workflow name   Error details

## Groq API Configuration

The workflow uses the Groq OpenAI-compatible Chat Completions API.

Endpoint:

``` text
https://api.groq.com/openai/v1/chat/completions
```

Example model:

``` text
openai/gpt-oss-20b
```

Add your API key securely as an authorization header:

``` text
Authorization: Bearer YOUR_GROQ_API_KEY
```

**Never publish your API key in GitHub repositories, screenshots, or
LinkedIn posts.**

## Setup

1.  Create a Groq API key.
2.  Create a Google Sheet named `AI Summarizer`.
3.  Add the required columns.
4.  Open n8n and create the main workflow.
5.  Add the Form Trigger.
6.  Add the Prepare Text node.
7.  Configure the HTTP Request node for Groq.
8.  Add Google Sheets to save the result.
9.  Create a separate Error Trigger workflow.
10. Connect the error workflow to the main workflow through the workflow
    error settings.
11. Test both successful and failed executions.

## What I Learned

This project helped me practice:

-   AI API integration
-   n8n workflow automation
-   HTTP requests
-   Data mapping and expressions
-   Google Sheets integration
-   Error handling
-   Building practical AI automation workflows

## Project Purpose

The goal of this project was to build a simple, practical AI automation
system while learning how **AI APIs, workflow automation, data storage,
and error handling** work together.

## Author

**Abdullah Imran**

AI Engineering \| Generative AI \| AI Automation \| Data & Marketing
Analytics
