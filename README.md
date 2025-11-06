# EduFin — Smart Expense Tracker

A lightweight client-side expense tracker built with plain HTML, CSS and JavaScript. Tracks transactions, shows charts, lets you set goals, and includes optional AI suggestions (Gemini integration).

Files
- [edufin.html](edufin.html) — primary single-file app with transactions, goal tracker, Chart.js pie chart and Gemini integration. See functions: [`updateUI`](edufin.html), [`getAiInsight`](edufin.html).
- [index.html](index.html) — alternative/clean expense tracker UI. See functions: [`addExpense`](index.html), [`updateTable`](index.html), [`updateSummary`](index.html), [`updateChart`](index.html).
- [FIN.HTML](FIN.HTML) — another variant with Gemini assistant UI. See functions and handlers: [`addExpense`](FIN.HTML), [`updateTable`](FIN.HTML), [`updateSummary`](FIN.HTML), [`updateChart`](FIN.HTML), [`askGemini`](FIN.HTML).

Key Features
- Add, delete and list expenses.
- Budget and target savings tracking with alerts when budget exceeded.
- Category breakdown via Chart.js pie charts.
- Monthly saving goal and progress (in edufin.html).
- Simple AI assistant integration (Gemini) for suggestions and insights (requires API key).

How to run
- Open any HTML file in a modern browser (double-click or use Live Server in VS Code).
- No build tools or servers are required — fully client-side.

Usage notes
- Add expense fields and click Add Expense. The table, totals and chart update automatically.
- Configure Budget and Target inputs (visible in [index.html](index.html) / [FIN.HTML](FIN.HTML)).
- In [edufin.html](edufin.html) transactions persist to localStorage via the `transactions` variable; see [`updateUI`](edufin.html).
- Charts use Chart.js (loaded from CDN).

AI / Gemini integration
- The code includes calls to the Google Generative Language (Gemini) API:
  - [edufin.html](edufin.html) uses function [`getAiInsight`](edufin.html) and a placeholder API key variable `GEMINI_API_KEY`.
  - [FIN.HTML](FIN.HTML) wires button [`askGemini`](FIN.HTML) to a Gemini request.
- SECURITY: Do NOT commit real API keys. Replace any hard-coded key with an environment/config mechanism or remove the key before sharing. The code expects a key in `GEMINI_API_KEY` or you can replace with a placeholder and pass the key at runtime.

Important functions / symbols (quick links)
- [`addExpense`](index.html) — add new expense (index.html)
- [`updateSummary`](index.html) — updates totals & budget (index.html)
- [`updateChart`](index.html) — rebuilds Chart.js pie chart (index.html)
- [`updateUI`](edufin.html) — updates transaction list, balance and chart (edufin.html)
- [`getAiInsight`](edufin.html) — calls Gemini API for a tip (edufin.html)
- [`askGemini`](FIN.HTML) — Gemini assistant handler (FIN.HTML)

Dev tasks / Improvements
- Move AI keys out of HTML and into a secure server or use a prompt-proxy with server-side key storage.
- Add edit functionality and persistent storage (IndexedDB or server API).
- Validate and sanitize user input more thoroughly.
- Add CSV export/import and monthly filters.

License
- Add your preferred license file (e.g., MIT) if you intend to share this project.

If you want, I can:
- Generate a minimal server wrapper for safe Gemini key handling.
- Add CSV export or local DB persistence.
