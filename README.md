# n8n IP Reputation Checker with Discord Alerts

This n8n workflow lets you check the reputation of any IP address using the AbuseIPDB API. You send an IP address via webhook, and the workflow queries AbuseIPDB for abuse confidence scores, country info, and last reported date. The results are then sent as a formatted message to a Discord channel via webhook for real-time monitoring and alerts.

---

## Features

- Query IP reputation using AbuseIPDB's free API
- Sends formatted alerts to Discord channels
- Easy to customize and extend
- Use as a quick threat intel tool or monitoring service

---

## Setup Instructions

### 1. Get an AbuseIPDB API Key

- Sign up for a free account at [AbuseIPDB](https://www.abuseipdb.com/)
- Go to your account dashboard → API section
- Copy your API key

### 2. Create a Discord Webhook

- In your Discord server, go to the channel you want to send alerts to
- Click the ⚙️ (Settings) next to the channel name
- Choose **Integrations** → **Webhooks** → **New Webhook**
- Name your webhook, copy the **Webhook URL**, and save

### 3. Import the Workflow into n8n

- Download or clone this repo
- In n8n, click **Import** → **Import from File**
- Select the workflow JSON file (`ip-reputation-checker.json`)

### 4. Configure the Workflow

- Open the workflow in n8n editor
- In the **HTTP Request** node querying AbuseIPDB, replace the `Key` header value with your AbuseIPDB API key
- In the **Discord** node, replace the webhook URL with your Discord webhook URL
- Save and activate the workflow

---

## How to Use

- Send a POST request to your n8n webhook URL with a JSON body containing the IP address:

```json
{
  "ip": "8.8.8.8"
}
