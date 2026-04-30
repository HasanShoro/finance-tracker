# 💰 Personal Finance Tracker

A clean, minimal finance tracker built with plain HTML and Supabase.
Inspired by Apple's design language — white, simple, fast.

## Files

| File | Purpose |
|------|---------|
| `finance_family.html` | Private family version — connected to a real database |
| `finance_public.html` | Public template — plug in your own Supabase keys |

## Features
- Dashboard with budget vs spent progress bars
- Transaction log with income/expense filtering
- Monthly report — income, expenses, and what you're left with
- Admin view (password protected) — all-time data, month summaries, CSV export
- Powered by Supabase — data saves instantly, accessible from any device

## How to use the public template

1. Create a free account at [supabase.com](https://supabase.com)
2. Create a new project
3. Run this SQL in the SQL Editor:

\`\`\`sql
create table transactions (
  id bigint primary key,
  date text,
  type text,
  cat text,
  description text,
  amount numeric,
  month text,
  created_at timestamp default now()
);

alter table transactions enable row level security;

create policy "Allow all" on transactions
  for all using (true) with check (true);
\`\`\`

4. Go to Project Settings → API → copy your Project URL and anon public key
5. Open `finance_public.html` and replace:
   - `YOUR_SUPABASE_URL_HERE` with your Project URL
   - `YOUR_SUPABASE_ANON_KEY_HERE` with your anon key
6. Open the file in any browser — done

## Built with
- Plain HTML, CSS, JavaScript — no frameworks
- [Supabase](https://supabase.com) — open source database
- Inter font — via Google Fonts

## Author
Built by Hasan — Bay Area, CA
