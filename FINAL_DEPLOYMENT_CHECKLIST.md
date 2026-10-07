# FINAL DEPLOYMENT CHECKLIST — v1.38

1. Deploy this ZIP to the existing LIVE Vercel project.
2. Keep `SUPABASE_URL` and `SUPABASE_ANON_KEY`.
3. Keep LIVE `PAYSTACK_PUBLIC_KEY` and `PAYSTACK_SECRET_KEY`.
4. Add `OPENAI_API_KEY` and optionally `OPENAI_MODEL`.
5. For Claude, add `ANTHROPIC_API_KEY` and `ANTHROPIC_MODEL`.
6. For redundancy, set `AI_PROVIDER=auto` and configure both providers.
7. Redeploy after environment-variable changes.
8. Check `/api/health`: `aiConfigured:true`; inspect `providers` without exposing keys.
9. Check `/api/config`: Supabase values and `paystackPublicKey` are present; never expose secret keys.
10. Test AI Income Plan and each Pro AI tool.
11. Do not repeat the real Paystack payment; the existing successful payment remains valid.
12. Run final navigation and payment verification audit before Google Play work.
