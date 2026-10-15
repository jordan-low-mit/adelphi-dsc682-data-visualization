# DSC 682: Data Visualization for Business Analytics

Adelphi University, Robert B. Willumstad School of Business · Graduate (MS in Business Analytics) · Fall 2025 and Fall 2026 (eight-week modules)

A graduate course about the gap between being right and being believed: turning analysis into charts and presentations that make a busy, skeptical audience act. Students build visualizations in Python and Tableau on real business and market data, and every project ends as a recorded presentation structured as one argument rather than a tour of charts. The course runs as an eight-week module, with four group projects on a two-week rhythm.

## What students learn

- Structuring a business argument with SCQA (Situation, Complication, Question, Answer) and the Pyramid Principle, and presenting charts as one argument that ends in a verdict.
- Building and critiquing charts in Python (pandas, Matplotlib, Seaborn, Plotly) and in Tableau, and arguing for one tool over the other for a given job.
- Exploratory analysis that holds up: data quality and missing values, the median for skewed data, outliers with the IQR rule, box and violin plots, the KS test, and regression reported in units with no causal claim.
- Charts built for time and markets: candlesticks, cycle plots, spread plots, the yield curve and interactive Plotly charts, and how each can mislead.
- Showing many things at once with treemaps, heatmaps, slope graphs and maps, choosing size, colour and position deliberately.
- Visualizing text: embeddings of company descriptions, UMAP and HDBSCAN, compared against official sector labels.
- Honest charts: dating the data, checking the denominator, centring a diverging colour scale at zero, and showing when a signal did not work.

## Highlights

| Material | What it covers | Open |
|---|---|---|
| [01_svb_collapse_in_five_charts](notebooks/01_svb_collapse_in_five_charts.ipynb) | Project 3, "A Financial Event in Five Charts", with the four options (Silicon Valley Bank, the 2025 trade war, the US economy in sectors and jobs, Microsoft product growth) and the Option A data code: FRED series kept at their native frequencies, the share of U.S. deposits that are uninsured, a five-year Treasury priced from its yield, and cleaning a bank price file around the SVB failure. The notes explain four data pitfalls the code fixes. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jordan-low-mit/adelphi-dsc682-data-visualization/blob/main/notebooks/01_svb_collapse_in_five_charts.ipynb) |
| [fortune500_eda_project](assignments/fortune500_eda_project.md) | Project 2 specification, "Fortune 500 Exploratory Data Analysis" (1996 to 2023): data quality and an industry-to-sector repair, univariate, bivariate and time-series analysis, six required and two advanced visualizations, year-by-year regression of revenue on employees, and a 6 to 9 minute presentation. | [Read](assignments/fortune500_eda_project.md) |
| [course-guide](course-guide.md) | The eight weekly modules: the instructor's statement of why the course exists, pre-class readings, reflection questions, "things worth remembering" from each session, and the briefs for all four projects. | [Read](course-guide.md) |

## How the course is taught

- **Flipped classroom.** Students watch and read before class; class time is for questions and problem-solving, not lecture.
- **Graded only on projects.** Four group projects of equal weight, each submitted as a recorded 6 to 9 minute presentation in which every member speaks, plus the supporting artifacts and a Trello board. Participation, artifacts and original work are pass/fail prerequisites; then Presentation Quality 40%, Technical Implementation 40% and Project Management 20%, with individual grades within a group based on contribution.
- **Every project is a portfolio piece.** The presentation video is submitted as a shareable link so students can post it or show it to an interviewer as project experience.
- **AI with verification.** AI tools may be used for brainstorming, explanation and debugging, with a required disclosure of which tools were used, how, and how the output was verified. Hallucinations and bugs from generated work are penalized even when the rubric does not ask for that output.

## Data

- **01:** FRED series downloaded by the notebook (public, no API key): `CORESTICKM159SFRBATL` (inflation, monthly), `DGS5` (five-year Treasury yield, daily), `BOGZ1FL763139105Q` (uninsured deposits of U.S.-chartered banks, quarterly) and `DPSACBW027SBOG` (deposits of all commercial banks, weekly). The bank price file (`Banks_SVB_2023.csv`: JPM, C, BAC, SIVB, NYCB and SBNY, 3 January to 31 May 2023) was provided to the class and is **not included**. To run that cell, supply a daily file with a `ticker` column, a `dint` date column stored as YYYYMMDD numbers, open, high, low, close, volume and market capitalization.
- **Fortune 500 project:** `Fortune 500 Companies.csv`, 1996 to 2023, with company rankings, revenue, profit, employees, market value, industry and sector, and geographic location. It was provided to the class and is **not included**.
- **Course guide:** the projects and in-class work also use SPY holdings files published by State Street (ssga.com), fields from the Yahoo Finance API, New York Airbnb listings and the Wikipedia pages of 650 companies. The in-class notebooks for these are not part of this repository.

## Instructor

[Jordan Low](https://github.com/jordan-low-mit), adjunct professor at Adelphi University.

---

Materials © Jordan Low. Shared for reference; please ask before reusing in a course.
