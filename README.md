# ARIA: Audio Research & Intelligence Assistant

An automated, AI-powered research assistant built with n8n. This workflow takes a research topic, fetches data from academic sources using Perplexity AI, generates a concise summary with OpenAI, performs content safety checks, converts the summary to audio, and delivers the final result via email—all while logging any potential policy violations.

## Features

*   **Trigger:** Start via n8n Form
*   **Academic Source Retrieval:** Fetches data from reputable sources (arXiv, PubMed, etc.) using the Perplexity API.
*   **AI-Powered Summarization:** Uses OpenAI's GPT models to create clear, conversational, and objective summaries.
*   **Content Safety Check:** Automatically classifies generated text for safety policy violations using OpenAI's Moderation endpoint.
*   **Audio Narration:** Converts the final research summary into spoken audio (MP3) for easy consumption.
*   **Smart Routing:** Flags and prepends warnings to summaries that have content violations.
*   **Violation Logging:** Extracts and logs details of any flagged content to a Google Sheet for review.
*   **Modular Design:** Easy to customize and extend.

## Workflow Overview

1.  **Trigger:** The workflow is initiated (e.g., by submitting an n8n form or via a webhook).
2.  **Perplexity Node:** The user's query is sent to Perplexity AI to retrieve information from academic sources.
3.  **OpenAI Summarization:** The retrieved context is sent to OpenAI to generate a structured, audio-optimized summary.
4.  **Content Moderation:** The summary is checked against OpenAI's moderation API.
5.  **Switch Node:** Routes the workflow based on if the content was flagged.
    *   **Flagged Path:** Extracts violation categories, logs them to Google Sheets, and prepends a warning to the summary.
    *   **Clean Path:** Continues normally.
6.  **Audio Generation:** The summary text is converted to an MP3 audio file.
7.  **Email Delivery:** The audio file and summary text are sent to the user's email address.
   
![n8n Workflow Diagram](./images/workflow-diagram.png) 
