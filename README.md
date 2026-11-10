# Dark Patterns in Bangladeshi E-Commerce

Research artifacts for **Prevalence and User Perception of Dark Patterns: A Case Study on E-Commerce Websites of Bangladesh**. The repository brings together a labeled text dataset, website-discovery data, browser-automation scripts, text segmentation, model-assisted classification, and the thesis report.

## Dataset

[dp-dataset-bangladesh.csv](dp-dataset-bangladesh.csv) contains **99 dark-pattern text instances** collected from **131 Bangladeshi e-commerce websites**, as described in the accompanying study. Records use `text` and `label` fields, with five categories:

- Misdirection
- Urgency
- Scarcity
- Social Proof
- Forced Action

[The thesis report](Yasin_Sazid_MSSE_Thesis_Report.pdf) provides the study's methodology, research questions, and interpretation.

## Collection and classification pipeline

```text
E-commerce directory → Website URLs → Captured HTML → Segmented text → Classification
```

| Artifact | Purpose |
| --- | --- |
| `ecab-scrapper.js` | Discover and export directory information using Puppeteer |
| `ecab-member-data.csv`, `webpage-urls.csv` | Supplied discovery and URL artifacts |
| `html-scrapper.js` | Capture website HTML with browser automation and the stealth plugin |
| `segmentation-algo.js` | Process HTML into text segments using a browser-backed workflow |
| `gpt-classification.js` | Classify prepared records through the OpenAI client |
| `prompt.txt` | Classification prompt artifact |

## Explore and reproduce

Begin with the CSV dataset and report to inspect the research outputs directly. To study the collection code, use Node.js with the packages imported by the selected script: Puppeteer, Puppeteer Extra, its stealth plugin, SheetJS (`xlsx`), and the OpenAI client.

The scripts specify their own spreadsheet inputs and output locations, including `ecommerce.xlsx` and `gpt_remaining_dataset.xlsx`. Provision those stage-specific inputs and the appropriate service authentication before running a selected stage. The classifier records `gpt-3.5-turbo-0125` as its model selection.

## Technical contribution

The project connects regional e-commerce research to a computational workflow for website discovery, HTML capture, segmentation, and model-assisted categorization, with labeled data and a full research narrative presented together.
