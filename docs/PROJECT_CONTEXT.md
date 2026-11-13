# TarazYar — Project Context

> Status: initial project brief; not a verified code architecture. Update this document only after inspecting the actual source.

## Product goal
TarazYar (تراز یار) is an accounting web application intended for mobile, tablet, and desktop. The target is a reliable Iran-ready product with international-grade engineering and UX quality.

## Product principles
- Preserve existing user data and established product behavior during upgrades.
- Keep customer balances in one continuous ledger.
- Use one unified receive/pay workflow rather than fragmented balance-entry sections.
- Purchases, sales, receipts, payments, and settlements must reconcile through the same account history.
- Settlement should have one clear payment-entry path.
- Keep UI behavior consistent across mobile, tablet, and desktop.

## Identity, licensing, and storage — intended behavior
- Google sign-in identifies the user; it is not itself a data-storage or backup solution.
- Main application synchronization should use the application's backend/database.
- Google Drive backup, if implemented, must be treated as a separate explicit feature.
- A user requests a license; an authorized owner approves it; activation should be automatic for the same verified Google identity (google_sub), without requiring the customer to enter a manual activation code.
- Renewal should follow the same controlled approval flow.
- Owner privileges must be enforced server-side, not by hiding a URL or UI element.

## Security and release rules
- Never commit passwords, API keys, OAuth client secrets, signing keys, peppers, database credentials, private backups, or production configuration.
- Keep private runtime state outside the public web root.
- Require HTTPS for authentication and secret-bearing operations.
- Do not claim tests passed unless they were actually run; distinguish automated, integration, and live-host tests.
- Do not deploy an artifact until its source, migrations, installation flow, and security-sensitive paths have been reviewed.

## Current work baseline
- A 40.1.2 package and its Persian reports/install guide were supplied for review in the ChatGPT project conversation.
- Review identified issues requiring correction before production installation, including owner-table field mismatch, possible duplicate license issuance during approval, and migration handling for NULL/empty/duplicate google_sub values.
- The next intended corrected release is 40.1.3. These findings must be rechecked against source code; this brief is not a substitute for source-level verification.

## Architecture documentation policy
As source becomes available, document actual modules, entry points, routes, database tables, migrations, trust boundaries, external services, and data flows. Mark unknowns explicitly. Never infer implementation details from this brief.
