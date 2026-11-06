# SEC 8-K Filing Patterns for FDA 510(k) Clearances

Investigation into how and when public medical-device companies disclose 510(k) clearances via Form 8-K. Relevant to measuring the true lag between FDA public availability and issuer disclosure.

## Key rules

- Form 8-K is generally due within **4 business days** of a reportable event (SEC Form 8-K instructions).
- FDA 510(k) clearance is **not** a mandatory 8-K trigger by itself. Companies typically disclose it under:
  - **Item 8.01** (Other Events) — voluntary disclosure of information the company deems important.
  - **Item 7.01** (Regulation FD) — when the disclosure is made to satisfy Reg FD (often furnished rather than filed).
- Many companies issue a press release and file the 8-K the same day (or within 1–2 business days), attaching the PR as Exhibit 99.1.
- There is no strict same-day requirement for a clearance; the 4-business-day clock applies only if the company treats the event as reportable under a specific item. In practice, material clearances are announced promptly because of Reg FD and investor expectations.

## Observed patterns from public examples

- Companies frequently announce the clearance via PR and file the 8-K on the **same day** or the next business day.
- Examples:
  - Nuwellis (NUWE): 8-K filed the same day as the announcement of a catheter clearance (Item 8.01).
  - Outset Medical: 8-K under Item 8.01 announcing Tablo platform clearance, with PR as exhibit.
  - Microbot Medical: 8-K under Items 7.01 and 8.01 on the day of the LIBERTY robot clearance announcement.
  - Older example (Insulet 2012): 8-K under Item 8.01 with PR exhibit for OmniPod clearance.
- Microcap and small-cap medtech often use Item 8.01 for positive regulatory news. Larger firms sometimes use the same structure.
- Not every clearance generates an 8-K. Routine or non-material clearances (minor accessories, process changes) may appear only in later 10-Q/10-K or not at all if the company does not consider them material.

## Implications for the timing thesis

1. **Issuer disclosure is usually fast once the company decides to announce.** The practical lag is more likely between FDA decision letter → company internal decision to announce → PR/8-K, rather than a multi-day delay after the company is ready to speak.
2. **8-K timestamps are reliable public markers.** EDGAR filing date + time is an objective, timestamped public disclosure. It is often the same day as the PR.
3. **FDA database lag remains the bigger unknown.** Because the searchable 510(k) database is updated weekly and full packages monthly, an 8-K/PR can easily precede the public FDA record by days. The reverse (FDA record before any 8-K) is also possible for non-material clearances or slow-to-announce firms, but appears less common for material events.
4. **Materiality filter is essential.** Only clearances the company itself treats as material (evidenced by a dedicated 8-K or PR) are realistic candidates for a price-moving event.

## Practical notes for data collection

- Search EDGAR full-text for terms such as “510(k) clearance”, “FDA clearance”, “substantial equivalence” limited to 8-K filings.
- Cross-reference K-numbers mentioned in the 8-K text against the FDA database decision date.
- Record: 8-K filing date/time, Item used (7.01 vs 8.01), whether a PR is attached, and any stated commercial impact.
- Compare that timestamp to the first recoverable public FDA database appearance.

## Preliminary conclusion

8-K filings provide a clean, timestamped issuer-disclosure signal for material 510(k) clearances. Most material announcements appear to occur the same day or within 1–2 business days of the company’s decision to publicize. The more uncertain lag is still between the FDA decision letter and the company’s announcement, and between the announcement and the FDA public database update. This supports using 8-K/PR timestamps as the primary “issuer news” marker in the first data-collection step.

Sources: SEC Form 8-K instructions; public 8-K examples (Nuwellis, Outset Medical, Microbot, Insulet); FDA 510(k) process page on weekly database updates.

Research only. Not investment advice.
