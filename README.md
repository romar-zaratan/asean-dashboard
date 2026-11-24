# ASEAN in Numbers

How does the Philippines compare with its ASEAN neighbors? A data dashboard built on live World Bank data, with the cleaning steps shown on the page.

**Live demo:** https://romar-zaratan.github.io/asean-dashboard/

## What it shows

- **4 measures** for all 10 ASEAN countries, 2000 to today: internet use, access to electricity, life expectancy, and GDP per person
- **Trend chart:** the Philippines and one comparison country highlighted, the other 8 in grey for context, with names labeled at the line ends
- **Latest ranking** of all 10 countries
- **Summary tiles:** latest value, 10-year change, and rank
- **ASEAN median** in the tooltip and table
- **Log scale** option for income, where Singapore would otherwise flatten everyone else

## Data cleaning

The raw API response has gaps and countries report on different schedules. The rules:

1. **Gaps stay gaps.** Missing years are not filled in or guessed; the line breaks there.
2. **Fair ranking.** Each country is ranked on its most recent year with data, and that year is shown when it is older than the others.
3. **Rounding only for display.** All calculations use the full values.
4. **Median from real data only.** The ASEAN median for a year uses only countries that reported that year.

The page also reports how many rows were fetched, how many values were missing, and the largest single-year change for the Philippines, so unusual jumps are visible instead of hidden.

## How it works

- **Data:** [World Bank Open Data API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392), fetched live in the browser (no key needed). Responses are cached for the session.
- **No framework, no chart library.** One `index.html` file; charts are hand-built SVG.
- **Color-blind safe:** the two highlight colors were checked with a CVD validator in both light and dark mode, and lines are also labeled by name.

## Run it locally

Open `index.html` in a browser.

## Built by

John Romar Z. Francisco · [Portfolio](https://romar-zaratan.github.io/)
