---
description: >-
  Integrate the SimpleSpa Clients API with OpenAI and automate it daily using
  Node.js and cron
icon: code
---

# OpenAI & Cron Jobs

The SimpleSpa Clients API is very powerful and ideal for scheduled tasks. This page shows how to integrate the SimpleSpa Clients API with OpenAI and automate it on a daily basis using Node.js with cron.

| Step | Purpose                                                              | Technology               |
| ---- | -------------------------------------------------------------------- | ------------------------ |
| 1    | Fetch clients from your clients.php API                              | Node.js (axios)          |
| 2    | For each client, generate a custom message using OpenAI API          | Node.js (openai package) |
| 3    | Store or send the messages (e.g., save to file or trigger SMS/email) | Node.js                  |
| 4    | Schedule this script to run every day at 8 AM using node-cron        | Node.js (cron jobs)      |

## 1. Set Up a Node.js Project

```bash
mkdir simplespa-ai-messages
cd simplespa-ai-messages
npm init -y
npm install axios openai node-cron dotenv
```

Create a .env file:

```bash
OPENAI_API_KEY=your_openai_api_key_here
CLIENTS_API_URL=https://my.simplespa.com/api/v1/clients.php
CLIENTS_API_KEY=your_simplespa_api_key_here
```

## 2. Here’s the Node.js Script (scheduler.js)

```jsx
require('dotenv').config();
const axios = require('axios');
const { Configuration, OpenAIApi } = require('openai');
const cron = require('node-cron');
const fs = require('fs');

const openai = new OpenAIApi(new Configuration({
  apiKey: process.env.OPENAI_API_KEY
}));

const fetchClients = async () => {
  try {
    const response = await axios.post(
      process.env.CLIENTS_API_URL,
      {
        page: 1,
        per_page: 50, // You can adjust this
        last_visit_after: '2023-01-01' // Example filter
      },
      {
        headers: {
          'Authorization': `Bearer ${process.env.CLIENTS_API_KEY}`,
          'Content-Type': 'application/json'
        }
      }
    );
    return response.data.clients || [];
  } catch (error) {
    console.error('Error fetching clients:', error.response?.data || error.message);
    return [];
  }
};

const generateMessage = async (client) => {
  try {
    const prompt = `Write a short, friendly SMS inviting ${client.firstname} ${client.lastname} to schedule their next appointment. Mention their last visit was on ${client.last_visit || "an unknown date"}.`;

    const completion = await openai.createChatCompletion({
      model: "gpt-3.5-turbo",
      messages: [{ role: "user", content: prompt }]
    });

    return completion.data.choices[0].message.content.trim();
  } catch (error) {
    console.error('Error generating message:', error.response?.data || error.message);
    return null;
  }
};

const runScheduler = async () => {
  console.log("Starting SimpleSpa AI Scheduler...");

  const clients = await fetchClients();
  if (clients.length === 0) {
    console.log('No clients found.');
    return;
  }

  const results = [];
  for (const client of clients) {
    const message = await generateMessage(client);
    if (message) {
      results.push({
        client_id: client.client_id,
        name: `${client.firstname} ${client.lastname}`,
        mobile: client.mobile,
        message: message
      });
    }
  }

  // Save results to a JSON file
  const timestamp = new Date().toISOString().replace(/[:.]/g, '-');
  fs.writeFileSync(`messages-${timestamp}.json`, JSON.stringify(results, null, 2));

  console.log(`Generated ${results.length} personalized messages.`);
};

// Schedule this to run daily at 8:00 AM
cron.schedule('0 8 * * *', () => {
  runScheduler();
});

runScheduler(); // Run immediately on startup
```

## 3. To Run It

```bash
node scheduler.js
```

✅ fetchClients() calls the SimpleSpa API /api/clients.php with a real API key

✅ It automatically filters and fetches active clients

✅ OpenAI then creates a personalized message for each client

✅ Saves results in files (can be adjusted to send emails/SMS in this step)
