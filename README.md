# Student Insights — Week 5 Mini Web Application

A responsive student dashboard that combines static JSON data, dynamic metrics, a score distribution chart, searchable records, sorting, and department filtering. It is a vanilla HTML/CSS/JavaScript project with no build step or third-party JavaScript dependencies.

## Features
- Dashboard summary cards recalculate from the visible records.
- Score distribution chart updates with the selected department and search query.
- Search by student name, ID, or department.
- Sort student records by name, department, score, or attendance by activating the column buttons.
- Status labels identify records with a score below 70 or attendance below 80%.
- Responsive desktop, tablet, and mobile layout.
- Semantic landmarks, skip link, visible keyboard focus, table caption, labelled form controls, and an ARIA live status region.
- Reduced-motion preference support and graceful error message when JSON cannot load.
- Minified CSS/JS files are included for deployment and performance comparison.

## Files
- `index.html` — semantic page structure.
- `styles.css` — responsive layout and accessible visual states.
- `app.js` — JSON loading, filtering, sorting, metrics, chart, and error handling.
- `data/students.json` — sample data.
- `styles.min.css`, `script.min.js` — minified assets for the optimized deployment.
- `performance-and-accessibility-report.md` — project report and test record.

## Run locally
The dashboard fetches JSON, so do not open `index.html` directly as a `file://` URL. Use a local HTTP server:
1. Open the folder in Visual Studio Code.
2. Install the **Live Server** extension if it is not already installed.
3. Right-click `index.html` and select **Open with Live Server**.
4. Check that the dashboard displays 12 sample records. Try the department selector, search, and sortable table headers.

If Node.js is installed, another option is `npx serve .`. No Python installation is required.

## Deploy using GitHub Pages
1. Upload the project files and folders to a public GitHub repository.
2. Open **Settings → Pages**.
3. Under Build and deployment, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Wait for GitHub Pages to publish and open the provided URL.

For the optimized deployment, update `index.html` to reference `styles.min.css` and `script.min.js` instead of the unminified assets. Keep the `data/` folder at the same relative path.

## Test checklist
- [ ] Initial page loads with 12 records when served over HTTP.
- [ ] Department filter updates cards, chart, activity summaries, and table.
- [ ] Search matches a name, ID, or department and handles no matches.
- [ ] Each column header sorts ascending and descending on repeated activation.
- [ ] Reset filters restores all records and moves focus to the department selector.
- [ ] Keyboard-only navigation reaches all controls and shows focus outlines.
- [ ] Mobile layout can be used without horizontal page overflow.
- [ ] Browser developer tools show no missing JSON or asset requests.

The included data is fictional sample data and must not be used to make real academic decisions.
