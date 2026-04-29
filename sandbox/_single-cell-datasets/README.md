# Single-cell PRIDE autoresearch drafts

Generated with the sdrf:autoresearch workflow for target `all PRIDE single-cell datasets`, using PRIDE Archive project/file APIs, Europe PMC accession searches, and the `ms-proteomics` + `single-cell` SDRF templates.

This folder contains the campaign manifest. Accession-specific draft SDRFs are staged under `sandbox/{ACCESSION}/{ACCESSION}.sdrf.tsv` unless an annotation already existed in `datasets/`. These sandbox drafts are evidence-backed scaffolds, not finished curator-reviewed submissions. In particular, TMT/channel-level single-cell mappings often require publication supplements or deposited sample maps before promotion to `datasets/`.

Summary:

- Confirmed candidate accessions: 109
- Existing dataset updated directly: 1
- New sandbox draft SDRFs: 108
- Templates applied to drafts: `NT=ms-proteomics;VV=v1.1.0` and `NT=single-cell;VV=v1.0.0`
- Round 2 enrichment applied to all 108 sandbox drafts using PRIDE project metadata, complete PRIDE file lists, and Europe PMC accession evidence.
- Round 2 added richer method fields where evidence supported them: acquisition mode, dissociation method, collision energy, precursor/fragment tolerances, digestion enzymes, modification parameters, sample-preparation batch, FACS/LCM/microfluidics/nanoPOTS metadata, and inferred cell-line hints.

Validation notes:

- `datasets/PXD043473/PXD043473.sdrf.tsv` passes `parse_sdrf validate-sdrf --template single-cell --skip-ontology`.
- `sandbox/PXD016921/PXD016921.sdrf.tsv` passes the same structural/template check as a representative label-free draft.
- `sandbox/PXD020586/PXD020586.sdrf.tsv` fails on `comment[label]` because TMT channel labels require supplement-backed channel mapping; similar multiplexed drafts should remain in `sandbox/` until curated.
- Full round 2 validation: 87 of 108 enriched sandbox drafts pass structural/template validation with `--skip-ontology`; the 21 failures all fail because exact TMT/TMTpro channel-to-sample labels are unresolved and were not guessed.

See `manifest.tsv` for PRIDE URLs, Europe PMC hits, publication identifiers, evidence terms, file counts, and draft paths. See `autoresearch-round2.tsv` for per-accession enrichment status, unresolved high-value gaps, and validation status.
