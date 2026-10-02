# Kenya Digital Risk Index

**The empirical backbone of RETACH's Cyber Risk Quantification (CRQ) Engine.**

Audit findings extracted from 1,774 public Office of the Auditor-General (Kenya) reports, tagged to RETACH's S.I.N.S. Framework™ (Systems, Infrastructure, Network, Security) and aligned to ISO 27005 and NIST CSF.

Live site: **[kdri.retach.ke](https://kdri.retach.ke)**
Company: **[retach.tech](https://retach.tech)**

## Headline numbers

> **Correction (3 October 2026).** Version 4.0 replaces version 3.8. Earlier versions read only the first six pages of 722 longer native-text reports, and did not recover text from every page of every scanned report. Findings after page six, or on unread scanned pages, were missed. Version 4.0 reads every page of all 1,774 reports. The register grew from 4,675 to 8,205 rows, and digital-tagged findings from 212 to 484. Entities with three or more tagged findings rose from 21 to 69; after checking against the source reports, 48 have three or more confirmed findings, up from 21. No entity's confirmed findings went down. Counts and charts across the site have been restated.

| Metric | Value |
|---|---|
| Published register rows | 8,205 |
| Entities covered | 570 |
| Source reports | 1,774 |
| Financial years | FY2015/16 – FY2024/25 (10 years) |
| Real findings | 7,972 (233 rows are clean/no-findings) |
| Unreadable files excluded | 1 (0.1% of corpus; scanned reports are now read with OCR) |
| Content-matched recurrence rate | **29.7%** (2,366 of 7,973 real findings analysed recur) |
| Self-reported prior-year reference rate | 14.9% |
| Recurring issue-threads identified | 908 (240 entities, 681 with an unbroken consecutive-year run) |

## S.I.N.S. pillar distribution (real findings, multi-label so >100%)

| Pillar | Share | Count |
|---|---|---|
| Other | 93.9% | 7,488 |
| Systems | 3.7% | 294 |
| Infrastructure | 2.0% | 160 |
| Security | 1.1% | 87 |
| Network | 0.8% | 60 |

**484 unique findings (6.1% of 7,972) carry at least one digital-pillar tag.** The four digital pillar counts sum to 601 because 91 findings are tagged to more than one pillar. Tags come from keyword matching. In a hand check of 296 tagged findings, 205 (69.3%) were confirmed against the source report.

Only 46 of the 908 recurring issue-threads tag to an actual S.I.N.S. pillar — that subset (disaster-recovery, IT-governance, e-procurement, and ICT-procurement findings recurring across audit cycles) is explicitly labeled small-by-design / proof-of-concept, not a validated prevalence rate.

## What's in this repo

- `index.html` — the standalone public site (live at kdri.retach.ke)
- `methodology.html` — full methodology & citation page: extraction approach, patch history, ISO 27005 / NIST CSF alignment, recurrence method, entity tiers, and how to cite this dataset
- `register_public_v38_stats.json` — (filename kept for stable links; content is version 4.0) the aggregate statistics behind every number above and on the site
- `entities.html`, `entities_aggregate.json` and `entities/` — entity search, per-entity coverage data, and the 48 Tier A profile pages
- `kenya-digital-risk-index.html` — legacy redirect stub to `/` (kept for old inbound links)

## What's *not* in this repo, and why

The row-level register (8,205 register rows), the recurrence-thread dataset, and the extraction/dedup/recurrence-threading pipeline scripts are **not published here**. That dataset represents the core empirical work behind RETACH's CRQ Engine, and we keep it available to partners, researchers, and clients on request rather than publishing it outright.

**Want the underlying dataset, a walkthrough of the methodology, or to discuss a partnership?** Get in touch via [retach.tech](https://retach.tech).

## Known limitations (disclosed, not hidden)

- **Network-pillar findings carry false-positive risk** — keyword echo on non-IT findings, ~1-in-3 in manual sample. Don't treat Network counts as validated without a manual pass.
- **Scanned reports were read with OCR**, which can misread characters; the OCR error rate has not been measured. Published Tier A profiles cite findings checked by hand against the source report.
- **Keyword tagging precision is 69.3%** (205 of 296 hand-checked tagged findings confirmed). Tier A counts confirmed findings only.
- **FY2020/21 has fewer published reports**, so trends across that year are not like-for-like. The year-mismatch and truncation rates published for earlier versions were not re-measured for this version.
- **Recurrence-thread matching (Jaccard 0.5 on a 10-word title window) can over-match generic recurring category names** in edge cases. The 46-thread S.I.N.S. subset is a proof-of-concept sample, not a validated prevalence rate.
- Neither the 14.9% nor the 29.7% recurrence figure is a validated actuarial coefficient. Both need entity-level normalization, time-decay weighting, and held-out cross-validation before they can feed the CRQ Engine's EAL formula.

## Methodology in one line

Text is extracted directly from native-text PDFs; scanned reports are read with optical character recognition (OCR). Findings are split with heading patterns and classified into S.I.N.S. pillars with fixed keyword rules; no machine-learning classifier is used to tag or count findings. Every parser change is a versioned, standalone patch, regression-tested against a hand-validated sample before running on the full corpus. Full detail in the methodology doc above.

## License

Site code is MIT-licensed (see `LICENSE`) — fork it, adapt it, build on it. If you do, we'd appreciate keeping the RETACH attribution in the footer.

## About RETACH

RETACH DIGITAL LTD is a Kenya-based digital governance and cybersecurity firm. Our thesis: quantify digital risk against a proprietary S.I.N.S. Framework™, aligned to ISO 27005 and NIST CSF, feeding an actuarial Cyber Risk Quantification Engine (`EAL = Σ(frequency × severity)`). This index is the frequency side of that formula, built from real, cited government audit evidence — not survey data.
