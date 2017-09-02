# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Unit Project 2: Exploratory Analysis
DS | Unit Project 2

## PROMPT

In this project, you will implement the exploratory analysis plan developed in Project 1. This will lay the groundwork for our first modelling exercise in Project 3.

Before completing an analysis, it is critical to understand your data. You will need to identify all the biases and variables in your model in order to accurately assess the strengths and limitations of your analysis and predictions.

Following these steps will help you better understand your dataset.

**Goal:** A Jupyter notebook that provides a dataset overview with visualisations and statistical analysis.

---

## DELIVERABLES

### Jupyter Notebook Exploratory Analysis

- **Requirements:**
  - Read in your dataset, determine how many samples are present and identify any missing data
  - Create a table of descriptive statistics for each of the variables (n, mean, median, standard deviation)
  - Describe the distributions of your data
  - Plot box plots for each variable
  - Create a covariance matrix
  - Determine any issues or limitations, based on your exploratory analysis

- **Bonus:**
    - Replace missing values using the median replacement method
    - Log transform data to meet normality requirements
    - Advanced Option: Replace missing values using multiple imputation methods

- **Submission:**
    - by 14/02

---

## TIMELINE

| Deadline | Deliverable| Description |
|:-:|---|---|
| Lesson 5 | Project 2 | Exploratory Data Analysis |

---

## EVALUATION

Your project will be assessed using the following standards:

1. Parse the Data

### Rubric: [Click here for the complete rubric](./project2-rubric.md).

Requirements for these standards will be assessed using the scale below:

    Score | Expectations
    ----- | ------------
    **0** | _Incomplete._
    **1** | _Does not meet expectations._
    **2** | _Meets expectations, good job!_
    **3** | _Exceeds expectations, you wonderful creature, you!_

While your total score is a helpful gauge of whether you have met overall project goals, **specific scores are more important** since they'll show you where to focus your efforts in the future!

---

## RESOURCES

### Dataset
We will be using the same dataset as UCLA's Logistic Regression in R tutorial to explore logistic regression in Python, as explained in [yhat's blog](http://blog.yhat.com/posts/logistic-regression-and-python.html). This is an excellent resource for using logistic regression and summary statistics to explore a relevant dataset. Our goal will be to identify the various factors that may influence admission into graduate school. It contains four variables: `admit`, `gre`, `gpa` and `rank`.

- `admit` is a binary variable. It indicates whether or not a candidate was admitted (admit=1) or not (admit=0)
- `gre` is GRE score
- `gpa` stands for Grade Point Average
- `rank` is the rank of an applicant's undergraduate alma mater, with 1 being the highest and 4 as the lowest

Dataset: [admissions.csv](../../../data/admissions.csv)

### Starter code
For this project, we will be using a Jupyter notebook. This notebook will use `matplotlib` for plotting and visualising our data. This type of visualisation is handy for prototyping and quick data analysis. We will discuss more advanced data visualisations for disseminating your work.

- Open the [starter code instructions](./starter/project2-starter.ipynb) in a Jupyter notebook.

### Suggestions for Getting Started

- Read in your dataset
- Try out a few pandas commands for describing your data:

        df['dataframeName'].describe(),
        df['columnName'].sum(),
        df['columnName'].mean(),
        df['columnName'].count(),
        df['columnName'].skew(),
        df.corr()

- **Read the docs for Pandas.** Most of the time, there is a tutorial that you can follow, but not alwaysand learning to read documentation is crucial to your success as a data scientist.

### Past Projects
Look at some sample notebooks for an example of the types of visualisations you can use in your notebook.
- [Example Notebook](https://github.com/justmarkham/DAT8/blob/master/notebooks/05_pandas_visualization.ipynb)

### Additional Links
- [Pandas Docs](http://pandas.pydata.org/pandas-docs/stable/)
- [Useful Pandas Snippets](https://gist.github.com/bsweger/e5817488d161f37dcbd2)