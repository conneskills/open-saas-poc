# Definition of done for the first deployment

The first deployment is complete only when:

1. The source commit is known and reproducible.
2. The Wasp build succeeds from `template/app`.
3. The database is dedicated to this PoC and its migration state is recorded.
4. Registration and login work in the deployed environment.
5. An authenticated page reads and writes persistent data.
6. No secret is committed or exposed in client assets or logs.
7. A browser smoke test and server log check are attached as evidence.
8. The deployment URL, environment inventory, and known limitations are documented.
9. A rollback procedure exists, even if it is not executed in the first run.
10. Every unresolved issue is listed in `BLOCKERS.md` with an explicit owner and next action.

