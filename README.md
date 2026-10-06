# AI in Peer Review: the Good, the Bad and a Path Forward  -- Study Tracker

A continuously updated companion resource to **"AI for Peer Review: the Good, the Bad and a Path Forward"** (Islamaj, Comeau, Yeganova, Tian, Kim, Lemberger, Gashteovski & Lu).

This repository hosts a GitHub Pages site tracking empirical studies, pilots, and audits on AI use in scientific peer review. It extends Table 2 from the manuscript and is updated periodically by the authors as new relevant work is published, so the evidence base stays current beyond the publication date of the paper.

**Live page:** `https://NLM-DIR/github.io/AI-Peer-Review-tracker` 

**Maintenance:** This page is maintained solely by the authors of the accompanying manuscript. It is not open to public edits, pull requests, or external contributions. 

To suggest a study for inclusion, open an issue or pull request against this repository following the format in <code>studies-data.js</code>. This page is a research resource.

---

## Citation

If you use this resource, please cite the accompanying paper:

> Islamaj, R., Comeau, D.C., Yeganova, L., Tian, S., Kim, W., Lemberger, T., Gashteovski, K., & Lu, Z. *AI for Peer Review: the Good, the Bad and a Path Forward.* [Nature Computational Science, 2026]

---

## Repository structure

```
.
├── index.html    # The live tracker page (self-contained: HTML + CSS + JS)
└── README.md     # This file
```

`index.html` has no build step and no external dependencies beyond what's inlined in the file. It can be edited directly by an author and will update the live site as soon as it's pushed to the branch GitHub Pages is serving from.

---


## Table structure

Each entry looks like this:

```js
{
  date: "2026-05",              // YYYY-MM, used for default sort order
  author: "Kim et al.",         // First author + "et al." if more than one
  title: "On the limits and opportunities of AI reviewers",
  url: "https://arxiv.org/abs/2605.20668",  // Direct link to the paper (DOI preferred over publisher landing page where available)
  venue: "arXiv",                // Journal, conference, or preprint server
  design: "Expert annotation study + benchmark; 45 domain scientists; 469 hours; 2,960 review items from 82 Nature-family papers",
  models: "GPT-5.2; Claude Opus 4.5; Gemini 3.0 Pro",
  tiers: ["t2", "t3"],           // Which framework tier(s) the findings bear on: "t1", "t2", "t3"
  pos: [
    "GPT-5.2 exceeded top-rated human reviewer on composite quality rate",
    "Surfaced distinct issues missed by humans"
  ],
  neg: [
    "Lower factual correctness than top-rated human reviewers",
    "AI–AI overlap much higher than human–human overlap"
  ]
}
```

**Field notes:**
- `url` should link directly to the paper — a DOI link (`https://doi.org/...`) is preferred where one exists, since it's stable even if the publisher reorganizes its site. Fall back to an arXiv or preprint-server link if no DOI is available yet. This field is required for every entry; the title in the table links out to it.
- `tiers` accepts any combination of `"t1"`, `"t2"`, `"t3"`. Assign based on which part of the three-tier framework (Tier 1: automated verification, Tier 2: supervised assistance, Tier 3: human-led judgment) the study's findings are most relevant to. Many studies span more than one tier — include all that apply.
- `pos` and `neg` are plain arrays of short strings (roughly one line each). Keep them concise; this is a scanning table, not an abstract.
- `design` should include corpus size and study type in one line where possible, matching the style of existing entries.
- Dates use `YYYY-MM` format so the default chronological sort works correctly.

**Note:** DOIs are generally stable, but preprint versions (e.g. arXiv) can be superseded by a published version with a new DOI. When a preprint you've linked is later published in a journal, update the `url` field to the DOI and note the publication venue change in the `venue` field if it differs from the original preprint server.

---

## Scope

This tracker includes:
- Peer-reviewed studies, preprints, and conference pilots evaluating AI-assisted or AI-generated peer review
- Large-scale audits or corpus analyses of AI-modified review content
- Surveys of researcher attitudes toward AI in peer review, where they include original data

It does not include:
- Publisher policy pages (tracked separately in the manuscript's Table 1)
- General commentary or opinion pieces without original data or analysis
- Tools or platforms without an accompanying evaluation study

---

## License and disclaimer

This is a research resource maintained exclusively by the authors of the accompanying manuscript. It does not constitute legal or publisher policy guidance. Publisher AI-use policies change frequently — consult the relevant journal or conference directly for current requirements.

Content summarized here reflects the authors' reading of the cited studies at the time of entry. This page does not accept external corrections via issue or pull request; readers who notice an error are welcome to contact the corresponding author directly (see manuscript for contact information).

---

## Acknowledgement

This research was supported by the Intramural Research Program of the National Institutes of Health (NIH). The contributions of the NIH authors are considered Works of the United States Government. The findings and conclusions presented in this paper are those of the authors and do not necessarily reflect the views of the NIH or the U.S. Department of Health and Human Services.