# GPT Action: Random UUID Generator

A simple MVP prototype of a ChatGPT GPT Action that returns a random UUID. Built with TypeScript and ready to deploy to Vercel.

## Features

- 🎲 Generates random UUIDs (v4)
- ⚡ Serverless function on Vercel
- 🔌 OpenAPI 3.1 specification for ChatGPT integration
- 📝 TypeScript for type safety

## Local Development

1. Install dependencies:
```bash
npm install
```

2. Run locally with Vercel CLI:
```bash
npm run dev
```

The API will be available at `http://localhost:3000/api/random-uuid`

## Deploy to Vercel

1. Install Vercel CLI (if not already installed):
```bash
npm i -g vercel
```

2. Deploy:
```bash
vercel
```

3. Follow the prompts to link your project and deploy.

## Configure ChatGPT Action

1. After deployment, note your Vercel URL (e.g., `https://your-app.vercel.app`)

2. Update `public/openapi.json` with your actual Vercel URL in the `servers` section

3. Go to ChatGPT and create a new GPT:
   - Go to https://chat.openai.com/gpts/editor
   - Click "Create a GPT"
   - Go to "Configure" tab
   - Scroll down to "Actions"
   - Click "Create new action"

4. Import the OpenAPI schema:
   - Either paste the contents of `public/openapi.json`
   - Or provide the URL: `https://your-app.vercel.app/openapi.json`

5. Test the action in ChatGPT:
   - Ask: "Generate a random UUID for me"
   - ChatGPT will call your API and display the result

## API Endpoint

### GET `/api/random-uuid`

Returns a random UUID with a timestamp.

**Response:**
```json
{
  "uuid": "550e8400-e29b-41d4-a716-446655440000",
  "timestamp": "2025-10-15T12:00:00.000Z"
}
```

## Project Structure

```
gpt-actions/
├── api/
│   └── random-uuid.ts    # Serverless function
├── public/
│   └── openapi.json      # OpenAPI specification
├── package.json
├── tsconfig.json
├── vercel.json
└── README.md
```

## Notes

- No authentication required for this MVP (add auth in production!)
- CORS is enabled to allow ChatGPT to call the API
- The OpenAPI spec follows OpenAI's requirements for GPT Actions

