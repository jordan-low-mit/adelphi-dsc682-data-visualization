# Fortune 500 Exploratory Data Analysis Project

*DSC 682 Data Visualization for Business Analytics, Project 2 (assignment specification). The dataset is not included in this repository.*

## Project Overview
In this project, you will perform a comprehensive Exploratory Data Analysis (EDA) on the Fortune 500 dataset spanning 1996-2023. This project will test your ability to extract meaningful insights from real-world business data and communicate findings effectively.

## Dataset
- **File**: `Fortune 500 Companies.csv`
- **Time Period**: 1996-2023
- **Key Variables**: Company rankings, revenue, profit, employees, market value, industry sectors, geographic locations

## Project Requirements

### Part 1: Comprehensive EDA (40% of grade)
Create a Google Colab notebook that performs systematic exploratory data analysis following professional data science practices.

**Required Components:**
1. **Dataset Overview**
   - Load data and display shape, memory usage, column types
   - Identify numerical vs categorical variables
   - Report temporal coverage and data dimensions

2. **Data Quality Assessment**
   - Analyze missing values (counts and percentages)
   - Check for duplicate rows
   - Verify data consistency (impossible values, range checks)
   - **Fix sector data quality issue**: The `sector` column has poor coverage (~32% populated) while `industry` column is complete. Create a mapping from industry to sector using available data:
     ```python
     # Create industry-to-sector mapping from non-null entries
     i2s = df[['industry','sector']].dropna().set_index('industry')['sector'].to_dict()
     # Apply mapping to fill missing sectors
     df['sector'] = df['industry'].map(i2s)
     # This should improve sector coverage from ~4,500 to ~12,800 non-null values
     ```
   - Document remaining data quality issues after cleaning
   - Report on the effectiveness of the sector imputation
    - After applying the industry-to-sector mapping, some industries may still lack sector assignments (those that never had a sector value in the original data)
    - Document which industries couldn't be mapped to sectors
    - Consider whether to exclude these unmapped records from sector-based analyses or create an "Unknown" category
    - Verify the mapping makes business sense (spot-check several industry-sector pairs)
    - This cleaning step is crucial because many analyses (like profit margin distribution by sector in Part 2) require the sector variable. Without this fix, you'd lose ~70% of your data when filtering for non-null sectors.

3. **Univariate Analysis**
   - Summary statistics for all numerical variables
   - Distribution analysis including skewness and kurtosis
   - Frequency tables for categorical variables
   - Identify top categories in key dimensions

4. **Distribution & Outlier Detection**
   - Calculate quartiles and IQR for key financial metrics
   - Identify outliers using IQR method
   - Test for normality (Shapiro-Wilk test)
   - Document distribution characteristics

5. **Bivariate Analysis**
   - Correlation matrix for numerical variables
   - Identify strong correlations (|r| > 0.7)
   - Analyze relationships between categorical and numerical variables
   - Industry-based financial metric comparisons

6. **Time Series Analysis**
   - Year-over-year trend analysis
   - Calculate growth rates and changes
   - Identify companies with consistent Fortune 500 presence
   - Document temporal patterns

7. **Key Insights Summary**
   - Synthesize findings into actionable insights
   - Provide data quality recommendations
   - Suggest next steps for analysis

### Part 2: Statistical Visualizations (30% of grade)
Continue in your notebook with publication-quality charts.

**Required Visualizations (minimum 6):**
1. Revenue trends over time (line plot with mean/median)
2. Industry distribution (horizontal bar chart, top 15)
3. Geographic distribution by state (bar chart, top 10)
4. Top companies by recent revenue (2020-2023 average)
5. Financial metrics correlation heatmap
6. Profit margin distribution by sector (box plots)

**Advanced Visualizations (choose at least 2):**
- Company growth trajectories
- Employee vs revenue relationship scatter plot
- Ranking volatility analysis
- Market cap to revenue ratio distribution

### Part 3: Regression Analysis (30% of grade)
Develop a regression analysis examining the relationship between company size and revenue.

**Required Analysis:**
1. **Overall Linear Regression**
   - Model revenue as a function of employees
   - Calculate R-squared, correlation coefficient
   - Compute standard errors and confidence intervals
   - Perform hypothesis testing (t-statistics, p-values)

2. **Year-by-Year Analysis**
   - Fit separate models for each year (minimum 10 observations)
   - Track parameter evolution over time
   - Identify trends in slope and intercept changes

3. **Parameter Evolution**
   - Analyze how regression coefficients change over time
   - Calculate trends in model fit (R-squared evolution)
   - Identify best/worst predictive years

4. **Business Interpretation**
   - Translate statistical findings into business insights
   - Discuss implications of temporal changes
   - Provide actionable recommendations

## Deliverables

### 1. Google Colab Notebook
- Well-organized notebook with clear markdown sections
- Clean, well-commented code
- Functions/classes for code organization where appropriate
- All outputs visible in the notebook

### 2. Presentation (6-9 minutes)
- **Introduction** (30 seconds): Dataset context and objectives
- **Data Quality** (1-2 minutes): Key data characteristics and quality issues
- **Main Findings** (3-4 minutes): Most interesting insights with supporting visualizations
- **Statistical Analysis** (1-2 minutes): Regression results and implications
- **Conclusions** (30 seconds): Key takeaways and recommendations

### 3. Project Management
- Trello board screenshot showing task assignments
- Evidence of equal contribution from all members

## Technical Requirements

### Required Libraries
```python
pandas, numpy, matplotlib, seaborn, scipy, sklearn
```

### Code Quality Standards
- Modular design with functions/classes where appropriate
- Descriptive variable names
- Clear markdown headers separating sections
- Handle edge cases and missing data gracefully
- No hardcoded values - use configuration variables

### Output Format
- Console output should be well-formatted and readable
- Use clear section headers and separators
- Round numbers appropriately for display
- Ensure all visualizations are properly sized and labeled

## Evaluation Criteria

### Technical Implementation (40%)
- Correctness of statistical methods
- Completeness of analysis components
- Code quality and organization
- Appropriate use of data science techniques

### Insights & Interpretation (30%)
- Quality of insights derived from data
- Business relevance of findings
- Depth of analysis
- Critical thinking demonstrated

### Visualization Quality (20%)
- Chart clarity and aesthetics
- Appropriate chart type selection
- Effective use of color and layout
- Professional presentation quality

### Presentation & Communication (10%)
- Clear articulation of findings
- Equal participation from all members
- Time management (6-9 minutes)
- Engaging delivery

## Important Notes

1. **Group Work**: Follow the group project guidelines posted separately. Each member must contribute equally and present.

2. **Original Work**: Your code must be original and specifically address this project's requirements. Generic EDA scripts or unmodified AI-generated code will receive 0%.

3. **Data Handling**: The dataset may contain missing values and outliers. Your analysis should handle these appropriately and document your approach.

4. **Reproducibility**: Ensure your notebook can be run by others with only the CSV file and standard Python libraries.

5. **Professional Standards**: This project simulates a real-world data analysis task. Approach it as if presenting to business stakeholders.

## Tips for Success
- Start with data quality assessment before diving into analysis
- Create reusable functions for common operations
- Test your code with data subsets first
- Focus on insights that would interest business decision-makers
- Practice your presentation to ensure smooth delivery within time limits
- Use markdown cells to explain your thought process and findings

Remember: The goal is not just to run statistical tests, but to tell a compelling data story about Fortune 500 companies over the past 2-3 decades.
