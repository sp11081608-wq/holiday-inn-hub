# Data Corrections — Production Report Extraction
*(saved August 11, 2026 — supersedes all earlier corporate-account figures)*

The hotel's **569-page "Profile Production Statistics" report** (run 06-03-26, covering
01-01-23 → 06-01-26) has been extracted into structured data. Source was 12 scanned,
image-only PDFs with zero extractable text, so this was OCR: each page rendered at 300 dpi,
OCR'd to word level with pixel coordinates, the table rebuilt **by x-position** against each
block's month header rather than by reading order, and every figure checked against
arithmetic the report itself guarantees. Failing blocks were auto re-read at 600 dpi.

## Verification — treat the arithmetic as reliable

- Sum of all accounts = **$3,975,646.09** = the report's own printed Grand Total, **difference $0.00**.
  The Grand Total was never fed into the extraction, so this is an independent check.
- Matches on **all 42 individual months**, for revenue and room nights.
- **0 of 35,770 rows** fail `nights × ADR = revenue`.
- Room nights by year reproduce the July anchors: **10,958 / 8,276 / 8,223 / 2,988**.
- 569/569 pages; 852 profiles × exactly 4 year-blocks = 3,412. Seven random blocks (84 cells)
  and the top 50 company names verified against the scans by eye.

Caveats below are about **names and definitions**, never about the figures.

## Headline data

- **831 real companies** (852 raw profiles — 20 customers filed under more than one)
- **467 active · 309 lapsed · 76 never produced**
- **$3,975,646.09** and **30,445 room nights**, 2023 → 2026 YTD

| Year | Room nights | Revenue | ADR |
|---|---|---|---|
| 2023 | 10,958 | $1,438,621.61 | $131.29 |
| 2024 | 8,276 | $1,124,793.90 | $135.91 |
| 2025 | 8,223 | $1,026,558.29 | $124.84 |
| 2026 YTD | 2,988 | $385,672.29 | — |

## Three findings that matter

**1. 2026 is Jan–May plus one day. Never compare it to a full year.**
The report ends 06-01-26; June shows 19 room nights, which is a single day. Like-for-like:

| Jan–May | Room nights | Revenue | ADR |
|---|---|---|---|
| 2023 | 4,562 | $616,361 | $135.11 |
| 2024 | 3,510 | $478,844 | $136.42 |
| 2025 | 4,464 | $602,357 | $134.94 |
| **2026** | **2,969** | **$382,775** | **$128.92** |

The decline is **recent and steep, not a slow four-year slide**. Corporate business recovered
in early 2025 to near-2023 levels, then fell away from mid-2025. Jan–May 2026 is **−33.5%
nights and −36.5% revenue vs 2025** — the worst stretch in the dataset. Full-year corporate
ADR also fell $135.91 (2024) → $124.84 (2025): rate down *and* volume down, which supports
the existing "discounting was tested and failed" thesis.

**2. The win-back framing targets the smaller half of the problem.**

| Cohort | Count | Revenue effect vs 2023–24 |
|---|---|---|
| **Declining** (still booking, down >15%) | 121 | **−$950,480** |
| Lapsed (gone entirely) | 307 | −$881,532 |
| Growing | 76 | +$442,407 |
| New since 2025 | 244 | +$239,779 (~$983 each) |

More is lost from accounts the hotel **still has** than from ones that left. Saving a current
account is cheaper than resurrecting a dead one — work the declining list first.

**3. Duplicate profiles were splitting customers' revenue.**
20 customers on file under 2+ profiles — typically a proper corporate profile (Corporate ID +
address) plus a **bare-name profile with no ID and no address**, the signature of a front-desk
manual entry instead of selecting the existing account. Totals unaffected; **rankings are not**:

| Company | Was | Now (merged) |
|---|---|---|
| Howard Sheppard | #41 · $20,911 | **#22 · $41,636** |
| Anderson And Son | #35 · $22,393 | **#28 · $32,414** |
| Franklin Management | #42 · $20,840 | **#31 · $29,849** |
| Lift Power (3 profiles) | #63 · $11,363 | **#49 · $17,462** |
| Concrete Supply | #22 · $40,050 | **#20 · $43,990** |
| Texas Roadhouse | #20 · $42,623 | **#19 · $44,258** |

This is a real PMS data-hygiene problem worth raising with **GM Mathew Gaines** — every
account report the hotel runs is splitting these customers.

## Numbers previously circulated that are WRONG — retire them

- ~~929 accounts~~ → **852 profiles / 831 companies**
- ~~"~456 active / ~283 lapsed"~~ → **467 / 309 / 76 never produced**
- ~~"35 active · 16 lapsed · ~$7,800 recoverable"~~ → placeholder figures from an early
  dashboard draft; replaced entirely by the account book
- ~~Benore Logistics ~$351K~~ → **$340,844** (merged; $340,328 unmerged). Still #1.
- ~~"Top 3 win-backs: NFI, Georgia Storefronts, Barnett Southern ≈ $178K/yr"~~ →
  **NFI Industries is NOT lapsed.** Still active but collapsed 91% ($127,045 in 2023–24 →
  $11,229 in 2025–26). Pitch as a **save**, not a win-back.
  Real top lapsed: **Georgia Storefronts $120,971 · Barnett Southern $109,311 ·
  Smyrna Ready Mix $76,960.**
- Gap Inc **confirmed correct**: $341.98 total, rank 505 of 852 — so it is *not* a top account
  to protect, as an earlier dashboard draft claimed.
- Concentration: top 10 = 38.1% of revenue · top 25 = 56.4% · top 50 = 71.0% · top 100 = 82.8%

## Never claim these — not in the report

- **Rooms booked** — it records *room-nights* (rooms × nights as one figure); cannot be split
- **Length of stay** — not captured anywhere
- **Individual dates** — monthly is the finest grain
- Guest names, rate plans, booking channel, cancellations

## Remaining caveats

- **Company names are OCR-read.** Top 50 verified against the scans; 799 double-read at
  300 + 600 dpi; **3 flagged `CHECK SPELLING`** in the workbook. Numbers unaffected (accounts
  group by Corporate ID, not name), but verify a name before putting it in a deliverable or in
  front of the GM.
- **Merging duplicate profiles is a documented judgement, not a fact from the report.** Basis
  recorded per row in the workbook's "Merged on" column; the unmerged view is kept intact. Two
  similar pairs deliberately NOT merged: Al Farm Bureau vs Ga Farm Bureau (Alabama vs Georgia),
  and AMN Healthcare Services vs Healthcare Services.
- **active / lapsed / declining / revenue_at_risk are our definitions**, not the report's.
  active = booked in 2025 or 2026 YTD; lapsed = produced 2023–24 and nothing since;
  growing/declining = ±15% band on 2025–26 vs 2023–24.
- **Keep the two ADRs apart.** Corporate-account ADR here ($124.84–$136.42) is not the same
  measure as whole-property STR ADR ($148.63). Never quote them as one number.

## Files (in `~/Desktop/Holiday Inn/outputs/`)

| File | What it is |
|---|---|
| `Corporate_Account_Book_2026-07-30.xlsx` | **Main deliverable.** 9 sheets; start at "Companies (merged)" |
| `company_book_MERGED_2026-08-11.csv` | 831 companies, duplicates combined |
| `company_book_2026-07-30.csv` | 852 raw profiles, unmerged |
| `production_monthly_2026-07-30.csv` | 35,770 rows — company × year × month (raw grain) |
| `duplicate_profiles_2026-07-30.csv` | The 20 split customers |
| `production_EXTRACTION-NOTES.md` | Method, accuracy, the bugs found |
| `report-extraction/` | Scripts, rerunnable on a future report |

## Method lesson worth carrying forward

The extraction looked clean and complete at **four** separate points while silently dropping
~75 accounts, flipping the sign on refunds, passing a cell with two compensating errors, and
undercounting duplicate profiles. Every one was caught by an **independent** check — the
report's own printed totals — never by the pipeline agreeing with itself.
**Internal consistency is not evidence of correctness.**

**Related:** [[project-holiday-inn]], [[financial-diagnosis]], [[key-contacts]]
