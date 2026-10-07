# Elias Veriton AI Income Builder v1.34.1 — Production Setup

Set these Vercel **Production** environment variables:

- PAYSTACK_PUBLIC_KEY = your Paystack Live Public Key (`pk_live_...`)
- PAYSTACK_SECRET_KEY = your Paystack Live Secret Key (`sk_live_...`)
- SUPABASE_URL = your Supabase Project URL
- SUPABASE_ANON_KEY = your Supabase Publishable Key
- OPENAI_API_KEY = your OpenAI API key

The Paystack public key is intentionally NOT hard-coded in the app. The browser receives it from `/api/config` at runtime.

The Paystack secret key remains server-side in `/api/paystack-verify.js`.

After changing Vercel environment variables, create/redeploy a Production deployment.

Never place the Paystack secret key in the client, HTML, JavaScript, GitHub, or this ZIP.

Pro access is activated only after server-side Paystack verification of successful status, expected amount, and expected customer email.
