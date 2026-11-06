# Research brief: can FDA 510(k) records create a tradable microcap signal?

## Origin of the idea

The owner proposed monitoring the FDA's public 510(k) database for clearances involving publicly traded medical-device companies below $5/share, buying before the company's press release (on the theory small firms may announce 12–24 hours later), and selling around a 50% gain.

The hypothesis is open. Do not treat either the 12–24-hour delay or 50% return as established fact.

## What we know from primary sources

1. FDA sends the decision letter to the submitter when it makes the decision. FDA says it adds cleared records to the public 510(k) database weekly; attachments to the clearance letter may be posted monthly. Source: https://www.fda.gov/medical-devices/premarket-notification-510k/510k-submission-process (Decision Letter section).
2. FDA's searchable record exposes decision date, applicant, device name, and clearance details. Source: https://www.fda.gov/medical-devices/510k-clearances/search-releasable-510k-database
3. The openFDA 510(k) API reports monthly update frequency, so it is not a real-time alert source. Source: https://open.fda.gov/apis/device/510k/
4. A 510(k) generally supports substantial equivalence to a legally marketed predicate. It is not the same as PMA approval or drug approval. Source: https://open.fda.gov/apis/device/510k/
5. FDA records identify the applicant, which may not map cleanly to the listed parent company or ticker.

These facts imply the FDA database could lag the actual decision and could sometimes precede a company's own press release, but we need point-in-time evidence for when the entry first became public and when the issuer announced it.

## Competing explanations

- **Possible edge:** Some issuers may not promptly publicize a clearance, and some clearances may be material to a small firm's revenue prospects. Automated monitoring might catch a public FDA entry while the market has not fully reacted.
- **Why it may fail:** Weekly database publication can make the record stale; companies may disclose first; other traders can scan the same public data; clearance may have little commercial impact; market may have anticipated the event; microcap price prints may not be executable at displayed prices.
- **Separate pre-clearance thesis:** Predicting a pending clearance before the decision is a distinct, much riskier strategy. A public decision date in hindsight does not reveal the outcome beforehand. Do not mix this with the post-publication database-signal test.
- **Legal boundary:** Keep all entries based on timestamped public information. Do not seek or use confidential FDA or issuer information. SEC overview: https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/insider-trading-arrangements-and-related-disclosures

## Required empirical test

Build an event-level dataset starting from FDA records, not from stocks remembered for large jumps. For each event record:

- K number, applicant, device, decision date, decision, predicate/indication context, and record availability timestamp if recoverable;
- issuer-parent mapping with evidence, ticker as it existed then, and listing venue;
- first issuer PR, SEC filing, and other broad-publication timestamp;
- intraday prices/volume and bid/ask if available; halts; splits; financing/dilution; delisting/acquisition;
- whether the issuer was below $5 at the time (explicitly define whether prior close, entry price, or both).

Measure a strategy only from the first executable trade after public FDA record availability. Compare to the first issuer announcement and the next market open. Predefine exit rules: for example +50% take-profit, a hard loss limit, and a maximum holding period. Report what happens if the target is never hit. Use realistic spread/slippage and no-fill assumptions.

Include all eligible events, including clearances with flat/negative reactions and companies that later disappeared. Separate categories such as first product, new indication, manufacturing/process change, and routine accessory. Evaluate whether public-posting-to-PR lag is actually 12–24 hours and how often the record appears after the issuer has already announced.

## Metrics and safeguards

Report sample size, coverage, mapping confidence, PR lead/lag distribution, median and mean net return, win rate, +50% target-hit rate, downside tail, max drawdown, time in trade, liquidity constraints, and results by market cap, price, volume, and clearance type. Use split-adjusted data; include delisted tickers; avoid selecting events based on realized return. Keep a holdout period or out-of-sample validation to limit rule fitting.

A few huge winners do not establish a repeatable edge. Be explicit about data gaps, especially historical FDA posting timestamps and microcap intraday quotes.

## Decision requested

Each of Companies A (Claude), B (ChatGPT), and C (Grok) should independently comment on:

1. Is the signal feasible with public data, given the weekly/monthly update cadence?
2. What exact dataset and historical period are needed to answer it?
3. Which candidate data sources provide point-in-time posting/PR/SEC timestamps and executable microcap prices?
4. What biases or execution problems could falsely create an apparent edge?
5. What would count as a convincing go/no-go result?
6. Should we proceed to build the dataset/backtest, and what is the smallest credible first phase?

Then compare the three reviews and resolve disagreements with evidence. No trades are proposed by this brief.

## Initial assessment (provisional)

This is worth a bounded historical study because the core thesis can be falsified without risking capital. The FDA database is not instant, so any edge would need to exist after the database entry is publicly observable and before/after issuer PR. A +50% target is a test parameter, not a reasonable base-case assumption. Proceed only if the historical data support a tradable, out-of-sample result after costs.
