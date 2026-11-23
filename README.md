[README (5).md](https://github.com/user-attachments/files/35303072/README.5.md)
# Cement Yield Calculator

v2026.11.23 · S. Siddhu | SOGE | Central

`Cement_Yield_Calculator.html` is a single-page tool for cement slurry design, primary cement top of cement (TOC), and cement/plugging memos. It runs in the browser. Nothing you enter is uploaded.

## Tabs

- **Slurry design.** Density, yield and mix water by the absolute volume method (SLB *Well Cementing*, App. C, Eq. C-1).
  - Guided start, a component table with BWOC / BWOW / BWOB / lb/sk / gal/sk bases, Suggest water, and Solve to a target density.
  - Show the math, help (?) buttons and range warnings.
  - Job volume and water sensitivity.
  - Recipes and a 132-material library, tagged by source (SLB App. C, Red Book, additive database, or user-entered).
- **Primary cement TOC.** Casing strings, slurries and returns give the calculated TOC for each string, drawn on a wellbore diagram to scale.
- **Cement memo.**
  - API lookup fills the header.
  - Casing, mudding, squeeze and plug tables; the plug table shows % of required.
  - A wellbore diagram and Copy memo text.
  - **Permit check:** drop the *Permit to Conduct Well Operations* PDF on the Permit panel to compare its requirements with the memo (✓ / ✕ per item). Text PDFs only; scanned PDFs must be entered by hand.

## Use

Open the GitHub Pages link, or open the file in Chrome or Edge. Recipes, My materials, and the TOC and memo drafts are saved in that browser only.

An internet connection is needed the first time a permit PDF is read, to load pdf.js from cdnjs.

## Well list (API lookup)

The memo tab reads the same well list as Plug Volume Review:

```
data/manifest.json          {"file":"wells_20261022.tsv.gz","asOf":"2026-10-22"}
data/wells_20261022.tsv.gz  CalGEM AllWells export, 20 columns, gzip
```

The calculator must sit in the repository root next to `data/`. The first lookup downloads about 5 MB; the browser keeps it after that.

**To update:** upload a new `.gz`, change `file` and `asOf` in `manifest.json`, and delete the old `.gz`.

If the file is opened locally (not hosted), click **Load AllWells CSV** once in the memo tab. It accepts the full CSV or the `.gz`.

## Sources

- SLB *Well Cementing*, 2nd ed.: Ch. 2–3, Ch. 10, App. C (Tables C-1, C-4).
- Halliburton Cementing Tables (Red Book), Section 240.
- Additive database: vendor and third-party material SG values compiled in a slurry-design workbook.
- CalGEM AllWells export.

Results are calculations, not lab results. Thickening time, fluid loss and strength come from lab testing.
