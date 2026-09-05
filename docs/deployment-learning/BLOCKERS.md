# Blockers

| ID | Description | Impact | Owner | Status | Resolution / next action |
| --- | --- | --- | --- | --- | --- |
| BLK-001 | The repository is a Wasp template and has no committed Vercel deployment configuration. | The Vercel root directory and build/runtime shape are not yet proven. | Engineering | Open | Run the Wasp build, inspect `.wasp/out`, then choose static frontend plus backend strategy. |
| BLK-002 | The only Supabase project currently visible is `INACTIVE`. | It cannot be used as the PoC database without an explicit restore decision. | Infrastructure | Open | Select a dedicated active project or explicitly authorize restoration. |
| BLK-003 | `template/app/src/env.ts` imports validation schemas for optional modules. | A minimal deployment may fail startup without payment, analytics, upload, and AI variables. | Engineering | Open | Either provide test values for every imported schema or remove unused feature specs and imports in a documented commit. |
| BLK-004 | Background analytics is declared with Wasp `PgBoss`. | Serverless execution may not provide the same process lifetime as a long-running Wasp server. | Architecture | Open | Disable the job for the baseline or move it to a durable worker/cron design. |
