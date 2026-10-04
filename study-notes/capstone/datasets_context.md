# Happiness / Well-Being Datasets — Context & Local Files

Datasets gathered for the UCB ML/AI capstone project on applying ML to happiness and
well-being. Files that could be downloaded directly (no login/registration) are stored
in this folder; datasets that require manual download are documented below with exact
steps.

## Downloaded files

### 1. Self-reported life satisfaction (World Happiness Report proxy)
- **Local file:** [world_happiness_life_satisfaction_owid.csv](world_happiness_life_satisfaction_owid.csv)
- **Source:** Our World in Data, "Self-reported life satisfaction" (Cantril Ladder, 0–10 scale), underlying source is the **Gallup World Poll** — the same survey the World Happiness Report is built on.
- **Original URL:** https://ourworldindata.org/grapher/happiness-cantril-ladder.csv
- **Shape:** 2,269 rows. Columns: `Entity` (country), `Code` (ISO3), `Year`, `Self-reported life satisfaction`.
- **Use:** Target variable (happiness score) for a country-year regression, in place of/alongside the official WHR Excel workbook (which is not scriptable without a browser session — see "Manual downloads" below).

### 2. Share of people who say they are happy
- **Local file:** [world_happiness_pct_happy_owid.csv](world_happiness_pct_happy_owid.csv)
- **Source:** Our World in Data, based on World Values Survey / Gallup.
- **Original URL:** https://ourworldindata.org/grapher/share-of-people-who-say-they-are-happy.csv
- **Shape:** 424 rows. Columns: `Entity`, `Code`, `Year`, `Happiness: Happy` (%).
- **Use:** Alternative/secondary happiness target (binary-leaning "% happy" vs. the continuous Cantril ladder score); fewer country-years than file 1, useful as a robustness check.

### 3. GDP per capita
- **Local file:** [world_happiness_gdp_per_capita_owid.csv](world_happiness_gdp_per_capita_owid.csv)
- **Source:** Our World in Data / World Bank.
- **Original URL:** https://ourworldindata.org/grapher/gdp-per-capita-worldbank.csv
- **Shape:** 7,444 rows. Columns: `Entity`, `Code`, `Year`, `GDP per capita`, `World region according to OWID`.
- **Use:** Core economic predictor for the happiness regression (the "GDP per capita" factor in WHR-style models).

### 4. Life expectancy
- **Local file:** [world_happiness_life_expectancy_owid.csv](world_happiness_life_expectancy_owid.csv)
- **Source:** Our World in Data.
- **Original URL:** https://ourworldindata.org/grapher/life-expectancy.csv
- **Shape:** 21,564 rows (longest time series, back to 1950). Columns: `Entity`, `Code`, `Year`, `Life expectancy`.
- **Use:** Health predictor (the "healthy life expectancy" factor in WHR-style models). Join to files 1–3 on `Code` + `Year`.

> Files 1–4 all share `Entity`/`Code`/`Year` keys, so they merge cleanly into a single
> country-year panel for regression/feature-importance work (Project idea #1).

### 5. CDC BRFSS 2023 — raw survey microdata
- **Local file:** [brfss_2023_llcp_xpt.zip](brfss_2023_llcp_xpt.zip) (contains `LLCP2023.XPT`, SAS transport format, ~1.2 GB unzipped)
- **Source:** CDC Behavioral Risk Factor Surveillance System, 2023 annual survey.
- **Original URL:** https://www.cdc.gov/brfss/annual_data/2023/files/LLCP2023XPT.zip
- **Shape:** 433,323 individual respondent records, US + territories.
- **Use:** Individual-level predictor of self-reported life satisfaction / mentally-unhealthy-days from health behaviors, income, employment, access-to-care (Project idea #4). Requires `pyreadstat` or `pandas.read_sas` to load the `.XPT` file.
- **Note:** the unzipped file is ~1.2 GB — consider adding it to `.gitignore` rather than committing to git.

### 6. CDC BRFSS 2023 — codebook
- **Local file:** [brfss_2023_codebook.zip](brfss_2023_codebook.zip) (contains `USCODE23_LLCP_021924.HTML`)
- **Source:** CDC, companion codebook for file 5.
- **Original URL:** https://www.cdc.gov/brfss/annual_data/2023/zip/codebook23_llcp-v2-508.zip
- **Use:** Variable definitions/value labels for every column in `LLCP2023.XPT` — required to interpret the raw survey codes (e.g., which column is life-satisfaction, income bracket, employment status).

## Manual downloads (no scriptable no-login endpoint found)

These datasets could not be fetched with a direct, unauthenticated URL — each either
sits behind a login/registration wall or the provider's current API/site blocked
scripted access during this session. Steps to get them manually:

- **World Happiness Report official Excel workbook** (all six WHR factors + rankings,
  as published by the Sustainable Development Solutions Network): go to
  https://data.worldhappiness.report , which is a JS-rendered data portal — the
  download link isn't a static URL. Open "Explore the data" in a browser and export
  the table, or use the Kaggle mirror `unsdsn/world-happiness` (requires a free Kaggle
  account + API token).
- **OECD Better Life Index** (11 well-being dimensions: housing, income, jobs,
  community, education, environment, civic engagement, health, safety, work-life
  balance, life satisfaction): the old bulk-CSV endpoint (`stats.oecd.org`) has been
  retired and the new OECD Data Explorer (`data-explorer.oecd.org`) requires
  navigating the UI to find the current dataflow ID before its SDMX API will serve
  data — go to https://data-explorer.oecd.org , search "Better Life Index", and use
  the on-page "Export → CSV" button.
- **World Values Survey (WVS)** individual-level data: requires free registration at
  https://www.worldvaluessurvey.org/WVSDocumentationWV7.jsp before the SPSS/Stata/CSV
  files unlock.
- **General Social Survey (GSS)** cumulative file: requires using the GSS Data
  Explorer (https://gssdataexplorer.norc.org) to build and export a custom extract;
  no static bulk-download URL is exposed without going through that tool (or ICPSR,
  which also requires an account).
- **OSMI Mental Health in Tech Survey**: the canonical copy lives on Kaggle
  (`osmi/mental-health-in-tech-survey`), which requires a Kaggle account + API token
  (`kaggle datasets download osmi/mental-health-in-tech-survey`) — no unauthenticated
  download endpoint exists. Numerous third-party GitHub mirrors of this CSV exist but
  their provenance/cleaning is unverified, so they weren't used here.

## Suggested next step

Join files 1–4 into one country-year table (inner join on `Code`+`Year`) as the
dataset for Project idea #1 (World Happiness Report-style regression + SHAP feature
importance) — it's fully downloaded and ready to load with `pandas.read_csv`.
