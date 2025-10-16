# Retail Sales Trend Analysis - Hackathon

This hackathon project aims to explore a retail sales dataset. The purpose is to exercise ETL skills, the creation of visualisations, as well as of overall project management.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Dataset Content
* The dataset, obtained from Kaggle, is comprised of 3 different CSV files:
    - Stores (577 bytes): anonymized information about the 45 stores, indicating the type and size of store.
    - Features (600 kilobytes): additional data related to the store, department, and regional activity for the given dates.
    - Sales (13.3 megabytes): historical sales data, covering the period 2010-02-05 to 2012-11-01.

## Business Requirements
* The main aims are:
    - Identify sales trends
    - Evaluate the impact of promotional markdowns on sales
    - Provide useful visualisations


## Hypothesis and how to validate?
* The project's aim is mostly exploratory in nature, there is no specific hypothesis to be tested. However, there are several expectations needing confirmation:
    1. There is a significant difference in sales between Holiday and non Holiday weeks;
    1. MarkDowns affect sales significantly;
    2. Unemployment and CPI influence sales. 

## Project Plan
* High-level project layout:
    1. Extraction
    2. Preliminary exploration
    3. Cleaning
    4. Transformation and feature engineering
    5. Exploratory data analysis + visualisations

* Data was 'collected' (i.e. downloaded) in CSV format. Data from each CSV file was then extracted as Pandas dataframe, subsequently merged into a unitary dataframe. It was kept in dataframe format for the remainder of the project.
* Pandas dataframe format was chosen for it versatility: as the project required extensive manipulation of the data, Pandas' facilitation of data wrangling tasks made it the ideal framework.

## The rationale to map the business requirements to the Data Visualisations
* Understanding the target variable - Weekly_Sales. Exploration always starts with the target variable. Since this is a continuous variables, looking into the distribution is a crucial step. 
    - Fig1 provides a histogram of the distribution, prior to any tampering.
    - Fig3 is a histogram for after cleaning.
    - Figs 4 and 5 offer additional visualisations of its distribution.

* Sale trends were investigated at a high-level (i.e. store level over the whole period).
    - Fig12 offers an interactive view of the overall sales trend.
    - Fig13 explores the differences between high and low performers.

* The effects of Mark Downs were explored using:
    - Fig10, a correlation matrix, shows the relationship (linear) between various features
    - Fig14, a scatterplot, investigates in more detail the effects of the best correlated Mark Down (no. 5) on sales.

## Analysis techniques used
The analysis applied structured data cleaning, transformation, and visualization for retail sales.
* Notable decisions:
    - Negative and anomalous sales were corrected or removed using conditional logic and median imputation.
    - Outliers were addressed via quantile-based capping and log–z-score filtering.
    - MarkDown features were cleaned, capped, and normalized through log transformation and z-score standardization.
    - Temporal trends were explored with interactive Plotly line plots and Seaborn time-series visuals.
    - Correlations and distributional patterns were examined through heatmaps, histograms, and scatterplots.

* Further justification for each step can be found in the project notebook.

## Ethical considerations
* The data was already anonymised, there are no identified ethical issues. 

## Unfixed Bugs
* No unfixed bugs.
* Weaknesses:
    - Comparative analysis does not cover inter-store or inter-department.
    - Trend analysis does not go into detail at department level, or year by year.
    - Only explored linear relationships between the features.
* Improvements:
    - More in-depth statistical analysis of the relationship between Weekly_Sales and the other features.
    - Web-based method of disseminating the visualisations.

## Development Roadmap
* An early challenge was merging the original 3 CSV files. I first needed to establish which is the main table (i.e. where the target variable is), then to understand how to map Features onto Sales (by a combination of Store + Department, rather than Store alone). 

## Findings / Conclusions
1. Sales follows the expected Exponential distribution;
2. There is a noticeable increase in sales during Holiday;
3. High performing stores manage to create big sales spikes during Holidays, whilst low performing ones exhibit a constant level all year round;
4. Between the 4 major holidays (mentioned by the dataset creators), only Christmas and Thanksgiving/Black Friday result in significant trend changes;
5. There are mini spikes in sales at the beginning of each month;
6. The Mark Downs are not very well correlated with sales (the best having a mere 0.17 positive correlation). Suggesting that they do not play a major role. Though, further analysis using statistical tests is required to confirm this.
6. It remains unclear whether Mark Downs increase sales during Holidays (see Fig14).  
7. Unemployment and CPI are (at least linearly) not correlated to sales; 

## Main Data Analysis Libraries
* The following are the main libraries used in the project:
    1. Pandas - create and manipulate dataframes;
    2. Matplotlib - foundation layer for visualisations; 
    3. Seaborn - more advanced and visually pleasing visualisations;
    4. Plotly express - interactive visualisations.

## Credits 

* Data was obtained from Kaggle (https://www.kaggle.com/datasets/manjeetsingh/retaildataset). 
