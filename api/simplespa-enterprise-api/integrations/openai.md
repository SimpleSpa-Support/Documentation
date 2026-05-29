---
icon: code
---

# OpenAI

Here is an easy integration flow to start using OpenAI with the SimpleSpa API

## Flow

```
SimpleSpa API (/clients.php)
        ↓
Filter Clients (birthday month = this month)
        ↓
For Each Client:
    ↓
    → Create custom prompt (Name + Birthday)
    → Send to OpenAI (ChatGPT API)
    → Receive Birthday Message
    → (Optional) Send email via Mailchimp/Gmail
```

## React

```
npm create vite@latest birthday-ai-app -- --template react
cd birthday-ai-app
npm install axios
npm run dev
```

Then replace src/App.jsx with this:

```jsx
import { useEffect, useState } from 'react';
import axios from 'axios';

function App() {
  const [clients, setClients] = useState([]);
  const [messages, setMessages] = useState([]);
  const [loading, setLoading] = useState(true);

  const simpleSpaApiKey = 'YOUR_SIMPLESPA_API_KEY';
  const openaiApiKey = 'YOUR_OPENAI_API_KEY';
  const simpleSpaApiUrl = 'https://my.simplespa.com/api/v1/clients.php';
  const todayMonth = new Date().getMonth() + 1; // JS months are 0-indexed
  const todayDay = new Date().getDate();

  useEffect(() => {
    async function fetchClientsAndMessages() {
      try {
        // Step 1: Fetch clients
        const response = await axios.post(
          simpleSpaApiUrl,
          {
            dob_month: todayMonth,
            dob_day: todayDay,
            page: 1,
            per_page: 100
          },
          {
            headers: {
              Authorization: `Bearer ${simpleSpaApiKey}`,
              'Content-Type': 'application/json'
            }
          }
        );

        const clients = response.data.clients || [];
        setClients(clients);

        // Step 2: Generate birthday messages
        const newMessages = [];

        for (const client of clients) {
          const name = client.firstname || 'Client';

          const aiResponse = await axios.post(
            'https://api.openai.com/v1/chat/completions',
            {
              model: 'gpt-4', // or 'gpt-3.5-turbo'
              messages: [
                { role: 'system', content: 'You are a creative assistant for a spa.' },
                { role: 'user', content: `Write a short, warm, friendly birthday message for a client named ${name}.` }
              ],
              temperature: 0.7
            },
            {
              headers: {
                Authorization: `Bearer ${openaiApiKey}`,
                'Content-Type': 'application/json'
              }
            }
          );

          const message = aiResponse.data.choices[0]?.message?.content || 'Happy Birthday!';
          newMessages.push({ name, email: client.email, message });
        }

        setMessages(newMessages);
      } catch (error) {
        console.error('Error fetching clients or generating messages:', error);
      } finally {
        setLoading(false);
      }
    }

    fetchClientsAndMessages();
  }, []);

  return (
    <div style={{ padding: '2rem', fontFamily: 'Arial, sans-serif' }}>
      <h1>🎉 Birthday Messages</h1>

      {loading ? (
        <p>Loading...</p>
      ) : messages.length === 0 ? (
        <p>No birthdays today!</p>
      ) : (
        <div>
          {messages.map((item, index) => (
            <div key={index} style={{ marginBottom: '2rem', padding: '1rem', background: '#f9f9f9', borderRadius: '8px' }}>
              <h3>{item.name} ({item.email})</h3>
              <p>{item.message}</p>
            </div>
          ))}
        </div>
      )}
    </div>
  );
}

export default App;
```

## What This React App Does:

| Step | Action                                                       |
| ---- | ------------------------------------------------------------ |
| 1    | Calls your SimpleSpa API to get today’s birthday clients     |
| 2    | For each client, calls OpenAI and generates a unique message |
| 3    | Displays the generated birthday messages on the screen       |

## PHP

To do this directly on your webserver you can also create a PHP file that generates this message

```php
<?php
// Configuration
$simpleSpaApiUrl = 'https://my.simplespa.com/api/v1/clients.php';
$simpleSpaApiKey = 'YOUR_SIMPLESPA_API_KEY_HERE';

$openaiApiKey = 'YOUR_OPENAI_API_KEY_HERE';
$openaiModel = 'gpt-4'; // or 'gpt-3.5-turbo' if you want cheaper
$todayMonth = date('n'); // 1-12
$todayDay = date('j');   // 1-31

// 1. Fetch clients with birthday today
$clients = fetchClientsWithBirthdayToday($simpleSpaApiUrl, $simpleSpaApiKey, $todayMonth, $todayDay);

if (empty($clients)) {
    echo "No clients found with birthday today.\n";
    exit;
}

foreach ($clients as $client) {
    $firstname = $client['firstname'];
    $email = $client['email'];

    // 2. Generate a birthday message with OpenAI
    $message = generateBirthdayMessage($firstname, $openaiApiKey, $openaiModel);

    // Output
    echo "🎉 Birthday Message for {$firstname} ({$email}):\n";
    echo $message . "\n\n";
}

// Functions

function fetchClientsWithBirthdayToday($apiUrl, $apiKey, $month, $day) {
    $postData = json_encode([
        'dob_month' => (int)$month,
        'dob_day' => (int)$day,
        'page' => 1,
        'per_page' => 100
    ]);

    $ch = curl_init($apiUrl);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Authorization: Bearer ' . $apiKey,
        'Content-Type: application/json'
    ]);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $postData);
    curl_setopt($ch, CURLOPT_POST, true);

    $response = curl_exec($ch);
    if (curl_errno($ch)) {
        echo 'SimpleSpa API error: ' . curl_error($ch) . "\n";
        return [];
    }
    curl_close($ch);

    $data = json_decode($response, true);
    if (isset($data['clients']) && is_array($data['clients'])) {
        return $data['clients'];
    }
    return [];
}

function generateBirthdayMessage($clientName, $openaiKey, $model) {
    $prompt = "Write a short, warm, friendly birthday message for a client named {$clientName}.";

    $payload = json_encode([
        'model' => $model,
        'messages' => [
            ['role' => 'system', 'content' => 'You are a creative assistant for a beauty spa.'],
            ['role' => 'user', 'content' => $prompt]
        ],
        'temperature' => 0.7
    ]);

    $ch = curl_init('https://api.openai.com/v1/chat/completions');
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Authorization: Bearer ' . $openaiKey,
        'Content-Type: application/json'
    ]);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $payload);
    curl_setopt($ch, CURLOPT_POST, true);

    $response = curl_exec($ch);
    if (curl_errno($ch)) {
        echo 'OpenAI API error: ' . curl_error($ch) . "\n";
        return 'Happy Birthday!';
    }
    curl_close($ch);

    $data = json_decode($response, true);
    if (isset($data['choices'][0]['message']['content'])) {
        return trim($data['choices'][0]['message']['content']);
    }
    return 'Happy Birthday!';
}
?>
```

