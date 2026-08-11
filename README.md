# Holiday Inn Revival — Project Hub

Performance diagnosis and 90-day recovery plan for the **Holiday Inn & Suites Savannah
Airport – Pooler** (100 Outlet Pkwy, Pooler GA 31322 · 104 rooms · built 2019).

Built by **Shyam Patel**. All data here is private and confidential to the hotel.

---

## The two files

| File | What it is | Open it when |
|---|---|---|
| **`presentation.html`** | 11-slide owner deck | You are presenting |
| **`index.html`** | 9-tab working dashboard | You need the number behind a slide |

Both are **fully self-contained**. No internet, no build step, no dependencies — open
either one by double-clicking it. That is deliberate: a presentation should never depend on
conference-room wifi.

### Presenting

| Key | Does |
|---|---|
| `→` / `space` / click | Next slide |
| `←` / click far left | Previous slide |
| `1`–`9`, `0` | Jump straight to a slide |
| `O` | Overview — all 11 slides at once, click one to jump. **This is the Q&A view.** |
| `Esc` | Leave overview |
| `F` | Fullscreen |
| `P` | Print → saves a clean 11-page PDF |

The deck runs about 10–12 minutes. If someone asks a detail question, switch to the
dashboard's **Diagnosis** or **Accounts** tab rather than digging through slides.

### Dashboard tabs

| Tab | Contents |
|---|---|
| **Home** | Phase, what to do now, headline stats, the one-sentence diagnosis, key facts |
| **Diagnosis** | 18-month occupancy chart, the three STR indices, three ways to value the gap, guest-score root cause, ranking history |
| **The Plan** | The 7 initiatives, the 90-day roadmap, and what the plan deliberately does *not* do |
| **Intel** | Competitor walkthroughs, strategic insights, last rating-monitor reading |
| **Outreach** | Demand generators, the Chamber membership gap, 5 corporate targets with drafted emails |
| **Accounts** | The verified corporate account book — start here for anything account-related |
| **Files** | Every project file and its status |
| **Tasks** | Live task list, click any row to toggle |
| **How to Use** | Workflow and the data-integrity rules |

Tabs support arrow-key navigation once a tab has focus. Both files respect light and dark
mode, print cleanly, and work on a phone.

---

## The argument, in short

**This is an occupancy problem, not a pricing problem.**

- ADR **$148.63** — *above* the comp set (rate index 102)
- Occupancy **71.82%** vs comp set **80.46%** (occupancy index 89)
- RevPAR **$106.75** vs **$117.35** — revenue index 91, down **16.5% year over year**
- Gap of **$10.60 per available room-night**

Guests will pay our price; fewer of them are choosing us. **Do not cut rates** — that
surrenders the one measure we win on. The fix is service, cleanliness, and reviews.

Modeled recoverable upside: **$195K–$362K/year** (Cornell elasticity, +1.42% RevPAR per
point of guest satisfaction). Present that figure, not the ~$402K full-fair-share ceiling.

Two measured root causes: **Problem Handling 40.74** (the lowest score in the file) and
**Shower/Bath 65.98**.

The corporate account book confirms the same collapse independently: like-for-like
January–May, **2026 is down 33.5% in room nights and 36.5% in revenue against 2025**.

---

## Data integrity rules

These are not optional — the project's credibility rests on them.

- **Hard data:** Heartbeat, FPS, Medallia, STR STAR, and the production report extraction.
  Cited as fact.
- **Labeled assumptions:** all cost estimates. Never presented as quotes.
- **Never used:** Clearwater (CLWHS) screenshots — that is a different property.
- **Never shared externally:** any internal performance data in these files.
- **Authority:** Shyam is an intern. Outreach opens relationships; it never commits the
  hotel to a rate or a billing arrangement. The sales team sends.
- **Two different ADRs.** Corporate-account ADR from the production report
  ($124.84–$136.42) is not whole-property STR ADR ($148.63). Never quote them as one number.
- **Read `memory/data-corrections.md` before quoting any account figure.** Several
  previously circulated numbers are wrong and are listed there for retirement.

## Known caveats

- The **$26K/month** and **$402K/yr** figures in older notes do not reconcile — they rest on
  different bases. The Diagnosis tab shows all three valuation methods with their
  assumptions. Say one number and cite its method.
- Company names in the account book are **OCR-read**. The top 50 were verified against the
  scans; **3 are flagged `CHECK SPELLING`**. Verify a name before it goes in a deliverable.
- Merging duplicate account profiles is a **documented judgement**, not a fact from the
  report. The unmerged view is preserved.
- `active` / `lapsed` / `declining` are **our definitions**, not the report's.
- The rating-monitor reading on the Intel tab is dated. Re-run it before quoting.

---

## Repository layout

```
index.html            The dashboard
presentation.html     The owner deck
memory/               Project memory — read MEMORY.md first
  data-corrections.md READ BEFORE QUOTING ANY ACCOUNT NUMBER
  financial-diagnosis.md
  seven-initiatives.md
  ...
```

Larger source artifacts (the Strategic Blueprint, financial model, RACI matrix, account
workbook, and extraction scripts) live outside this repository in
`~/Desktop/Holiday Inn/`. The Files tab lists them all.

## Updating

Paste new information into the chat and say what it is — raw notes, a fresh STR PDF, a new
monitor run. The dashboard, the deck, and the memory files get updated together. The charts
are drawn from data arrays at the bottom of each file, so refreshing a chart means replacing
the numbers, not redrawing anything.
