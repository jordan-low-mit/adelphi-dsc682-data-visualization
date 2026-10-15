# DSC 682 Course Guide: Weekly Modules and Projects

The eight-week plan from the Fall 2026 course page. Schedules, recordings, administrative details and links to private course files have been removed; links to public readings and videos are kept.

---

## Why we are doing this

At some point in your career you are going to be right about something that matters, and nobody is going to care.

You will have done the work properly. The data will be clean, the method will be sound, the finding will be real. You will put it in front of people who need to know it, and they will nod, and then they will go do what they were already going to do. It is one of the most frustrating experiences in professional life, and almost everyone who works with data has it.

The gap between being right and being believed is what this course is about.

I spent my career in quantitative finance, where the analysis is genuinely hard and the models are genuinely sophisticated. What I learned is that the hard part is usually not the model. The hard part is the twenty minutes in a room where you have to make someone who is smart, busy, and skeptical understand something they did not previously believe, and care enough to act on it. The people who can do that end up running things. The people who cannot end up producing excellent work that sits in a folder.

That skill is not decoration on top of analysis. It is the part where the analysis finally does something.

### Three things I hope you take with you

**How to be understood.** A good visualization is an argument with the unnecessary parts removed. You will learn to strip a chart down until what remains is the point, and to notice when you have made something that looks impressive but says nothing. Edward Tufte, whose book you will read, argued that clarity is close to an ethical obligation. I agree with him. Confusing your audience and misleading them are separated by a thinner line than most people think.

**How not to be fooled.** You are going to spend the rest of your life being shown charts by people who want something from you. Advertisers, politicians, executives pitching a strategy, a fund selling you a product, a headline about a study. Once you have built these things yourself, you cannot unsee the choices behind them: the truncated axis, the cherry-picked window, the scale that turns noise into a trend. This is one of the few subjects where the professional skill and the life skill are identical.

**How to tell the truth about uncertainty.** Real data is incomplete, messy, and often does not say what you hoped. Learning to show that honestly, rather than smoothing it away, is what separates an analyst people trust from one they eventually stop believing. Trust compounds over a career. It is the most valuable thing you will build.

### A word about AI

You have tools now that will write the plotting code for you. That is fine, and you should use them, within the course policy. But it makes the human part more valuable, not less. A model can produce a chart. It cannot decide which question was worth asking, know which number your audience will not believe without proof, or take responsibility when the finding turns out to be wrong. Those judgments are the job, and they are what we will practice.

### How this course runs

We use a flipped model: you do the reading and watching before class, and class is for questions and building things. That means class is only as good as your preparation. Come with questions, including the ones you think are too basic to ask. In my experience the person willing to ask the basic question is usually the one who ends up understanding the material best, and they are almost never the only person in the room who was confused.

You will work in small groups and present. The presentations are not a formality at the end of the real work. They are the real work.

**Prof. Jordan Low**

---

## How the course is graded

The grade comes entirely from projects: four projects of equal weight, each assigned in one class, built with support in class, and due at the next. Work done in class or between classes is practice and is not graded.

Each project is submitted as a presentation video, the supporting artifacts (notebooks, Tableau workbooks, spreadsheets, data files or documents), and a Trello board with tasks assigned and completed. Groups are of three; presentations run 6 to 9 minutes and everyone speaks.

**Prerequisites (pass/fail):** every group member appears and participates in the presentation; the supporting artifacts are submitted; the work is original and directly addresses the project tasks.

**Then weighted:** Presentation Quality 40% · Technical Implementation 40% · Project Management 20%. Different students in the same group can receive different grades based on contribution.

**Texts:** Tufte, *The Visual Display of Quantitative Information*; *Think Python* (free, https://greenteapress.com/thinkpython2/thinkpython2.pdf); and the pandas guide *10 minutes to pandas* (https://pandas.pydata.org/docs/user_guide/10min.html).

---

## Week 1 - Introduction to Data Visualization and Business Storytelling

**In one line:** why a chart persuades, the structure of a business argument, and your first visualization end to end.

We start with structure rather than tools. A chart that is technically perfect and rhetorically shapeless does not move anyone. SCQA and the Pyramid Principle are the two structures consultants use to make a recommendation land, and they will shape every presentation you give in this course.

**Before class**
* SCQA and business storytelling - https://www.youtube.com/watch?v=HnlWiVs9P5o
* Flipped learning, what it is - https://www.youtube.com/watch?v=wwlgsg2IgcY
* Tufte, *Visual Display of Quantitative Information*, chapters 1 to 2
* Data visualization principles, lessons from Tufte - https://moz.com/blog/data-visualization-principles-lessons-from-tufte
* Flipped learning, what it is and when it is effective - https://www.brookings.edu/articles/flipped-learning-what-is-it-and-when-is-it-effective/
* Getting started with Google Colab - https://www.youtube.com/watch?v=i-HnvsehuSw

**Reflection questions**

1. In SCQA, what is the difference between the Complication and the Question? Why does skipping the Complication usually make a recommendation fall flat?
2. Think of a presentation you have sat through that did not persuade you. Was the problem the evidence, the structure, or the delivery?
3. Tufte writes about the data-ink ratio. Find a chart in the news this week and identify three elements you could delete without losing information.
4. Who is the audience for your work right now, and what do they already believe? What would have to be true for them to change their mind?
5. When is a table better than a chart?

**In class**
* SCQA applied to a real finding, then the Pyramid structure on top of it: **S**ituation / **C**omplication / **Q**uestion / **A**nswer. Pyramid: answer first, then two supporting points, then sub-points as needed.
* SCQA and the Pyramid Principle with data visualization, worked on a retirement planning example.
* Colab mechanics, live: save a copy in Drive, what a runtime restart does, and why the cells run in order.

### Project 1 - S&P 500 Storyboard (Python + Tableau)

**Where the data comes from.** SPY is the biggest S&P 500 ETF, and State Street publishes its full holdings every day - every ticker, its weight, and its sector - as a downloadable file on the SPY fund page at ssga.com. The course used saved snapshots of that file (2025-08-26, and 2024-06-05 for year-over-year comparison). A Yahoo Finance notebook then enriches the tickers with fundamentals (P/E, P/S, market cap, employees, and anything else you ask it for). Extra credit: download today's holdings file from ssga.com yourself and note what changed.

Some tickers in these snapshots have since left the index. When the Yahoo Finance notebook throws an error on a ticker, that is usually a company leaving the index, and your code is fine.

**Tasks**

1. Use the Yahoo Finance API notebook to download fields for the SPY tickers. You can add more fields such as returnOnEquity as extra credit.
2. Build at least one visualization in Python per group, starting from the SPY notebook.
3. Use Tableau to make one data visualization **each**. Every group member builds and presents their own.
4. Present the visuals as **one argument, not a stack of charts**, structured with SCQA from Week 1 and ending in a verdict: what is the situation in the index, what complication did your data reveal, and what do your visuals answer?

**Examples shown in class (do not copy - make your own):**
* *Scatter plot:* P/E vs P/S, outliers removed, trendline added, marks are tickers, size is market cap
* *Bar plot:* number of employees by sector, N/A sector removed, sorted by sector size, bar width is market cap weight, bars colored by weight
* *Grouped bar plot:* for every industry, two bars for the sector weights 2024 vs 2025, marks showing numerical totals per bar, labels renamed to be meaningful

**Questions the last section asked**
* *How many charts and slides?* One project, one argument. Use as many slides as the argument needs and no more.
* *Is a written summary required?* No. It is welcome but optional.
* *How do I compare 2024 with 2025?* Compute the year-over-year change in the notebook first, then chart it. Tableau's Quick Table Calculation, Difference, also works; check what it is subtracting before you trust it.
* *How do I save in Tableau?* Tableau Desktop Public Edition saves locally with File, Save As, which gives you the .twbx file to submit. The browser version publishes to your Tableau Public profile instead. Export a chart with Worksheet, Export, Image.

---

## Week 2 - Tableau and Web Data

**In one line:** the second tool, where data actually comes from, and building a storyboard rather than a chart.

Tableau and Python are good at different things. By the end of this week you should be able to argue for one over the other rather than defaulting to whichever you learned first.

**Before class**
* Tableau tutorial 1 - https://youtu.be/jEgVto5QME8
* Tableau tutorial 2 - https://youtu.be/6xv1KvCMF1Q
* Python Graph Gallery, complete guide - https://python-graph-gallery.com/
* Seaborn gallery with code examples - https://seaborn.pydata.org/examples/index.html
* Visual Capitalist, for examples worth stealing - https://www.visualcapitalist.com/

**Reflection questions**

1. What can Tableau do in five minutes that would take you an hour in Python? What is true in the other direction?
2. A scatter of P/E against P/S has obvious outliers. What are the arguments for removing them, and what are you hiding when you do?
3. When you size a mark by market cap, what have you told the reader that a plain scatter does not? What could that mislead them about?
4. Pick a chart from Visual Capitalist. What is the single sentence it is arguing? Could it be made in half the ink?
5. Your data came from an API written by someone else. What would you need to check before you put it in front of an executive?
6. Tufte considers the pie chart close to indefensible, yet executives ask for them constantly. Why do humans compare angles so poorly, and when is a pie chart actually the right choice?

**In class**
* Build the three example charts from Project 1 live and critique them: the sector bar chart, the P/E vs P/S scatter, and a dashboard that links them.
* **The pie chart debate.** Build a sector-weights pie next to a sorted bar of the same data. We discuss when to push back on a request for a pie and when it is fine (two or three categories, one dominant share).
* Python, Tableau or Power BI: which tool for which job.
* Project idea to try, recreate this sector weight graph - https://www.hussmanfunds.com/research/rs250316/

**Four things worth remembering**

1. Tableau defaults to SUM and will happily show you nonsense. A technology P/E of 1,872 is an aggregation problem, not a data problem.
2. Average or median is an editorial choice. Show the median, then break the outliers out separately so they get discussed rather than hidden.
3. Make colour carry a second variable. Length for size, colour for how expensive, and the chart starts saying something.
4. Prefer the fix that deletes nothing. A log axis keeps every company in the picture; a filter improves the chart by deleting evidence.

---

## Week 3 - Exploratory Data Analysis

**In one line:** finding a pattern is easy; deciding whether it supports a business claim is the work. Data quality, missing values, descriptive statistics, charts for exploration and regression, practiced on Airbnb listings before you take them to the Fortune 500.

**Before class: the five EDA modules**

**A. Data quality assessment and cleaning.** Handling missing values, duplicates, and consistency across multiple years.
* A complete guide to data cleaning in Python - https://towardsdatascience.com/the-ultimate-guide-to-data-cleaning-3969843991d4
* Handling missing data with Pandas - https://www.datacamp.com/tutorial/techniques-to-handle-missing-data-values

**B. Descriptive statistics.** Central tendency, spread, distribution shape.
* Statistics fundamentals, StatQuest - https://www.youtube.com/watch?v=qBigTkBLU6g
* Descriptive statistics in Python using Pandas - https://realpython.com/python-statistics/
* Pandas describe method guide - https://www.w3schools.com/python/pandas/ref_df_describe.asp

**C. Data visualization for exploration.** Categorical distributions, relationships, temporal trends.
* Matplotlib and Seaborn tutorial, Corey Schafer - https://www.youtube.com/watch?v=UO98lJQ3QGI

**D. Bivariate and time series analysis.**
* Time series analysis, Krish Naik - https://www.youtube.com/watch?v=e8Yw4alG16Q
* Correlation analysis in Python - https://www.geeksforgeeks.org/python-pandas-dataframe-corr/
* Time series visualization with Python - https://www.machinelearningplus.com/time-series/time-series-analysis-python/

**E. Linear regression.**
* Linear regression clearly explained, StatQuest - https://www.youtube.com/watch?v=nk2CQITm_eo
* Linear regression in Python with scikit-learn - https://realpython.com/linear-regression-in-python/
* scikit-learn documentation - https://scikit-learn.org/stable/modules/linear_model.html

**Reflection questions**

1. How do you assess data completeness across different time periods, and what does a gap in one year do to a trend line?
2. What strategies work best for missing numerical values, and when is dropping rows the honest choice rather than the lazy one?
3. How do you tell a meaningful correlation from a spurious one? Give an example from your own field.
4. Why might the median be more appropriate than the mean for skewed data? Name a business metric where using the mean would actively mislead.
5. What do regression coefficients tell you that a scatter plot does not? What does R-squared mean in plain language to someone who has never taken statistics?
6. If a variable depends on another variable you have no data for, what are the dangers?
7. The Airbnb data has latitude and longitude. What does a map of listings show about price that a histogram of price cannot? And what is the classic trap when you color geographic regions by a raw value?

**In class**
* The five modules applied to New York Airbnb listings, then an investment case: six business questions and one imperfect file.
* **Map exercise (optional).** The Airbnb data is the one dataset in this course with coordinates: build a Tableau map view of listings colored by price, and ask what the spatial pattern says that no aspatial chart could. Python twin if you prefer: a borough-level choropleth in GeoPandas.

**Five things worth remembering**

1. Say what one row is before anything else: one listing snapshot for Airbnb, one company in one year for the Fortune 500.
2. A missing price is not a price of zero, and filling blanks with the mean creates data nobody observed. When 41.5% of Airbnb prices are missing, find out why, analyse the 21,279 observed prices, and say so beside every result.
3. Use the median for skewed data. The typical Airbnb price is $150, against a mean of $448 and a maximum of $50,052. Inspect the maximum; never just delete it.
4. A near-zero correlation leaves the question open. Price against reviews per month has a Spearman correlation of about 0.03, and reviews are an incomplete measure of demand.
5. A regression slope has units, and R-squared describes these rows only. Neither shows cause. Pause before the words causes, drives and leads.

### Project 2 - Fortune 500 Exploratory Analysis

Find something surprising in the data and defend it. The deliverable is an argument about business models, supported by distribution analysis - not a tour of every chart you know. The full specification is in [assignments/fortune500_eda_project.md](assignments/fortune500_eda_project.md).

**Three parts**

1. **Comprehensive EDA**, including the sector data-quality fix. Only about 32% of rows carry a sector; a documented industry-to-sector mapping lifts that to about 92%. Disclose the mapping rules and list the industries left unmapped. Document every transformation so another person can reproduce it.
2. **Statistical visualizations**: the six required charts plus at least two advanced charts, so eight or more. The charts form one story: question, overview, comparison, explanation, qualified conclusion. A chart that does not change what the audience understands goes in an appendix.
3. **Regression**: revenue on employees, overall and year by year, with the slope in units, R-squared, a residual plot, and no causal claim.

Within the technical work, the template weights EDA 40%, visualizations 30% and regression 30%. A beautiful chart cannot make up for an undocumented transformation.

**Before you build the charts,** state your group's one sentence: what you want to investigate, what you must verify before you claim it, and why. *Technology is the best sector* is too short: it names no measure, no period, and no definition of best.

**Keep the SCQA structure in the video.** The situation is what the data shows overall, the complication is the surprise you found, the question is what that surprise forces you to ask, and the answer is your qualified conclusion. The charts are the evidence, in that order.

---

## Week 4 - Distributions and Outliers

**In one line:** what an average hides. Box plots, the IQR rule, violin plots, the KS test for separating groups, and word clouds for text-heavy fields.

**Before class**
* Box plots in Python - https://cduvallet.github.io/posts/2018/03/boxplots-in-python
* Understanding Kolmogorov-Smirnov tests - https://towardsdatascience.com/understanding-kolmogorov-smirnov-ks-tests-for-data-drift-on-profiled-data-5c8317796f78

**How a box plot is actually calculated**

1. Interquartile range (IQR) is Q3 minus Q1. That is the box. The line inside is the median.
2. Whiskers extend 1.5 times the IQR from the edges of the box. The lower whisker reaches the smallest point greater than or equal to Q1 minus 1.5 IQR; the upper whisker reaches the largest point less than or equal to Q3 plus 1.5 IQR.
3. Points beyond the whiskers are plotted individually and treated as potential outliers.

A cousin worth knowing: the **violin plot** replaces the box with the full density shape, so you see bimodality a box plot hides. Seaborn draws one in a single line; we will look at when the extra detail helps and when it just adds ink.

**Reflection questions**

1. When should you use a box plot rather than a histogram, and what does each one hide?
2. The 1.5 IQR rule is a convention, not a law. What happens to your outlier count if the underlying distribution is heavily skewed?
3. What does a KS test tell you that comparing two means does not?
4. A violin plot shows the full distribution shape where a box plot shows five numbers. Describe a dataset where the box plot would actively mislead and the violin would not.
5. Word clouds are widely criticised by visualization experts. What is the criticism, and when is a word cloud still the right choice?
6. You find four features that separate financial firms from non-financial ones. How would you check that the separation is real rather than an artifact of how the data was collected?

**In class**
* Four businesses with the same mean and the same standard deviation, then a box plot built step by step, the 1.5 IQR rule on skewed data, violins, the ECDF and the KS test, and TF-IDF word clouds on bank earnings calls.
* Why this course now: MIT's letter on AI and education - https://orgchart.mit.edu/letters/ai-and-education-watershed-moment-mit

**Week 4 exercise (practice, ungraded): box plots, KS test and word clouds.** The techniques for Project 2's distribution work, practiced on a different dataset: the SVB financial-risk data from the March 2023 collapse (financial ratios plus earnings-call transcripts).

* *Task 1, box plots + KS test.* Use the KS test to reduce a large feature set to a smaller number of significant features. Use your business judgement to choose 4 features that can predict whether a company is in the Financial sector. Plot box plots showing how the distributions of those features differ, Finance vs Non-Finance.
* *Task 2, word clouds.* Create 3 word clouds illustrating the main topics for: Non-Finance, Finance with low risk, Finance with high risk. Explain what the visualization says about the business models of the three segments.
* *Task 3, combining the two.* Create word clouds split by the features chosen in Task 1 and explain what you see in business-model terms. Example: if R&D/Sales separates the groups, build word clouds for high and low R&D/Sales companies and describe what each group is actually doing.

**Five things worth remembering**

1. One average can describe completely different businesses. Four datasets with the same mean of 50 and the same standard deviation of 12 can be a bell curve, two separate customer groups, a flat spread, or a long tail. Report only the average and you have thrown away everything that tells them apart.
2. Fences sit 1.5 times the IQR beyond each quartile and decide what counts as inside; you never draw them. Whiskers stop at the last real data point inside the fences, which is why whiskers come out uneven.
3. On skewed data, flagged points are usually your biggest customers, not errors. Fortune 500 revenue flags 61 companies in raw dollars and 18 on a log scale. Say so, or move to a log scale.
4. A box plot hides humps. When one column mixes two populations, use a violin or a histogram. Under about 30 points, show the dots, and put n on every label.
5. KS compares whole shapes, so it sees spread, skew and tails that a comparison of means misses. With enough data everything is significant; D says whether the difference matters.

---

## Week 5 - Time Series and Financial Charts

**In one line:** charts built for time, and the week where axes start lying.

Candlesticks, cycle plots, spread plots and the yield curve. Every one of these encodes something a line chart cannot, and every one of them can be used to mislead.

**Before class**
* Candlestick charts explained - https://www.youtube.com/watch?v=7hEMwOKmYxY
* Histograms and spread plots - https://www.youtube.com/watch?v=THJcN4qr00U
* How to look for seasonality in time series data, Tableau cycle plots - https://www.tableau.com/blog/how-look-seasonality-your-time-series-data-25578

**Reflection questions**

1. A candlestick encodes four numbers per period. What question is it good for, and when is a plain line chart the better answer?
2. Truncating the y-axis is sometimes honest and sometimes deceptive. Where is the line, and how would you defend your choice to a skeptical reader?
3. What does a cycle plot show that a normal time series plot buries?
4. A spread plot of long large banks against short regional banks removes market direction. What question does that let you ask, and what does it hide?
5. The yield curve inverts, and a recession follows some months later. How would you show that relationship honestly, including the times it did not work?
6. An interactive chart lets the reader hover, zoom, and choose. When does that serve the audience, and when is it an excuse for not deciding what the chart is about?

**In class**
* Candlesticks, histograms and spread plots, the yield curve, and energy-futures fundamentals from EIA data.
* **Interactive charts with Plotly.** Colab renders Plotly natively: `pd.options.plotting.backend = "plotly"` and every `.plot()` becomes zoomable and hoverable. We flip one of the notebooks to the Plotly backend live and discuss when interactivity earns its place in a business presentation.

**Before you build Project 3.** Save your own copy, then check three things. Convert the date column with `pd.to_datetime`, since it loads as text. Make sure the years in the text match the years the code downloads. Never fill a gap with a placeholder value: a `fillna(1)` on a shifted series invents months of data that never happened.

**Six things worth remembering**

1. Choose the chart for the audience. Weekly candles show a collapse at a glance where daily candles bury it, and a log axis shows percentage moves, which is what investors care about.
2. A gap is where no trade happened. A stop-loss cannot protect you across a gap.
3. A cycle plot shows when. It cannot show why.
4. Setting a histogram range drops the extreme days. Say so on the chart.
5. Show when a signal worked and when it did not. The 10-2 yield spread has led recessions by anywhere from 6 to 34 months. Report the range, not one average.
6. Aggregating changes what a point means: 18,000 daily points and 600 monthly averages can tell different stories, so say which one you are showing. Interactivity answers follow-up questions; the title still has to make the argument.

### Project 3 - A Financial Event in Five Charts

The specification and the Option A data code are in [notebooks/01_svb_collapse_in_five_charts.ipynb](notebooks/01_svb_collapse_in_five_charts.ipynb).

---

## Week 6 - Comparison: Treemaps, Heatmaps, Slope Graphs

**In one line:** showing many things at once without losing the reader.

Size, colour and position are the three encodings you have. This week is about choosing among them deliberately instead of by habit.

**Before class**
* Slope graphs in Python - https://cduvallet.github.io/posts/2018/03/slopegraphs-in-python
* Tufte slope graph implementation - https://github.com/mhlinder/tufte-slopegraph
* Learn GeoPandas, plotting US maps - https://jcutrer.com/python/learn-geopandas-plotting-usmaps
* Tufte, *Visual Display of Quantitative Information*, the chapters on graphical integrity and data density

**Reflection questions**

1. A treemap encodes size by area and a second variable by colour. What happens to a reader's accuracy when you ask them to compare two areas that are not adjacent?
2. When is a heatmap better than a table of the same numbers? When is it worse?
3. Slope graphs show change between two points and nothing in between. What kind of argument does that suit, and what does it conceal?
4. Choropleth maps colour regions by value. Why is population density the classic trap, and how would you avoid it?
5. You have twelve series to show. What are your options besides twelve lines on one axis, and how would you choose?

**In class**
* Heatmaps and treemaps of year-to-date sector returns and size.
* Size, colour and position; heatmaps with the full table in the appendix; categorical palettes; slope graphs.
* Three fixes that improved the most charts last section: centre the colour scale at zero when values can be negative; put the date of the data on every chart; and check the denominator before you divide.

---

## Week 7 - Embeddings and Clustering

**In one line:** visualizing data that has no natural coordinates.

Text has no x-axis. Embeddings turn language into geometry, and once you have geometry you can plot it. UMAP reduces it to something a human can look at, and HDBSCAN finds the groups.

**Before class**
* Understanding UMAP, an interactive explainer - https://pair-code.github.io/understanding-umap/

**Reflection questions**

1. What does it mean for two companies to be close together in embedding space? Close in what sense?
2. UMAP distances are not preserved faithfully from the original space. Given that, what claims can you honestly make about a UMAP plot, and what claims are you not entitled to?
3. HDBSCAN leaves some points unclustered as noise. Why is that more honest than k-means, which assigns everything?
4. If the clusters you find do not match the official sector classifications, which one is wrong?
5. You show a UMAP plot to an executive who has never seen one. What is the first sentence out of your mouth?

**In class**
* Walkthrough: 650 companies, their Wikipedia pages and embeddings.

**Five things worth remembering**

1. An embedding turns a page into a list of numbers, and similar pages get similar numbers. Cosine similarity compares two lists; the ranking matters more than the raw number. The model reads only about the first 400 words of each page.
2. Close means close in the text. Two companies whose pages read alike can differ completely in size, profit or returns, so say which kind of close you mean in the title or the caption.
3. Know a data error from a finding. Nine Wikipedia pages were shared by 26 rows, and a shared page is a data error. The 80 companies HDBSCAN left ungrouped are the opposite: that is where to look first.
4. A UMAP map keeps neighbours, not distances. Write the settings in the caption, and tell your reader what a dot is and what closeness means before you show any result.
5. When the text disagrees with the official sector, that disagreement is the story: Amazon, Starbucks, Walmart.

### Project 4 - Company Relationships from Embeddings

Use embeddings of company descriptions to reveal structure among companies that the standard sector classifications miss, and make an argument about what that structure means - which companies are secretly similar, which sector labels mislead, and what an investor or strategist should do differently because of it.

Four steps: **embed, cluster, compare, argue.** The last step is the one that counts.

1. Embed the company descriptions and reduce with UMAP, following the template. Check for bad rows first, such as one Wikipedia page shared by several companies, and say in a footnote what you dropped.
2. Cluster with HDBSCAN. Treat the unclustered noise points honestly - they are part of the story. Name each group by what is inside it.
3. Compare your clusters against the official sector classifications: where they agree, where they disagree, and which disagreements are interesting rather than artifacts.
4. Present the finding as an argument in five charts, the same shape as Project 3: each chart answers the question the last one raised, makes one claim in its title, and keeps the evidence beside it. Explain how to read a chart before you show its result. The first sentence you say over a UMAP plot to someone who has never seen one is the hardest sentence in the deck.

---

## Week 8 - Project 4 Presentations

**In one line:** groups present, the class asks questions, and we look back at what actually persuaded.

* Presentations, 6 to 9 minutes per group, everyone speaks
* Questions from the class, not only from me
* The look back: across your four projects, which chart changed someone's mind, and which did nothing?

---

## Extra credit and further reading

**Chart makeover (individual, optional).** Take one chart from any of your projects and remake it with one technique from class: centre the colour scale at zero, date the data, or fix the denominator. Show the before and after side by side, with one sentence on why you changed it, and about 150 words on what the new chart shows and one limit. Tableau is fine.

**Reference shelf**
* Visual Capitalist, a daily habit worth forming - https://www.visualcapitalist.com/
* Data visualization principles from Tufte - https://moz.com/blog/data-visualization-principles-lessons-from-tufte
* Slope graphs - https://github.com/mhlinder/tufte-slopegraph and https://cduvallet.github.io/posts/2018/03/slopegraphs-in-python
* GeoPandas for US maps - https://jcutrer.com/python/learn-geopandas-plotting-usmaps
* Seaborn FacetGrid axis labels - https://cduvallet.github.io/posts/2018/11/facetgrid-ylabel-access
* Python Graph Gallery - https://python-graph-gallery.com/
