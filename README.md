# Gender-Korpus — Overview

- Corpus analysis of gender assignments in German texts (18th–20th c.) from https://msternchenw.de/. 
- Scans all `*.tsv` with tokens labeled `Mann`, `Frau`, `Genderneutral`, `O`.
- Adds POS tagging for labeled tokens using spaCy (`de_core_news_md`, fallback `de_core_news_sm`).
- Start Dashboard with:
  ```powershell
  Start-Process ".\dashboard.html"
  ```

## Requirements

- Python 3.12; `pandas`, `numpy`, `matplotlib`, `spacy`
- spaCy model: `de_core_news_md` (auto-fallback to `de_core_news_sm`)

## Key totals (last run)

- Tokens total: 684,105
- Labeled total (M/F/N): 29,199
- `Mann`: 17,716 (60.67%)
- `Frau`: 10,200 (34.93%)
- `Genderneutral`: 1,283 (4.39%)
- Other `O`: 654,906

## Results

### Gender distribution across the corpus

<p align="center">
  <img src="gender_counts_bar.png" alt="Gender label counts across the corpus" width="60%">
</p>

Of 29,199 labelled tokens, 60.7% are `Mann`, 34.9% `Frau` and 4.4% `Genderneutral`.

### Variation between texts

<p align="center">
  <img src="gender_diverging_bars_per_text.png" alt="Diverging bars of Mann vs. Frau labels per text" width="85%">
</p>

Share of `Mann` vs. `Frau` labels per text, showing which texts deviate from the corpus-wide pattern.

### Part-of-speech patterns by gender label

<p align="center">
  <img src="pos_heatmap.png" alt="Heatmap of POS tags by gender label" width="75%">
</p>

POS tags (spaCy, `de_core_news_md`) for each gender label, showing how male, female and neutral references differ grammatically.
## Outputs (generated files)

- `gender_counts_summary.csv`
- `gender_counts_bar.png`, `gender_counts_donut.png`
- `gender_counts_normalized_per_text.png`, `gender_ratio_per_text.png`
- `gender_diverging_bars_per_text.png`
- `pos_tagged_tokens.csv`, `pos_counts.csv`
- `pos_heatmap.png`
- `pos_distribution_stacked100.png`, `pos_distribution_grouped_top10.png`
