# ALB-DESK-001 — Safe Offline Desktop Migration

- **Type:** Product discovery and specification / engineering handoff
- **Date:** 2026-10-11
- **Assigned role:** `product-manager` in `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager`
- **Status:** READY FOR DISCOVERY
- **Priority:** High — leadership recommendation; not a declared production emergency
- **Due date:** UNSCHEDULED. User requested “ASAP”; no delivery date has been promised.
- **Authority:** User explicitly requested a ticket and goal so the Product Manager can start. This authorizes discovery/specification, not architectural changes, a release, or migration of live merchant data.
- **Meeting source:** [Two existing users: desktop migration meeting](2026-10-11-two-active-users-desktop-migration-product-ticket.md)

## Goal

Define and plan the smallest viable offline desktop path that lets **both existing users** continue their essential current workflows on their confirmed desktop environment, with existing data reconciled, recoverable backups, and a documented rollback path.

This is a target outcome, not a guarantee that migration currently works or is risk-free. Successful PM delivery produces an actionable specification and implementation/test backlog; successful user migration is a later milestone.

## Why this work is needed now

**KNOWN — user-reported:**

- Two people are currently using Albyta and want to migrate to a desktop application as soon as possible.
- These two users are not paying because the current functionality is fully offline.
- Desktop is reported as not currently usable. The failure mode and cause are OPEN.
- Current devices, target desktop operating systems, usage frequency, and data volumes are UNKNOWN.

This is evidence of an existing-user platform need. It is not measured retention, product-market fit, willingness to pay, or proof of broad desktop demand. Payment and stranger interviews are **not prerequisites** for supporting the two existing users.

The earlier meeting recommended delaying speculative desktop work without evidence of current-user demand. That premise must be revisited for this cohort. The earlier recommendation was PROPOSED, so no approved decision is being formally reversed.

## Work that can start immediately

1. Read relevant product, workflow, desktop, licensing, persistence, and backup/import code.
2. Document what is implemented versus what is only described in release notes.
3. Prepare the two-user discovery questionnaire and desktop reproduction checklist.
4. Draft user stories, migration constraints, acceptance criteria, engineering tasks, QA matrix, and Decisions Needed.
5. Record unknowns and route the relevant technical and data-trust questions to CTO/CEO review.

Do not wait for all user answers before reviewing the repository. Missing environment information blocks a finalized user-specific specification, not initial PM discovery.

## Required user discovery

Collect an environment record for **each** user. Do not assume both environments are the same.

| Field | Needed information |
|---|---|
| Current app | Platform, operating system/version, Albyta version, installation method |
| Desktop target | Operating system/version, architecture, approximate hardware/storage availability |
| Desktop problem | What they tried; command/installer and version; exact error, screenshot, or observed failure |
| Migration need | Why desktop is needed, essential workflows, urgency and acceptable fallback |
| Existing data | Approximate volume, backup availability, tables/features actually used |
| Receipts | Whether printing is necessary; printer model and connection type |
| Workflow | Single-user/single-device expectations; when a controlled rehearsal/cutover could occur |
| Data sharing | Permission for any export/fixture sharing; prefer synthetic or anonymized data where suitable |

User relationships, usage frequency, and desired operating systems have not been established. “ASAP” must be clarified rather than converted into an invented date.

## Relevant repository evidence

Participant inspections identified the following; no tests or builds were executed during the meeting:

- `package.json`, `electron/package.json`, `electron/electron-builder.config.json`: desktop scripts and scaffolding exist. Placeholder configuration does not establish the cause of desktop failure or runtime readiness.
- `components/BackupManager.tsx`: Excel export metadata version 4 and twelve table sheets. Import confirms a **full replacement** of destination records, then performs deletion/insertion via `db.executeSet`, saves, and reloads.
- The inspected backup component does not show an automatic pre-import backup, post-import row-count/control-total reconciliation, or a dedicated rollback artifact. Driver-level transaction/atomicity behavior remains unverified.
- Exported tables: `stocks`, `transactions`, `customers`, `debt_payments`, `consignments`, `expenses`, `settings`, `categories`, `expense_categories`, `units`, `payment_methods`, `held_transactions`.
- `components/providers/ExpirationProvider.tsx`: inspected portions include local-date warning/lock and secret-code behavior. Permanent free offline behavior must be reconciled with actual desktop licensing behavior; do not assume network requirements or the intended expiry policy.
- `CHANGELOG.md`: includes claims of Windows support and 96 tests. These are not fresh runtime verification.
- `.claude/WORKFLOWS.md`: defines PM, CEO, CTO, testing, backup, hardware, and release review requirements.
- `.claude/agents/product-manager.md`: defines the PM output format, stories, Given/When/Then criteria, edge cases, and Decisions Needed.

All relative paths above resolve from `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager`.

## Scope

### In scope

- Discovery for the two users' confirmed desktop environments.
- Reproduction/investigation tasks for the actual desktop problem.
- The smallest offline desktop implementation necessary for their essential existing workflows.
- A safe local export/restore migration specification preserving identities and related records.
- Backup, compatibility validation, destination reconciliation, and rollback requirements.
- Offline startup, persistence across restart, and single-user free-tier compatibility.
- Printer compatibility only if needed by either user.
- A controlled rehearsal on copies before any live cutover.

### Out of scope

- Cloud sync, online backups, remote access, subscriptions, or internet-dependent free-tier features.
- New prices, paywalls, reseller/white-label terms, or Lamongan expansion.
- Building every desktop OS before confirming the two users' needs.
- Feature expansion unrelated to migration or essential workflow parity.
- Concurrent use of independently edited source and desktop copies as if they were synchronized.

## PM deliverables and definition of done

PM discovery/specification is complete when:

1. Both user environment records are captured, or unresolved fields are explicitly marked as blocking finalization.
2. Existing desktop and migration behavior is mapped with concrete repository references and evidence limitations.
3. A reproducible desktop investigation task is defined; root cause is not marked resolved without engineering evidence.
4. User stories have Given/When/Then criteria, dependencies, failure cases, and a clear distinction between current behavior and proposed changes.
5. An implementation backlog is broken into bounded tasks: reproduction, platform remediation, migration safeguards, workflow verification, and release/cutover preparation. Implementation owners remain UNASSIGNED until assigned through the technical workflow.
6. A QA matrix covers populated data, repeat restore, failed import, offline restart, required hardware, and rollback.
7. CEO/CTO review points, release dependencies, and Decisions Needed are explicit.
8. A user migration/recovery guide is specified, including source preservation and when to stop using one device as the authoritative record.

**PM can start now. PM completion does not mean desktop is production-ready.**

## Proposed implementation and release acceptance criteria

These are specification targets, not statements that the current application already supports them. Engineering/QA must refine them against the actual schema and devices.

### Desktop readiness

- Given the confirmed target desktop environment, installation and startup succeed with the network unavailable and without unapproved online activation requirements.
- Essential workflows used by each user operate correctly offline; records remain accessible and consistent after application restart and desktop reboot.
- Single-user permanently free offline operation is preserved. Any conflict with existing expiration/date-lock behavior is a Decisions Needed item before changing licensing behavior.
- Required receipts print on the confirmed hardware; printing failure must not duplicate transactions or silently corrupt records.

### Backup and migration

- Before any destructive restore, source export and any populated destination have recoverable backups. The source device is not overwritten or wiped by the migration procedure.
- Export format/version, required tables and fields, record identifiers, relationships, and compatibility rules are documented and validated before destructive operations.
- Pre-migration baselines include per-table record counts and relevant transaction, stock, debt, expense, and consignment control totals. Use the implemented monetary and quantity precision; do not invent floating-point tolerances or treat current stock value as a substitute for all inventory history.
- Restore semantics are explicit: current behavior is full replacement, not merge. A repeat restore must not duplicate records or silently merge independently changed copies.
- Destination counts, identities/relationships, and relevant control totals reconcile with the baseline before users rely on the desktop records.
- Missing metadata, malformed or incompatible files, missing tables, repeat import, partial failure, insufficient storage, and interrupted operations have defined validation/recovery behavior.
- Backup enforcement and reconciliation are **proposed safeguards**, not existing verified functionality.

### Rehearsal, recovery, and cutover

- Run a rehearsal using synthetic/anonymized fixtures or consented copies; do not begin with the only copy of live records.
- Preserve products, transactions, debts, consignments, settings, held transactions, and other applicable exported data; do not silently omit a table because it is not immediately visible in a cashier screen.
- If import, persistence, or reconciliation fails, stop migration and use the documented recovery path. Do not promise that calling `executeSet` alone guarantees recovery.
- Existing records remain authoritative until verification and user acceptance are complete. Define a cutover point so transactions entered after export are not silently lost.
- Document rollback, including how any new desktop records after cutover are handled. Restoring an old source backup must not silently discard later activity.
- Each user's successful workflow/reconciliation result is recorded separately; one successful device does not prove the second is ready.

## Review gates and responsibility boundaries

| Stage | Required review/evidence | Current status |
|---|---|---|
| PM discovery/specification | User-requested task; follow technical PM output/workflow | READY FOR DISCOVERY |
| Architecture/platform changes | CTO: native runtime, storage/persistence, drivers, dependencies, module boundaries, required printers | PENDING; holder/approval UNKNOWN |
| Migration/financial/data changes | CEO: money, stock, tax, destructive restore, stored data, trust and recovery | PENDING; holder/approval UNKNOWN |
| QA | Executed tests, populated-data scenarios, actual confirmed hardware and migration rehearsal | NOT EXECUTED in meeting |
| Release/cutover | Workflow-specific QA/release reviews, CEO/CTO where applicable, release-owner version approval and user cutover acceptance | BLOCKED pending evidence/reviews |

Review roles do not have to imply hiring separate people; use the coding project's actual workflow. No approval is implied by naming a role or by a build script existing.

## Decisions Needed

- Confirm each target OS and minimum environment.
- Confirm the exact essential workflows and any printer requirement.
- Diagnose the actual desktop failure; do not equate a placeholder app ID with the cause.
- Resolve schema/format compatibility and destructive import semantics.
- Decide and verify backup enforcement, reconciliation, and recovery design.
- Clarify free offline licensing versus current local-date locks.
- Assign implementation/test owners, establish reviewed priority, and estimate a delivery schedule after discovery.
- Obtain required review and release evidence before installer delivery/cutover.

## Ready-to-paste handoff

> Work as the `product-manager` for ALB-DESK-001 in `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager`. Read this ticket and its linked meeting record. The user confirms two existing unpaid users already use the app and need desktop migration ASAP. Start discovery/specification now under the local PM/workflow rules. Inspect existing desktop, backup/import, persistence, and licensing behavior; identify current versus target platforms without assuming Android or Windows. Produce user stories, Given/When/Then acceptance criteria, a bounded implementation backlog, QA matrix, migration/rollback requirements, and Decisions Needed. Protect source and destination records; current restore is full replacement. Preserve the permanently free one-user offline tier. Do not implement, release, or cut over live data as part of this PM task. Route native/persistence concerns to CTO review and money/stock/tax/stored-data concerns to CEO review. Root cause and runtime test results are unverified until investigated.

## Flags

**Red flags:** Destructive import and unverified migration/recovery behavior can affect real merchant data.

**Yellow flags:** Desired desktop platforms, usage frequency, device requirements, root cause, licensing behavior, and deadline are not yet confirmed. Two unpaid users provide a useful need signal, not broad-market validation.
