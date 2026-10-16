# Week 5 Task Report — Final Project Integration: Mini Web Application

## 1. Project overview
Student Insights is a mini dashboard built with semantic HTML, responsive CSS, vanilla JavaScript, and a static JSON dataset. It integrates responsive layout, DOM manipulation, data-driven UI, accessibility practices, error handling, and optimized asset delivery.

## 2. Requirements and design decisions
The dashboard includes four summary metrics, a score distribution chart, activity insights, and a student records table. A department selector and search field filter the visible data. Table heading buttons sort records. The interface uses a sidebar navigation on wider screens and a compact navigation row on small screens. The visual system uses consistent spacing, restrained colours, clear typography, and status labels so that key information is easy to scan.

## 3. Implementation
- `index.html` defines the page using `header`, `nav`, `main`, `section`, `article`, `table`, and `footer` landmarks/elements.
- `data/students.json` provides 12 fictional records across Computer Science, Design, and Business.
- `app.js` fetches and validates JSON, calculates the metric cards, renders the chart and table, and supports search, department filtering, sorting, and reset.
- `styles.css` provides responsive breakpoints for desktop, tablet, and mobile, visible focus styles, and reduced-motion support.
- `script.min.js` and `styles.min.css` provide minified deployment assets.

## 4. Accessibility improvements
The page includes a skip link, labelled controls, semantic table headers and caption, visible `:focus-visible` outlines, a live status region for important updates, and an accessible chart description that announces the score-band counts. Decorative symbols are hidden from assistive technology where appropriate. The layout respects `prefers-reduced-motion`. These measures support keyboard navigation and screen-reader comprehension. This implementation is designed with WCAG 2.2 AA considerations in mind; a formal conformance claim requires a full audit.

## 5. Performance enhancements
The project avoids framework dependencies and external charting libraries. JavaScript is loaded with `defer`, CSS is kept in external files, and minified CSS/JS assets are included. The JSON request uses the browser cache. The dashboard uses a small local dataset and CSS-rendered chart bars rather than a heavy chart library. The font import is an optional external request; system fallbacks are provided if it is unavailable.

## 6. Testing record and observed outcomes
The following are source-level checks and expected functional cases. Browser-based Lighthouse, WAVE, and cross-browser checks must be run on the deployed or locally served page before claiming measured performance or accessibility scores.

| Test case | Expected outcome | Evidence/status |
|---|---|---|
| Dataset structure | 12 records with ID, name, department, score, and attendance | Confirmed by inspecting `data/students.json` |
| Metric calculation | Count, average score, attendance, and support count derive from currently visible records | Implemented in `renderMetrics()`; browser execution still required |
| Department filter | Selecting a department updates all dashboard views | Implemented in change handler; browser execution still required |
| Search | Name, ID, and department can be searched; empty result message appears for no matches | Implemented in input handler and empty-state logic; browser execution still required |
| Sorting | Name, department, score, and attendance can be sorted both directions | Implemented with button event handlers; browser execution still required |
| JSON failure | Clear fallback message appears if the dataset cannot be fetched or validated | Implemented in `loadData()` catch path; failure simulation still required |
| Keyboard access | Skip link, select, search, sort buttons, and reset button can be reached by keyboard | Visible focus styling and native controls implemented; manual test still required |
| Responsive layout | Layout changes at 1100px and 700px breakpoints | CSS media queries present; device/browser test still required |
| Performance score | Lighthouse score and Core Web Vitals | Not measured; do not report a fabricated score |

## 7. How to test
Run the folder through VS Code Live Server or another local HTTP server; direct `file://` opening will normally block the JSON fetch. Verify the listed test cases, then run Lighthouse from Chrome DevTools and WAVE on the served page. Record actual results and screenshots before final submission.

## 8. Conclusion
The project brings together the main frontend skills from the earlier weekly tasks: structured HTML, responsive styling, JavaScript interactions, accessibility features, and performance-aware asset choices. The code includes error handling and a test plan. The remaining step is to execute browser-based checks and record real outcomes rather than infer them from the source code.

**Data note:** all student names and records are fictional sample data.
