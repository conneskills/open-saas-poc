# Blockers

| ID | Description | Impact | Owner | Status | Resolution / next action |
| --- | --- | --- | --- | --- | --- |
| BLK-001 | The repository is a Wasp template and has no committed Vercel deployment configuration. | The Vercel root directory and build/runtime shape are not yet proven. | Engineering | Open | Run the Wasp build, inspect `.wasp/out`, then choose static frontend plus backend strategy. |
| BLK-002 | The previously visible Supabase project `AI Platform API` is `INACTIVE`. | That project must not be used implicitly for the PoC. | Infrastructure | Resolved | A dedicated active project `open-saas-poc-db` (`enssrainstoczzbpdtgt`) was provisioned in `eu-central-1`; apply the application schema next. |
| BLK-003 | `template/app/src/env.ts` imports validation schemas for optional modules. | A minimal deployment may fail startup without payment, analytics, upload, and AI variables. | Engineering | Open | Either provide test values for every imported schema or remove unused feature specs and imports in a documented commit. |
| BLK-004 | Background analytics is declared with Wasp `PgBoss`. | Serverless execution may not provide the same process lifetime as a long-running Wasp server. | Architecture | Open | Disable the job for the baseline or move it to a durable worker/cron design. |
| BLK-005 | The included `tools/wasp` wrapper resolves Wasp `0.26.0`, while `main.wasp.ts` declares `^0.25.0`; the compile then needs a network download that this environment could not authorize. | The source/runtime compatibility and generated deployment artefact are not yet proven. | Engineering | Open | Pin and run a compatible CLI version in an environment with package-network access, then record the generated output. |
