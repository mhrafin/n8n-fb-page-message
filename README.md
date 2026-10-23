# Messenger Automation

An intelligent Facebook Messenger automated sales and customer support assistant powered by **n8n**, **Google Gemini AI**, and **Google Sheets**.

[![n8n Version](https://img.shields.io/badge/n8n-v2.44.6-orange.svg)](https://n8n.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED.svg?logo=docker&logoColor=white)](https://docs.docker.com/compose/)

## What the project does

**Messenger Automation** is a production-ready workflow solution that integrates Facebook Messenger with an advanced AI Agent. It automatically handles customer inquiries, provides accurate product prices and stock availability from a Google Sheets inventory, answers frequently asked questions (FAQs), guides users through the checkout process, and logs confirmed orders directly into a Google Sheets database, with built-in AI guardrails for safety and topical alignment.

---

## Why the project is useful

- **AI-Powered Customer Support**: Leverages Google Gemini to maintain natural, human-like conversations with customers 24/7.
- **Real-Time Inventory & FAQ Sync**: Automatically queries Google Sheets for up-to-date product information and store policies without manual intervention.
- **Seamless Order Processing**: Guides users through data collection (Name, Mobile, Address, Quantity) and safely appends confirmed orders to your spreadsheet.
- **Safety Guardrails**: Includes built-in moderation checks to detect jailbreaks, inappropriate content (NSFW), and ensure conversations stay strictly within the business scope.
- **Dockerized n8n Stack**: Easy to deploy locally or on a cloud server using Docker Compose, complete with task runners and an isolated sandbox environment.

---

## How users can get started

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your machine or server.
- A **Facebook Developer Account** with a Meta App configured for Messenger.
- A **Google Cloud Project** with Google Sheets API and Google Drive API enabled, and a Service Account/OAuth2 credentials.
- A **Google Gemini API Key**.

### 1. Installation

Clone the repository and configure your environment variables:

```bash
git clone https://github.com/your-username/msg-automation.git
cd msg-automation

# Copy the example environment file
cp .env.example .env
```

Edit `.env` to configure your passwords, tokens, and domain settings:

```bash
# Generate necessary secrets and configure your domains
nano .env
```

### 2. Running with Docker Compose

Start the n8n stack in the background:

```bash
docker compose up -d
```

Access the n8n editor at `http://localhost:5678` (or your configured domain).

### 3. Importing the Workflow

1. Open your n8n instance in your browser.
2. Go to **Workflows** -> **Import from File**.
3. Select `workflows/messenger-automation.json`.
4. Configure your credentials:
   - **Google Sheets OAuth2 / API**
   - **Google Gemini (PaLM) API**
   - **Facebook Graph API (Header Auth for Meta Webhooks)**
5. Connect your Google Sheets document containing `products`, `faq`, and `orders` sheets.
6. Activate the workflow and set your Facebook Webhook URL to point to your n8n webhook endpoint.

---

## Where users can get help

- **Issues & Bug Reports**: [GitHub Issues](https://github.com/mhrafin/msg-automation/issues)
- **Documentation**: Check the [n8n Docs](https://docs.n8n.io/) for detailed node configuration and workflow guides.
- **Discussions**: [GitHub Discussions](https://github.com/mhrafin/msg-automation/discussions)

---

## Who maintains and contributes

### Maintainer

- **MHRafin** — Initial creator and maintainer.

### Contributing

We welcome contributions from the community! Whether it's reporting bugs, discussing new features, or submitting pull requests.
