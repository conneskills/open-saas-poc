# Deployment learning log

This directory records the first direct deployment of `open-saas-poc`.

The purpose is to capture the reproducible path that will later be encoded as
skills, instructions, contracts, and Paperclip tasks. This is an operational
record, not a replacement for the application documentation.

## Scope of the first run

- Validate the Wasp application build from `template/app`.
- Deploy the smallest useful Open SaaS baseline.
- Use a dedicated non-production PostgreSQL database.
- Keep payments, analytics, file uploads, and the AI demo disabled until the
  core application is healthy.
- Record every command, decision, failure, workaround, and verification.

## Current status

| Area | Status | Evidence / next action |
| --- | --- | --- |
| Git fork | Ready | `origin` is `conneskills/open-saas-poc`; `upstream` is `wasp-lang/open-saas` |
| Wasp build | Pending | Run the pinned project tool from `template/app` |
| Vercel project | Pending | Create/link after confirming the correct deployment shape |
| PostgreSQL | Blocked | The visible Supabase project is inactive; do not restore or mutate it implicitly |
| Secrets | Pending | Add only after the target environments and feature scope are fixed |
| Core smoke test | Pending | Register, sign in, load authenticated page, and verify persistence |
| Production deploy | Pending | Do not call this complete until the smoke test and rollback path pass |

## Evidence convention

Every run should add an entry to `BLOCKERS.md`, `DECISIONS.md`, or the relevant
runbook section. Never store secret values, tokens, private keys, or complete
connection strings in this directory.

