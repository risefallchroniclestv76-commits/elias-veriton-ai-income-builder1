# Elias Veriton AI Income Builder — Production setup

## Required server secrets (never put these in the app)
- `OPENAI_API_KEY` — required for AI tools.
- `PAYSTACK_SECRET_KEY` — required for server-side payment verification.

## Optional database/auth
The current app's local profile/saved-work storage is device-local. For real multi-device accounts, connect a managed database/auth provider and set its server-side credentials. Do not put database service-role keys in the client.

## Paystack production
Use the Live public key in the client only after testing. Keep the Live secret key in Vercel Environment Variables. Payment success must be verified by `/api/paystack-verify` before granting Pro access.

## Vercel
Deploy this folder as a Vercel project. Add the two required secrets in Settings > Environment Variables, then redeploy.


## Live Paystack
Add `PAYSTACK_PUBLIC_KEY` (your `pk_live_...` public key) and `PAYSTACK_SECRET_KEY` (your `sk_live_...` secret key) to Vercel Production. The client reads the public key from `/api/config`; the secret key stays server-side. Redeploy after saving. The payment flow verifies the transaction server-side before showing payment success.
