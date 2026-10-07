# Live Paystack configuration — v1.34.3

The app's payment code is production-ready for Paystack Live mode, but the live credentials must remain in Vercel.

Required Production environment variables:

- `PAYSTACK_PUBLIC_KEY` = your Paystack Live Public Key (`pk_live_...`)
- `PAYSTACK_SECRET_KEY` = your Paystack Live Secret Key (`sk_live_...`)

The app does NOT hard-code either credential into the ZIP.

After adding/updating these variables in Vercel, redeploy Production. The app obtains the public key at runtime and sends the transaction reference to the server. The server verifies the transaction with Paystack before granting Pro access.

Do not test a real charge until the Vercel deployment shows the live public-key configuration is present.
