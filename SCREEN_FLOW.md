# Elias Veriton AI Income Builder v1.35.0 — Screen Flow

The main app flow is now sequential:

1. Screen 1 — Welcome
2. Screen 2 — Tell Us About You
3. Screen 3 — Your Income Opportunities
4. Screen 4 — Unlock Pro / Payment
5. Screen 6 — Payment Successful
6. Screen 7+ — Pro Dashboard and the remaining Pro/account/settings screens

A fresh browser/app load always starts on Screen 1.

The app prevents users from jumping directly to a later main-flow screen. The remaining dashboard and Pro tools become available after the main flow reaches the Pro Dashboard.

Paystack remains configured through Vercel at runtime; no test public key is hard-coded in the package.
