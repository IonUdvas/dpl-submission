# DPL 2026 · Team Evaluation dashboard

A static page (GitHub Pages) showing the IPL 2023–24 team evaluation on a context-adjusted runs scale
(RAE, DAR, Impact). **The page computes nothing.** Every number comes from `data/dashboard_data.json`,
which is written by the Kaggle notebook `DPL_KKR_01_data_metrics_selection.ipynb` (section 09).

## Layout

```
index.html                  the dashboard (single file, no dependencies)
data/dashboard_data.json    written by the Kaggle notebook
.nojekyll                   serve files as-is
```

## Updating after a notebook change

1. On Kaggle, open the notebook and run **Save Version → Save & Run All**.
2. In the version's **Output** tab, download `dashboard_data.json`.
3. Replace `data/dashboard_data.json` in this repository and push. Pages redeploys in about a minute.

The header shows the build time and platform, so a reader can tell which notebook run they are looking at.

## Hosting

Settings → Pages → Deploy from branch → `main`, folder `/ (root)`.

Opened straight from disk (`file://`), browsers block the data fetch; the page then offers a file picker
for `dashboard_data.json`. Alternatively run `python -m http.server` in this folder.

## Method

Bandyopadhyay, *Context-adjusted Player Evaluation for Twenty20 Cricket* (arXiv). The dashboard's
**M1 · How the metrics work** panel explains every metric with the fitted values.
