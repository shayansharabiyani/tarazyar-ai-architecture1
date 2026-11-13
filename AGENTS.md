# Instructions for AI agents working on TarazYar

1. Read `docs/PROJECT_CONTEXT.md` before proposing or changing code.
2. Treat that document as product requirements and review history, not proof of the current implementation.
3. Inspect the repository source before describing architecture or claiming a feature exists.
4. Preserve backward compatibility and user data. Never delete or rewrite production data as an automatic migration shortcut.
5. Keep the customer account balance as one continuous ledger; do not split receive/pay or settlement into unrelated balance systems.
6. License approval must be authorized server-side and idempotent. One purchase request must not create multiple active licenses. Bind activation to the verified identity subject, not a user-editable email or username.
7. Never hardcode credentials or commit secrets. Do not echo credentials in logs, reports, test fixtures, or documentation.
8. Validate installation and migration behavior on fresh and interrupted installs. Report tests as PASS, FAIL, or NOT RUN, with the environment stated.
9. Do not claim live Apache/Nginx, MySQL, OAuth, or production-host validation unless it was actually performed.
10. Prefer small, reviewable commits. Explain changed files, migration impact, rollback considerations, and remaining risks.
11. Do not publish a full application archive or production configuration to this public repository until it has been scanned for secrets and private customer data.
