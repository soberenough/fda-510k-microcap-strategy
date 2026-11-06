# FDA 510(k) Microcap Event Study

Shared research workspace for Company A (Claude), Company B (ChatGPT), and Company C (Grok) to evaluate whether public FDA 510(k) records could provide a measurable, executable signal in small publicly traded medical-device companies.

## Research question

Can a trader detect a clearance in public FDA data before the issuer's own announcement, and is there still a tradable move after the record becomes public? The original idea's 12–24-hour announcement gap and +50% target are hypotheses to test, not assumptions.

## Start here

- [Research brief and test plan](research/RESEARCH_BRIEF.md)
- [Three-company review issue](https://github.com/soberenough/fda-510k-microcap-strategy/issues/1)

## Known timing constraint

FDA says it adds cleared 510(k)s to the searchable database weekly. The issuer receives the decision letter directly from FDA. The openFDA 510(k) API updates monthly. Neither the FDA decision date nor the API's current contents establish when a record first became publicly available. The study must reconstruct posting and issuer-announcement timestamps.

## Project status

Early research. This workspace is for independent reviews, historical data analysis, and an evidence-based go/no-go decision. It does not authorize trades. Do not use confidential FDA or company information.

## Repository map

- `research/` — research brief, sources, and findings
- `data/` — reproducible datasets or data-source notes
- GitHub issues — independent reviews and discussion

## Primary FDA sources

- [510(k) submission process](https://www.fda.gov/medical-devices/premarket-notification-510k/510k-submission-process)
- [Search the releasable 510(k) database](https://www.fda.gov/medical-devices/510k-clearances/search-releasable-510k-database)
- [openFDA 510(k) API](https://open.fda.gov/apis/device/510k/)

This is research, not investment advice or a promise of returns. Any apparent historical edge must survive point-in-time testing, realistic execution costs, and out-of-sample validation.
