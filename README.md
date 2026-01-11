# SecurityPrompt

Prompt for fixing security issues on Lovable 


First Let me Say this I got this Prompt from the Prompt Master Alex - https://www.linkedin.com/in/alexcinovoj/ who gave me permission to share it. Second this is my first README share on github.  

Paste this into Lovable: When you ahve any security Problem. 

Act like a Senior Application Security Engineer and Supabase/Postgres specialist auditing a React + Tailwind app deployed on Lovable Cloud, using a Supabase wrapper, with RBAC already implemented. Objective: Produce a concise, actionable security + performance audit focused on (1) Supabase RLS correctness and coverage, (2) RBAC enforcement end-to-end, (3) stale/unsafe code and files in the repo root, (4) logging/auditability, and (5) database migrations completeness and schema drift. Inputs I will provide in this chat (use only what’s provided; do not guess):
	
•	Repo tree (root + key folders) and any suspicious/legacy folders
Supabase schema (tables, views, functions), RLS policies, grants, and migration filesAuth/RBAC code paths (middleware, server actions, API routes), and any “service role” usageLogging setup (client/server), audit logs, and env var patterns Task (do not write new features): Audit the app and return a prioritized punch list of issues and fixes. Steps: 1) RLS: Verify RLS is enabled on every table; enumerate missing/overbroad policies per CRUD; check policy predicates, role/claims usage, ownership checks, and edge cases (joins, views, RPC, security definer functions). 2) RBAC: Trace role checks from UI → API/server → DB; identify any bypass paths (direct table access, service role leakage, missing checks, inconsistent role mapping). 3) Migrations: Confirm migrations are complete, ordered, and match the current schema; flag drift, partial migrations, and risky manual changes. 4) Repo hygiene: Scan for dead code, unused deps, debug flags, insecure helpers, exposed keys, deprecated auth patterns, and leftover test/admin routes. 5) Logging: Confirm security-relevant events are logged (auth, role changes, policy failures, privileged actions) without leaking secrets/PII. Output (TLDR, max 12 bullets):
	
•	Status: RLS, RBAC, Migrations, Repo hygiene, Logging (Pass/Needs work)
Top 5 risks (severity + why)Exact remediation steps with file paths and “what to change”Anything that looks safe but is actually risky (gotchas) Reference: :contentReference[oaicite:0]{index=0} Take a deep breath and work on this problem step-by-step.
