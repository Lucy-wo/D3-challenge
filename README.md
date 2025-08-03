# D3Times — Interactive Health vs. Demographics Scatter (D3 v5)

## Summary

An interactive, single-page visualization that plots U.S. state-level health/demographic metrics as a **responsive D3 scatter plot** with **tooltips** and **axis switching**. The page is scaffolded with **Bootstrap 4**, uses **D3 v5** and **d3-tip**, and renders into a `#scatter` container on `index.html`.  &#x20;

## Goal

Explore correlations between **health risks and age/income** to reveal patterns at the state level, and demonstrate a clean, modular setup for D3 projects.&#x20;

## Procedure

1. **Page scaffold** — Bootstrap grid with a `#scatter` mount point and article panel. &#x20;
2. **Libraries** — Load **D3 v5** and **d3-tip** from CDNs; app logic in `app.js`.&#x20;
3. **Styles** — Full-page layout & sticky footer in `style.css`; chart/tooltip styling in `d3Style.css` (e.g., `.stateCircle`, `.stateText`, `.d3-tip`).  &#x20;
4. **Data load** — Read `data.csv` in `app.js`, parse numeric fields, and build scales/axes. (Code lives in `app.js`.)
5. **Marks** — Draw circles with **state abbreviations** centered inside (`.stateCircle` + `.stateText`).&#x20;
6. **Interactivity** — Axis label toggles (`.active/.inactive`) to switch metrics; **d3-tip** tooltips on hover. &#x20;

## Result

* A working **D3 scatter plot** rendered in `#scatter` with hover tooltips and clickable axis labels. &#x20;
* Clean, responsive layout with Bootstrap and a sticky footer.&#x20;
* Jekyll theme configured for **GitHub Pages** deployment (`_config.yml`).&#x20;

## Business Impact

* **Faster insights:** Quickly spot relationships (e.g., income vs. healthcare gaps) for public-health or policy discussions.
* **Reusable template:** A clear D3 baseline teams can adapt for other KPI correlations.
* **Stakeholder engagement:** Interactive exploration improves comprehension vs. static charts.

## Next Steps to Make It Better

* **Analytics:** Add a regression line, correlation stats, and small multiples by region.
* **UX:** Legend, accessible color/contrast, keyboard focus for points, and mobile-first sizing.
* **Data:** Validate sources, add year filters, and enable CSV refresh.
* **Performance:** Debounce resize, limit DOM nodes, and consider WebGL for very large datasets.
* **Ops:** Split `app.js` into modules, add lint/tests, and enable CI to auto-deploy Pages.

## Run Locally

```bash
# from project root (serves CSV without CORS issues)
python -m http.server 8000
# open
http://localhost:8000/index.html
```

## Project Structure

```
.
├── index.html        # Bootstrap page with #scatter mount and script includes
├── app.js            # D3 logic (load CSV, scales, axes, circles, tooltips)
├── data.csv          # input data for the scatter
├── css/
│   ├── style.css     # layout + sticky footer
│   └── d3Style.css   # chart + tooltip styles
└── _config.yml       # Pages/Jekyll theme config
```

*Attribution:* Built with **D3 v5**, **d3-tip**, and **Bootstrap 4**. &#x20;
