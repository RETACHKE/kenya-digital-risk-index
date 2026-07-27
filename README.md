# Kenya Digital Risk Index

**The empirical backbone of RETACH's Cyber Risk Quantification (CRQ) Engine.**

Audit findings extracted from all 1,554 public Office of the Auditor-General (Kenya) reports, tagged to RETACH's S.I.N.S. Framework™ (Systems, Infrastructure, Network, Security) and aligned to ISO 27005 and NIST CSF.

Live site: **[retach.ke](https://retach.ke)**
Company: **[retach.tech](https://retach.tech)**

## Headline numbers

| Metric | Value |
|---|---|
| Published register rows | 4,675 |
| Entities covered | 562 |
| Source reports | 1,361 |
| Financial years | FY2015/16 – FY2023/24 (9 years) |
| Real findings | 4,406 (269 rows are clean/no-findings) |
| Scanned/unextractable files excluded | 178 (11.6% of corpus, excluded as noise, not zeros) |
| Content-matched recurrence rate | **25.6%** (1,126 of 4,406 real findings recur) |
| Self-reported prior-year reference rate | 19.8% |
| Recurring issue-threads identified | 458 (243 entities, 341 with an unbroken consecutive-year run) |

## S.I.N.S. pillar distribution (real findings, multi-label so >100%)

| Pillar | Share | Count |
|---|---|---|
| Other | 95.2% | 4,194 |
| Systems | 3.0% | 134 |
| Infrastructure | 1.3% | 59 |
| Security | 0.8% | 36 |
| Network | 0.5% | 22 |

Only 18 of the 458 recurring issue-threads tag to an actual S.I.N.S. pillar — that subset (disaster-recovery, IT-governance, e-procurement, and ICT-procurement findings recurring across two audit cycles) is explicitly labeled small-by-design / proof-of-concept, not a validated prevalence rate.

## What's in this repo

- `kenya-digital-risk-index.html` — the standalone public site (also live at retach.ke / retach.tech)
- `Kenya_Digital_Risk_Index_Methodology.docx` — full methodology: extraction approach, patch history, ISO 27005 / NIST CSF alignment, and an actuarial honesty banner
- `register_public_v38_stats.json` — the aggregate statistics behind every number above and on the site

## What's *not* in this repo, and why

The row-level register (4,675 individually tagged findings), the recurrence-thread dataset, and the extraction/dedup/recurrence-threading pipeline scripts are **not published here**. That dataset represents the core empirical work behind RETACH's CRQ Engine, and we keep it available to partners, researchers, and clients on request rather than publishing it outright.

**Want the underlying dataset, a walkthrough of the methodology, or to discuss a partnership?** Get in touch via [retach.tech](https://retach.tech).

## Known limitations (disclosed, not hidden)

- **Network-pillar findings carry false-positive risk** — keyword echo on non-IT findings, ~1-in-3 in manual sample. Don't treat Network counts as validated without a manual pass.
- **178 scanned/image-only PDF reports (11.6% of the corpus) are excluded entirely**, not shown as empty rows. OCR recovery is a deferred phase-2 item.
- **17.6% of real findings have a filename-tagged FY that doesn't match the year stated in the report text** (vs. a 15.0% earlier baseline, unexplained drift).
- **Un-numbered findings are capped at 900 characters**; ~14% are cut mid-sentence in the stored excerpt (the underlying extracted text is correct — only the display excerpt is capped).
- **Recurrence-thread matching (Jaccard 0.5 on a 10-word title window) can over-match generic recurring category names** in edge cases. The 18-thread S.I.N.S. subset is a proof-of-concept sample, not a validated prevalence rate.
- Neither the 19.8% nor the 25.6% recurrence figure is a validated actuarial coefficient. Both need entity-level normalization, time-decay weighting, and held-out cross-validation before they can feed the CRQ Engine's EAL formula.

## Methodology in one line

Regex/keyword/heading-pattern extraction only — no ML/NLP anywhere in the pipeline, by design. Every parser change is a versioned, standalone patch, regression-tested against a hand-validated sample before running on the full corpus. Full detail in the methodology doc above.

## License

Site code is MIT-licensed (see `LICENSE`) — fork it, adapt it, build on it. If you do, we'd appreciate keeping the RETACH attribution in the footer.

## About RETACH

RETACH DIGITAL LTD is a Kenya-based digital governance and cybersecurity firm. Our thesis: quantify digital risk against a proprietary S.I.N.S. Framework™, aligned to ISO 27005 and NIST CSF, feeding an actuarial Cyber Risk Quantification Engine (`EAL = Σ(frequency × severity)`). This index is the frequency side of that formula, built from real, cited government audit evidence — not survey data.
