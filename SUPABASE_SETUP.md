# Supabase setup for v1.33

## 1. Vercel Environment Variables
Add these variables to your Vercel project for Production, Preview and Development:
- SUPABASE_URL = your Supabase Project URL
- SUPABASE_ANON_KEY = your Supabase Publishable/anon key

These are public client configuration values. Never put a Supabase service_role key in the browser.

## 2. Create the cloud table
In Supabase SQL Editor, run:

create table if not exists public.user_app_state (
  user_id uuid primary key references auth.users(id) on delete cascade,
  data jsonb not null default '{}'::jsonb,
  updated_at timestamptz not null default now()
);

alter table public.user_app_state enable row level security;

create policy "Users can read their own app state"
on public.user_app_state for select
using (auth.uid() = user_id);

create policy "Users can insert their own app state"
on public.user_app_state for insert
with check (auth.uid() = user_id);

create policy "Users can update their own app state"
on public.user_app_state for update
using (auth.uid() = user_id)
with check (auth.uid() = user_id);

## 3. Email authentication
Authentication -> Sign In / Providers -> Email should be enabled.

## 4. What v1.33 does
- Creates/signs users in with Supabase Auth.
- Pulls a signed-in user's saved app state from the cloud.
- Pushes local app state to the cloud after changes.
- Keeps local storage as a fallback.
- Does not expose a service_role key.
- Does not activate live Paystack by itself.

## Important
After adding Vercel environment variables, redeploy the Vercel project.
