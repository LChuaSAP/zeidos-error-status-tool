# ZEIDOS Error Status Tool

A browser-based tool for the **Invoice Delivery CoE** team to combine, comment, deduplicate, and export ZEIDOS error status reports.

## Live Tool

**[Open the tool](https://LChuaSAP.github.io/zeidos-error-status-tool)**

## How to use

1. **Load Rule.xlsx** — drop or click to load the rules file
2. **Add new ZEIDOS report files** — drag & drop any new `.xlsb` or `.xlsx` files
3. **Click Process All Steps** — combines all data, applies comments and colors, deduplicates by Invoice Document Number (keeps newest row)
4. **Download** — saves `ZEIDOS Error Status MAIN.xlsx` to your machine, then move it to the SharePoint folder

## What the tool does

- Merges new report files into the existing MAIN file
- Adds a **Comment** column (column A) based on:
  - **Rule1**: matches Sales Organization → assigns comment + color
  - **Rule2**: matches Action for O2I text → assigns comment + color
- Formats Sales Organization as 4-digit zero-padded text
- Formats Invoice Document Number and ODN as integers, centered
- Formats Event Date as DD/MM/YYYY
- Colors Invoice Document Number cells per rule definitions
- Bold light-blue header row
- Auto-fits column widths (fixed widths for Comment, Remark, Action, Sales Org, Rcvr Country)
- Deduplicates by Invoice Document Number — keeps the most recently added row
- Caches the MAIN file in browser localStorage so it auto-restores on next session

## Files

| File | Purpose |
|------|---------|
| `index.html` | The tool (also hosted on GitHub Pages) |
| `Rule.xlsx` | Rules file — stored in SharePoint, load manually each session |
| `ZEIDOS Error Status MAIN.xlsx` | Combined output — stored in SharePoint |

## SharePoint folder

All working files (Rule.xlsx, MAIN.xlsx) are stored in the team SharePoint:
`General > Invoice Delivery CoE > ZEIDOS and OpenText Tickets > ZEIDOS Error Status`
