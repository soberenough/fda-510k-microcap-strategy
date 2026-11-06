# Smallest Concrete First Data-Collection Step

**Goal:** Determine whether the key timestamps can actually be recovered at all. If they cannot, most trading-edge hypotheses are untestable historically and we stop or shift to prospective collection only.

This is the minimal viable experiment before any return calculations, options analysis, or strategy design.

## Scope (deliberately tiny)

- **Time window:** Fixed 24-month period (e.g., calendar years 2023–2024). No cherry-picking.
- **Universe:** Every 510(k) clearance in that window that appears in the FDA searchable database (not a filtered subset of “interesting” ones).
- **No returns yet.** No price data, no options, no filtering by stock price until the timestamp recovery rate is known.

## Exact tasks

1. **Pull the full census**
   - Download or scrape all cleared 510(k) records whose decision date falls in the window.
   - Capture: K number, decision date, applicant name, device name, product code, decision type.

2. **Attempt timestamp recovery for every record**
   For each clearance, try to establish three dates with evidence:
   - FDA decision date (already in the record).
   - **First public availability** of the FDA database entry (web archive, historical download snapshots, Wayback, third-party archives, or documented weekly update windows). Record source and confidence (high/medium/low/unrecoverable).
   - **Earliest issuer public disclosure** (company PR, 8-K, press wire, IR page). Search EDGAR, company sites, and news archives. Note if none found.

3. **Applicant → public company mapping (light)**
   - For each applicant, check whether it is (or was) a public company or a known subsidiary of one. Flag as: public / private / unclear. Do not require perfect ticker matching yet.

4. **Publish the recovery rates**
   - % of records where first-public-FDA timestamp is recoverable at medium+ confidence.
   - % where an issuer disclosure timestamp is found.
   - Distribution of lag (FDA public − decision; issuer PR − FDA public).
   - How many public or likely-public applicants exist in the set.

## Success / stop criteria for this step

- **Continue** if first-public-FDA timestamps can be recovered for a meaningful fraction (e.g., ≥30–40%) of records and issuer PRs can be found for most of the public ones. Then we have a basis to add prices.
- **Stop or switch to prospective-only** if historical first-availability timestamps are mostly unrecoverable. In that case, the pure historical “database before PR” edge cannot be tested and any future work must rely on real-time archiving going forward.

## Output of this step

A simple table or CSV (even a Google Sheet or markdown table) with one row per clearance and the columns above, plus a short summary of recovery rates. No trading signals, no performance numbers.

## Why this is the smallest useful step

Everything else (options liquidity, peer effects, pre-clearance windows, +50% targets, slippage) depends on knowing whether the public timestamps exist and can be aligned. This step answers that with a fixed, non-cherry-picked sample and zero capital risk.

Next (only if this succeeds): add split-adjusted prices and a basic event-study on the recoverable subset.

---
Research only. Not investment advice.
