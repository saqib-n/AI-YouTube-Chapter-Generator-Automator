# 📺 AI YouTube Chapter Generator & Automator

![n8n](https://img.shields.io/badge/Workflow-n8n-FF6584?style=for-the-badge&logo=n8n&logoColor=white)
![Gemini](https://img.shields.io/badge/AI_Model-Google_Gemini-8E75B2?style=for-the-badge&logo=google-gemini&logoColor=white)
![YouTube](https://img.shields.io/badge/Integration-YouTube_API-FF0000?style=for-the-badge&logo=youtube&logoColor=white)
![Apify](https://img.shields.io/badge/Scraper-Apify-97D700?style=for-the-badge&logo=apify&logoColor=white)

### 🚀 Overview
This repository contains an end-to-end **YouTube Automation Workflow** built in **n8n**.

Creating timestamps (chapters) for long videos is tedious manual work. This workflow solves that by using **Agentic AI** to read the video's transcript, understand the context, and generate precise, clickable chapters. It then **automatically writes them** to your video's description on YouTube.

---

### 🧠 System Architecture

The workflow automates the entire pipeline from URL to published description:

#### 1. Input & Extraction (The Scraper)
*   **Trigger:** You provide a YouTube Video URL via chat.
*   **Extraction:** The workflow uses **Apify** (via HTTP Request) to fetch the full transcript/captions and metadata of the video. This allows the AI to "watch" the video instantly without downloading the video file.

#### 2. The Chapter Agent (The Brain)
*   **Role:** Analyst & Editor.
*   **Logic:** The `Chapter Generator Agent` uses **Google Gemini** to analyze the transcript.
*   **Structured Output:** Using a strict parser, it enforces a specific format (e.g., `00:00 - Intro`), ensuring the timestamps are accurate and recognized by YouTube's algorithm.

#### 3. Execution (The Update)
*   **Role:** Publisher.
*   **Logic:** Instead of just giving you the text, the workflow connects directly to the **YouTube API**.
*   **Action:** It appends the generated chapters to your existing video description and saves the changes live on the platform.

---

### 🛠️ Prerequisites

1.  **n8n Instance:** Self-hosted or Cloud version.
2.  **Apify Account:** You need an API token to use the YouTube Scraper actor (to get transcripts).
3.  **Google Cloud Console:** Enable Gemini API.
4.  **Google Cloud OAuth:** Credentials for the YouTube Data API (to update descriptions).

---

### 📥 Installation

1.  Clone this repository.
2.  Open your **n8n** dashboard.
3.  Click **"Import Workflow"** and select the `.json` file.
4.  **Configure Credentials:**
    *   Add your Apify API Token.
    *   Connect your Google/YouTube OAuth account.
    *   Add your Gemini API Key.
5.  **Run:** Paste a YouTube link into the chat trigger and watch the description update automatically.

---

### 🔮 Use Cases

*   **Content Agencies:** Process dozens of client videos in minutes instead of hours.
*   **Podcasters:** Automatically generate "Show Notes" and topic breakdowns for long episodes.
*   **SEO Optimization:** Improve video discoverability by having keyword-rich chapters automatically added.

---

<div align="center">
  <p>Built with ❤️ by <a href="https://www.wolfxense.agency/">WolfXense AI</a></p>
  <p><i>Your AI Transformation Partner</i></p>
</div>
