# AI Backend Setup

This production build supports two server-side AI providers.

## Required for at least one provider
- OpenAI: `OPENAI_API_KEY`
- Claude: `ANTHROPIC_API_KEY` plus `ANTHROPIC_MODEL`

## Optional
- `OPENAI_MODEL` (defaults to `gpt-6-sol`)
- `AI_PROVIDER` = `auto` (default), `openai`, or `claude`

With `AI_PROVIDER=auto`, the backend tries OpenAI first and Claude second if both are configured. Keys are never sent to the browser and are not included in this ZIP.

## Vercel Production variables
Keep your existing Supabase and LIVE Paystack variables. Add whichever AI provider(s) you want. For redundancy, add both providers and set `AI_PROVIDER=auto`.

Never paste secret keys into `index.html`, GitHub, or the chat.
