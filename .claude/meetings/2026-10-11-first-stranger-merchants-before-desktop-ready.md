# Meeting: Initial Merchant Acquisition and Desktop Development Prioritization

- **Date:** 2026-10-11
- **Original topic:** `guys please help me how to get 3-5 merchants as a first target if the application is not done yet and still can't be used on desktop, should i finish first? or just straight finding the merchant? after you guys decide on that i need your help to how to get a first customer, i can't use my friends to avoid bias, need strager`
- **Purpose:** Address initial merchant acquisition, resolve whether to complete desktop before discovery, and establish recruitment methods for stranger merchants without friend bias.
- **Participants:** `startup-founder`, `startup-cofounder`, `executive-secretary`
- **Facilitator:** `main session`
- **Notes by:** `executive-secretary`
- **Record status:** Discussion record; recommendations remain proposals unless explicitly marked otherwise.

## Executive Summary

- The founder requested guidance on recruiting 3–5 stranger merchants while Albyta is incomplete and desktop is currently reported as unusable.
- Both leadership positions converged on a **discovery-first proposal**: begin stranger workflow and hardware discovery in Daerah Istimewa Yogyakarta rather than completing desktop speculatively.
- This is **not an approval to deploy or sell the unfinished product**. The proposed initial 3–5 merchants would be unpaid research design partners, not paying customers, and would retain their existing paper or POS records as the primary system.
- A staged sequence was proposed: **Stage A — Discovery → Stage B — Design Partners → Stage C — Gated Shadow Pilot → Stage D — Platform Decision**.
- Any shadow pilot involving live merchant money, stock, tax, or stored data is blocked pending the required CEO/finance-trust and CTO/technical reviews described in `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/.claude/WORKFLOWS.md`.
- The “96 tests passing” statement in `CHANGELOG.md` was not executed or independently verified in this meeting. Android runtime, SQLite persistence, and printer reliability were also not verified.
- The 40/60 reseller or white-label model is proposed for deferral. The founder’s baseline pricing estimates of Rp0 / Rp50,000 / Rp100,000 remain unvalidated. Suggested alternative prices of Rp49,000/month and Rp499,000/year are not adopted.
- No paying first customer was identified. No customer interviews, verified willingness-to-pay evidence, signed pilot agreements, revenue, or reseller contracts were supplied.

## Full Meeting Record

### Discussion by Topic

#### 1. Discovery timing versus desktop completion

**Known**

- The user reported that desktop cannot currently be used and that the product remains in development.
- Build scripts and desktop scaffolding exist in `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/package.json` and `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/electron/package.json`; this is evidence of configuration and dependencies, not proof of runtime readiness.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/electron/electron-builder.config.json` contains a placeholder `appId`. This supports that configuration is unfinished, but does not establish the technical root cause of desktop failure.
- The target launch geography is Daerah Istimewa Yogyakarta, Indonesia, with Lamongan, East Java planned as a later expansion. The initial target is small UMKM, not large enterprise.
- No device census exists for target merchants in Yogyakarta.

**Proposals**

- Start stranger discovery immediately instead of waiting for desktop completion.
- Temporarily pause or lower desktop priority while gathering evidence, without permanently cancelling desktop.
- Conduct 10–20 stranger workflow and hardware interviews before choosing the platform priority.
- Use observed merchant hardware, rather than assumptions, to decide whether desktop or mobile work should lead next.

**Concerns and dissent**

- Speculative desktop development may waste effort if target merchants use mobile devices, tablets, paper, or another system.
- Permanent desktop cancellation could exclude merchants who require Windows. The positions therefore support an evidence-based review rather than an irreversible cancellation.
- Participant thresholds such as 70% Android, 60% Windows, or 50% Windows were proposed hypotheses only. No threshold was approved and none is supported by field data.

**Open questions**

- What device operating systems and checkout hardware do target Yogyakarta merchants actually use?
- Is Android or desktop required for the first beachhead?
- What minimum hardware and operating-system requirements can Albyta support reliably?

#### 2. Stranger merchant discovery and design partners

**Known**

- The founder has technical knowledge and personal retail/café relationships but explicitly wants strangers to reduce friend bias.
- Zero merchant interviews have been conducted.
- The product documentation describes offline-first SQLite, dual UI modes, recipe and tax logic, and printer functionality in `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/feature.md` and `feature-payload.md`. These are product-description claims, not independent runtime or market validation.

**Proposals**

- Visit strangers during quiet periods, buy something first, observe the checkout workflow and device, then ask short problem questions.
- Ask about checkout speed, stock reconciliation, internet outages, current hardware, and existing workarounds without beginning with a product pitch.
- Invite only interested, relevant strangers into an unpaid design-partner study after disclosing that the app is unfinished and unproven.
- Keep the merchant’s existing ledger or POS as the primary record during any early shadow test.
- Do not promise stability, 24/7 support, a service-level agreement, or guaranteed data safety.
- Treat design partners as research participants, not paying customers or commercial traction.

**Concerns and dissent**

- Running unfinished software as the primary POS could cause financial discrepancy, stock errors, or loss of trust.
- A dual-record process may be burdensome, especially during busy periods.
- An Android-only qualification strategy is not justified until merchant hardware is observed.
- Any claim that the app is stable, approved, or ready for production would be inaccurate based on the evidence reviewed.

**Open questions**

- What qualification rubric should determine whether a stranger is suitable for a design-partner study?
- Will merchants tolerate parallel recording long enough to produce useful evidence?
- What specific workflow creates enough pain for a merchant to schedule a follow-up or shadow study rather than merely say the idea is interesting?

**Proposed truthful discovery wording**

> “Siang Mas/Mbak, saya sedang riset operasional kasir dan pencatatan stok UMKM di area Jogja untuk proyek software lokal. Boleh tanya sebentar? Saat rekap penjualan harian dan cek sisa stok, biasanya pakai buku, Excel, atau aplikasi? Bagian mana yang paling sering membuat hitungan selisih atau merepotkan?”

If the merchant describes a relevant problem and agrees to follow-up:

> “Saya sedang mengembangkan aplikasi kasir dan stok yang masih tahap pengembangan awal dan belum dijual. Saya mencari beberapa pemilik usaha untuk memberi masukan. Kalau cocok dengan perangkat yang dipakai, kita bisa mencoba pencatatan secara paralel tanpa mengganti cara utama toko, sehingga transaksi utama tetap aman di sistem yang biasa dipakai. Saya tidak menjanjikan aplikasinya sudah stabil; saya membutuhkan masukan jujur dan kita bisa berhenti kapan saja.”

These scripts are proposals, not commitments or approved sales copy.

#### 3. Pricing, commercial model, and geographic scope

**Known**

- The founder supplied unvalidated willingness-to-pay estimates: Rp0 for very small users, approximately Rp50,000/month for small-to-medium users, and up to Rp100,000/month for medium users.
- The founder proposed a 40% revenue share for retail partners and 60% retained by Albyta for infrastructure and operations.
- No stranger has paid, committed to pay, signed a letter of intent, or completed a paid pilot.
- Lamongan expansion is planned but not yet supported by Yogyakarta validation or a distribution agreement.

**Proposals**

- Defer reseller and white-label distribution until direct product use, retention, support burden, and unit economics are evidenced.
- Test direct willingness to pay after the core workflow is verified.
- Preserve the existing Rp0 / Rp50,000 / Rp100,000 figures as unvalidated hypotheses.

**Concerns and dissent**

- Thin-margin UMKM may prefer a free or manual alternative, so the paid conversion path is uncertain.
- A 40% partner share may not compensate partners for acquisition and support work, but this is an unvalidated commercial hypothesis rather than a measured conclusion.
- Suggested alternative prices of Rp49,000/month and Rp499,000/year were participant proposals only and were not adopted.

**Open questions**

- Which specific capability would cause a merchant to pay?
- Can support and infrastructure costs fit within the proposed prices?
- Is a reseller or white-label channel necessary, and who would carry merchant support responsibility?

#### 4. Technical verification and governance gates

**Known**

- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/.claude/WORKFLOWS.md` requires CEO review for changes touching money, stock, tax, or stored data, and CTO review for storage, sync, native platform, dependency, and hardware concerns.
- `CHANGELOG.md` contains a developer-written claim of 96 unit tests, but the test runner was not executed in this meeting. The pass status is therefore unverified here.
- Android runtime behavior, SQLite persistence, Bluetooth thermal-printer behavior, desktop runtime, and data-recovery behavior were not executed or independently verified in this meeting.
- No documented CEO or CTO approvals were supplied. Absence of approval evidence in the repository does not prove that no approval occurred outside the repository.

**Proposals**

- Before a shadow pilot handles live merchant money or stock, complete the applicable CEO and CTO reviews and document acceptance criteria.
- Verify the test suite independently rather than treating the changelog claim as a test result.
- Keep the existing merchant system primary and halt any shadow study on a discrepancy.

**Open questions**

- Who holds the CEO and CTO approval roles for this project?
- What exact tests and recovery procedures are required before a shadow pilot?
- Who owns the product-management decision for the discovery script, qualification rubric, and pilot criteria?

## Proposed Operating Sequence

The following is a facilitator reconciliation, not an approved execution plan:

1. **Stage A — Discovery:** Conduct 10–20 stranger workflow and hardware interviews in DIY Yogyakarta during quiet periods, initially without pitching the product.
2. **Stage B — Design partner qualification:** Invite 3–5 strangers with a relevant workflow, device, and concrete pain into an unpaid research study. Disclose that the software is unfinished and unproven.
3. **Stage C — Gated shadow pilot:** Only after the applicable technical and financial/data-integrity reviews, run a short parallel test while the merchant’s existing ledger remains primary. Stop on any discrepancy.
4. **Stage D — Platform and monetization review:** Use observed device mix and verified workflow performance to choose the next platform priority. Test willingness to pay only after the product is safe enough for the proposed test.
5. **Expansion:** Treat Lamongan expansion as deferred until the Yogyakarta beachhead produces evidence.

## Decisions

| ID | Decision / question | Status | Owner / approver | Rationale | Review or reversal condition |
|---|---|---|---|---|---|
| DEC-20261011-01 | Begin stranger discovery before completing desktop, rather than completing desktop speculatively. | PROPOSED | User / startup-founder | Learn actual merchant hardware and workflow before committing platform effort. | Revisit if discovery demonstrates that Windows desktop is required. |
| DEC-20261011-02 | Treat initial 3–5 recruits as unpaid research design partners, not paying customers. | PROPOSED | User / startup-founder | Product is incomplete and there is no validated commercial evidence. | Revisit after readiness gates and a defined paid offer. |
| DEC-20261011-03 | Retain the merchant’s existing ledger or POS as primary during any early shadow study. | PROPOSED | User / startup-founder | Reduces disruption while the product is unverified. | Do not reverse until runtime accuracy and recovery procedures are verified. |
| DEC-20261011-04 | Defer the 40/60 reseller and white-label model. | PROPOSED | User / startup-founder | Support burden and unit economics are unvalidated. | Revisit after direct usage, retention, and support costs are measured. |
| DEC-20261011-05 | Do not replace live merchant transaction or stock records until the applicable CEO and CTO gates pass. | BLOCKED | Required roles: CEO and CTO; role holders UNKNOWN | Required by the cited workflow rules and appropriate for money, stock, tax, stored-data, native, and hardware risk. | Unblock only after documented reviews and acceptance criteria. |
| DEC-20261011-06 | Do not adopt the proposed Rp49,000/month or Rp499,000/year prices; retain Rp0 / Rp50,000 / Rp100,000 as unvalidated founder hypotheses. | PROPOSED | User / startup-founder | No empirical willingness-to-pay evidence supports the change. | Revisit after stranger discovery and payment testing. |
| DEC-20261011-07 | Keep desktop as a temporary low-priority or paused workstream pending field evidence, not a permanent cancellation. | PROPOSED | User / startup-founder | Balances the opportunity cost of speculative engineering against the risk of excluding Windows merchants. | Review after device and workflow evidence is collected. |

## Action Register

| ID | Action | Owner | Due | Priority | Status | Dependency | Source | Last updated |
|---|---|---|---|---|---|---|---|---|
| ACT-20261011-01 | Draft a structured discovery interview and hardware-audit script covering checkout, internet outages, inventory pain, current tools, and devices without a product pitch. | UNASSIGNED | UNSCHEDULED | High | PROPOSED | None | Reconciliation | 2026-10-11 |
| ACT-20261011-02 | Conduct 10–20 off-peak discovery conversations with strangers in DIY and record hardware, workflow, pain, and follow-up interest. | UNASSIGNED | UNSCHEDULED | High | PROPOSED | ACT-20261011-01 | Reconciliation | 2026-10-11 |
| ACT-20261011-03 | Execute the test suite and document whether the `CHANGELOG.md` claim of 96 tests passing is reproducible. | UNASSIGNED | UNSCHEDULED | High | PROPOSED | None | Co-founder position; `CHANGELOG.md` | 2026-10-11 |
| ACT-20261011-04 | Define the design-partner qualification rubric, written disclosure, and immediate stop rules for discrepancies. | UNASSIGNED | UNSCHEDULED | High | PROPOSED | ACT-20261011-01 | Reconciliation | 2026-10-11 |
| ACT-20261011-05 | Review transaction calculations, stock mutations, tax handling, stored-data safety, and recovery procedures for the proposed shadow study. | Required CEO role; holder UNKNOWN | UNSCHEDULED | Critical | BLOCKED | Applicable technical/test evidence | `.claude/WORKFLOWS.md` | 2026-10-11 |
| ACT-20261011-06 | Review native Android behavior, SQLite persistence, printer compatibility, and relevant platform boundaries on target hardware. | Required CTO role; holder UNKNOWN | UNSCHEDULED | Critical | BLOCKED | Target hardware and technical evidence | `.claude/WORKFLOWS.md` | 2026-10-11 |
| ACT-20261011-07 | Diagnose and prioritize the Electron desktop issue if field evidence demonstrates meaningful Windows demand. | UNASSIGNED | UNSCHEDULED | Low pending discovery | PROPOSED | DEC-20261011-01 and field evidence | Founder/co-founder positions | 2026-10-11 |

No action above should be read as a confirmed personal commitment merely because a role appears in the discussion. Owners and due dates remain unassigned or unscheduled unless explicitly supplied.

## Risks and Blockers

| ID | Risk or blocker | Impact | Owner | Mitigation / next step | Status |
|---|---|---|---|---|---|
| RSK-20261011-01 | Merchant financial discrepancy or inventory data loss during testing. | High | UNASSIGNED; CEO review required | Keep existing records primary; use parallel testing only after applicable gates; stop on discrepancy. | OPEN / BLOCKED for live use |
| RSK-20261011-02 | Desktop engineering consumes effort before target hardware is known. | Medium | UNASSIGNED | Gather field hardware evidence before committing to desktop priority. | OPEN |
| RSK-20261011-03 | An indefinite desktop freeze excludes merchants who require Windows. | Medium | UNASSIGNED | Use a scheduled evidence review rather than permanent cancellation. | OPEN |
| RSK-20261011-04 | The 96-test changelog claim and native runtime are unverified. | High | UNASSIGNED; QA/CTO roles required | Execute tests and conduct relevant platform/hardware verification. | OPEN |
| RSK-20261011-05 | Incomplete Electron configuration and user-reported desktop failure block desktop commercial use. | Medium | UNASSIGNED; CTO review required | Reproduce and diagnose when field evidence justifies priority. | OPEN |
| RSK-20261011-06 | Merchants may resist duplicate records or have no time for a shadow study. | Medium | UNASSIGNED | Conduct short off-peak sessions and confirm consent before installation. | OPEN |
| RSK-20261011-07 | The 40/60 reseller model may create support costs greater than the retained revenue. | Medium | UNASSIGNED | Defer partner distribution; measure direct support and economics first. | OPEN |

## Decisions Needed

1. Should the user approve the proposed Stage A discovery sequence and the temporary desktop-priority pause? Required approver: user / startup-founder. Status: OPEN.
2. What exact discovery script and qualification criteria should be used? Product-manager owner/approver: UNKNOWN.
3. Who holds the CEO and CTO approval roles, and what evidence is required before any shadow pilot? Approvers: UNKNOWN role holders. Status: BLOCKED for live use.
4. What test execution and runtime verification will establish a safe enough technical baseline? Owner: UNKNOWN. Status: OPEN.
5. Which merchant device mix, pain signal, and follow-up behavior will justify prioritizing desktop, Android, or another platform? Owner: UNKNOWN. Status: OPEN.
6. What paid feature and price should be tested after product readiness? Owner: UNKNOWN. Status: OPEN.

## Record Gaps

- No stranger interviews, customer discovery transcripts, verified willingness-to-pay data, paid customers, revenue, or signed reseller agreements were supplied.
- The test suite was not executed in this meeting. The 96-test claim in `CHANGELOG.md` remains unverified here.
- Android runtime, SQLite persistence, thermal-printer behavior, and desktop runtime were not independently verified.
- The user reported that desktop cannot be used; the repository evidence does not establish the root cause.
- The placeholder Electron `appId` demonstrates unfinished configuration, not by itself that the application cannot run.
- No Yogyakarta device census or hardware distribution data exists.
- No minimum Android version, hardware requirement, Android-only requirement, absolute offline-uptime claim, or zero-risk data guarantee was verified.
- CEO/CTO role holders, product-manager authority, action owners, and deadlines are not identified.
- The record does not establish whether any approvals occurred outside the repository; it records only the absence of supplied approval evidence.

## Handoffs

| Role | Incoming context | Required output | Dependency |
|---|---|---|---|
| Product/discovery lead — role unassigned | Stranger discovery in DIY; small UMKM; need to avoid friend bias. | Draft Indonesian discovery script, hardware audit, design-partner qualification rubric, and disclosure notice. | ACT-20261011-01, ACT-20261011-04 |
| QA / technical verification — role unassigned | Changelog claims 96 tests; no execution evidence. | Test execution output and clearly scoped runtime result. | ACT-20261011-03 |
| CTO / technical lead — role holder UNKNOWN | Native platform, SQLite, printer, and Electron configuration concerns. | Technical review and acceptance criteria for any shadow study. | ACT-20261011-06 |
| CEO / finance-trust lead — role holder UNKNOWN | Money, stock mutation, tax, stored-data, and recovery concerns. | Governance review and acceptance criteria before live transaction or stock reliance. | ACT-20261011-05 |
| User / startup-founder | Proposed discovery-first direction. | Decide whether to approve the proposed sequence and assign owners. | Decisions Needed 1–2 |

## Evidence References

- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/package.json` — stack and build scripts; not runtime proof.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/feature.md` — described feature scope including offline/SQLite, UI modes, printer, tax, and recipe claims; not independent runtime proof.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/feature-payload.md` — marketing and feature copy; not customer validation.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/CHANGELOG.md` — developer-written release claims including desktop setup and 96 tests; execution/pass status unverified in this meeting.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/.claude/WORKFLOWS.md` — workflow rules for CEO and CTO review gates.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/electron/electron-builder.config.json` — placeholder Electron app ID; unfinished configuration evidence only.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/capacitor.config.ts` — consulted native platform configuration.
- `/Users/mnalwafi/Downloads/Coding/albyta-stock-manager/electron/package.json` — consulted desktop scaffolding.
- `/Users/mnalwafi/Downloads/Startup Idea/albyta-stock-manager` — leadership directory; no code, customer records, or metrics were present for this meeting.

## Deliberation Inputs

The following are source inputs from the two leadership positions and the facilitator reconciliation. They are preserved as discussion inputs, not independently verified facts or approvals.

### Founder Position — source input

- Recommended starting stranger discovery now rather than completing desktop speculatively.
- Proposed 10–15 problem interviews followed by 3–5 unpaid design partners, with the existing merchant record kept primary during a 7–14 day parallel test.
- Proposed an independent-café or small-UMKM beachhead, but acknowledged that segment, hardware, Android readiness, and numeric thresholds require validation.
- Recommended deferring the 40/60 reseller model until product-market fit and support economics are clearer.
- Confirmed that no CEO/CTO approval was verified and that the 96-test changelog statement was not executed in this meeting.

### Co-founder Position — source input

- Agreed that discovery and qualification can begin now, but opposed selling or deploying unfinished software as the primary POS.
- Critiqued unsupported assumptions about Android readiness, Yogyakarta device mix, test results, price changes, and reseller economics.
- Proposed direct field visits, honest disclosure, 3–5 unpaid design partners only after qualification, and parallel shadow testing with existing records retained.
- Proposed keeping desktop paused only provisionally, with platform priority decided from observed hardware rather than permanently killing desktop.
- Proposed deferring reseller/white-label distribution until product-market fit and support economics are demonstrated.

### Facilitator Reconciliation — source input

- The two positions agree on discovery now, no production replacement of merchant records, transparent unfinished-status disclosure, and deferring reseller distribution.
- The main nuance is desktop: temporary low priority pending field evidence is preferred over either speculative completion or permanent cancellation.
- The proposed sequence is Discovery → Design Partners → Gated Shadow Pilot → Platform and Monetization Review.
- Numeric thresholds and specific Android assumptions remain hypotheses. The reconciliation does not approve them.
- CEO/finance-trust review is required for money, stock, tax, and stored-data risk; CTO/technical review is required for native platform, persistence, sync, and hardware risk.

---

**End of meeting record.**
