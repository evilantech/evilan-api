# Umilan API — JavaScript SDK

AI-powered creative platform. Generate images, videos, and code with a single prompt.

## Installation

```bash
npm install umilan-sdk
```

## Quick Start

```javascript
import { UmilanClient } from 'umilan-sdk';

const client = new UmilanClient({
  apiKey: 'your_api_key'
});

// Chat
const reply = await client.chat.send('Hello, how are you?');

// Code generation
const code = await client.code.generate('Create a responsive navbar');

// Image generation
const image = await client.image.generate('A futuristic city at night');

// Video generation
const video = await client.video.generate('A slow pan over a foggy mountain valley at sunrise');
```

## Modules

| Module | Description |
|--------|-------------|
| [`chat`](./modules/chat.js) | Conversational AI with context awareness |
| [`code`](./modules/code.js) | HTML/CSS/JS code generation and editing |
| [`image`](./modules/image.js) | AI image generation from text prompts |
| [`video`](./modules/video.js) | AI video generation from text prompts |

## Client Configuration

```javascript
const client = new UmilanClient({
  apiKey:  'your_api_key',            // required
  baseUrl: 'https://umilan.onrender.com', // optional, default
  timeout: 30000,                     // optional, ms
  retries: 3                          // optional
});
```

## Error Handling

```javascript
import { UmilanError, RateLimitError, AuthError } from 'umilan-sdk';

try {
  const reply = await client.chat.send('Hello');
} catch (err) {
  if (err instanceof RateLimitError) {
    console.log('Rate limit hit, retry after:', err.retryAfter);
  } else if (err instanceof AuthError) {
    console.log('Invalid API key');
  } else {
    console.log('Error:', err.message);
  }
}
```

## Project Structure

```
api/
├── index.js           — main entry point
├── client.js          — base HTTP client
├── modules/
│   ├── chat.js        — chat module
│   ├── code.js        — code generation module
│   ├── image.js       — image generation module
│   └── video.js       — video generation module
└── utils/
    ├── errors.js      — custom error classes
    └── validator.js   — input validation helpers
```

## Connect

- X — [@umilantech](https://x.com/umilantech)
- GitHub — [umilantech/Umilan-API](https://github.com/umilantech/Umilan-API)
- Website — [umilan.xyz](https://umilan.xyz)
