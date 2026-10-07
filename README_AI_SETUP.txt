ELIAS VERITON AI INCOME BUILDER — SECURE AI BACKEND

This version connects the 9 Pro tools to /api/ai.

IMPORTANT:
- Never put an OpenAI Secret API key in index.html.
- Set OPENAI_API_KEY as a server-side environment variable.
- Optional: set OPENAI_MODEL (default: gpt-5.6-sol).

DEPLOYMENT:
1. Upload this folder/project to a serverless host that supports the included Vercel API function.
2. Add environment variable OPENAI_API_KEY in that host's project settings.
3. Redeploy.
4. Open the deployed app URL. The Pro tools will call /api/ai.

LOCAL FILE TESTING:
Opening index.html by double-clicking will not provide /api/ai. The app will display a clear message until deployed with the backend.
