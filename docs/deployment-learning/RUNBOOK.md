# First deployment runbook

## 1. Freeze the input

Record the source commit, Wasp version, Node version, package-lock checksum,
deployment target, database target, and enabled features before changing code.

## 2. Local validation

From `template/app`:

```bash
../../tools/wasp version
../../tools/wasp db migrate-dev
../../tools/wasp start
```

The migration and development commands are only valid after local environment
values have been reviewed. Do not paste their output if it contains secrets.

## 3. Core deployment slice

The first slice should contain only:

- landing page;
- email/password authentication;
- user session persistence;
- one authenticated page;
- PostgreSQL persistence;
- basic health verification.

Payments, OpenAI, analytics, S3 uploads, and social login are separate
activation slices. They must not be allowed to become accidental prerequisites
for the baseline.

## 4. Verification

The deployment is not complete until all of these are recorded:

- deployment URL and commit;
- database migration result;
- registration and login result;
- authenticated navigation result;
- browser console and network check;
- server log check;
- database connectivity check;
- rollback procedure and result or explicit reason it was not run.
