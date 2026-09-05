# Decisions

## DEC-001 — Use the fork as the working origin

- **Decision:** local `origin` points to `https://github.com/conneskills/open-saas-poc.git`.
- **Upstream:** `https://github.com/wasp-lang/open-saas.git` remains configured as `upstream`.
- **Reason:** product changes must be isolated from upstream while retaining a clean update path.

## DEC-002 — Prove the smallest baseline first

- **Decision:** the first deployment validates authentication, one authenticated route, and database persistence.
- **Deferred:** payments, analytics, uploads, social auth, and the AI demo.
- **Reason:** these integrations introduce independent credentials, webhooks, runtime requirements, and failure modes.

## DEC-003 — Do not use the inactive Supabase project implicitly

- **Decision:** no restore, schema mutation, or production connection is made against the visible inactive project without an explicit infrastructure decision.
- **Reason:** reactivating or reusing an existing project can create cost, data-isolation, and ownership problems.

## DEC-004 — Do not infer deployability from the template source

- **Decision:** Vercel configuration will be chosen only after a successful Wasp compile/build and inspection of `.wasp/out`.
- **Reason:** Open SaaS is a Wasp project whose generated client and server artefacts determine the actual deployment shape.
