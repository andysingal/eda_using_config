# eda_using_config
Books: 
1. Machine Learning Bookcamp - https://github.com/alexeygrigorev/mlbookcamp-code
2. Hands-On Exploratory Data Analysis with Python - https://github.com/PacktPublishing/Hands-on-Exploratory-Data-Analysis-with-Python/tree/master
3. Hands-On Data Analysis with Pandas - Second Edition - https://github.com/stefmolin/Hands-On-Data-Analysis-with-Pandas-2nd-edition/tree/master


![11](https://github.com/andysingal/eda_using_config/blob/main/images/Screenshot%202023-07-17%20at%201.55.56%20PM.png)

Ask a Question.
Asking good questions lies at the heart of data science, and recognizing different kinds of questions guides us in our analyses. We cover four categories of questions: descriptive, exploratory, inferential, and predictive. For example, “How have house prices changed over time?” is descriptive in nature, whereas “Which aspects of houses are related to sale price?” is exploratory. Narrowing down a broad question into one that can be answered with data is a key element of this first stage in the lifecycle. It can involve consulting the people participating in a study, figuring out how to measure something, and designing data collection protocols. A clear and focused research question helps us determine the data we need, the patterns to look for, and how to interpret results. It can also help us refine our question, recognize the type of question being asked, and plan the data collection phase of the lifecycle.

Obtain Data.
When data are expensive and hard to gather and when our aim is to generalize from the data to the world, we aim to define precise protocols for collecting the data. Other times, data are cheap and easily accessed. This is especially true for online data sources. For example, Twitter lets people quickly download millions of data points. When data are plentiful, we can start an analysis by obtaining data, exploring it, and then honing a research question. In both situations, most data have missing or unusual values and other anomalies that we need to account for. No matter the source, we need to check the data quality. Considering the scope of the data is equally important; for example, we identify how representative the data are and look for potential sources of bias in the collection process. These considerations help us determine how much faith we can place in our findings. And, typically, we must manipulate the data before we can analyze it more formally. We may need to modify structure, clean data values, and transform measurements to prepare for analysis.

Understand the Data.
After obtaining and preparing data, we want to carefully examine them, and exploratory data analysis is often key. In our explorations we make plots to uncover interesting patterns and summarize the data visually. We also continue to look for problems with the data. As we search for patterns and trends, we use summary statistics and build statistical models, like linear and logistic regression. In our experience, this stage of the lifecycle is highly iterative. Understanding the data can also lead us back to earlier stages in the data science lifecycle. We may find that we need to modify or redo the data cleaning and manipulation, acquire more data to supplement our analysis, or refine our research question given the limitations of the data. The descriptive and exploratory analyses that we carry out in this stage may adequately answer our question, or, we may need to go on to the next stage in order to make generalizations beyond our data.

Understand the World.
When our goals are purely descriptive or exploratory, then the analysis ends at the Understand the Data stage of the lifecycle. At other times, we aim to quantify how well the trends we find generalize beyond our data. We may want to use a model that we have fitted to our data to make inferences about the world or give predictions for future observations. To draw inferences from a sample to a population, we use statistical techniques like A/B testing and confidence intervals. And to make predictions for future observations, we create prediction intervals and use test/train splits of the data.



Data collection
Data collection is the natural first step for any data analysis—we can't analyze data we don't have. In reality, our analysis can begin even before we have the data. When we decide what we want to investigate or analyze, we have to think about what kind of data we can collect that will be useful for our analysis.

- Web scraping to extract data from a website's HTML (often with Python packages such as selenium, requests, scrapy, and beautifulsoup)
- Application programming interfaces (APIs) for web services from which we can collect data with HTTP requests (perhaps using cURL or the requests Python package)
- Databases (data can be extracted with SQL or another database-querying language)
- Internet resources that provide data for download, such as government websites or Yahoo! Finance
- Log files

Data wrangling
Data wrangling is the process of preparing the data and getting it into a format that can be used for analysis. The unfortunate reality of data is that it is often dirty, meaning that it requires cleaning (preparation) before it can be used. The following are some issues we may encounter with our data:

- Human errors: Data is recorded (or even collected) incorrectly, such as putting 100 instead of 1000, or typos. In addition, there may be multiple versions of the same entry recorded, such as New York City, NYC, and nyc.
- Computer error: Perhaps we weren't recording entries for a while (missing data).
- Unexpected values: Maybe whoever was recording the data decided to use a question mark for a missing value in a numeric column, so now all the entries in the column will be treated as text instead of numeric values.
- Incomplete information: Think of a survey with optional questions; not everyone will answer them, so we will have missing data, but not due to computer or human error.
- Resolution: The data may have been collected per second, while we need hourly data for our analysis.
- Relevance of the fields: Often, data is collected or generated as a product of some process rather than explicitly for our analysis. In order to get it to a usable state, we will have to clean it up.
- Format of the data: Data may be recorded in a format that isn't conducive to analysis, which will require us to reshape it.
Misconfigurations in the data-recording process: Data coming from sources such as misconfigured trackers and/or webhooks may be missing fields or passed in the wrong order.


EDA and data wrangling shared a box. This is because they are closely tied:

- Data needs to be prepped before EDA.
- Visualizations that are created during EDA may indicate the need for additional data cleaning.
- Data wrangling uses summary statistics to look for potential data issues, while EDA uses them to understand the data. Improper cleaning will distort the findings when we're conducting EDA. In addition, data wrangling skills will be required to get summary statistics across subsets of the data.

Drawing conclusions
After we have collected the data for our analysis, cleaned it up, and performed some thorough EDA, it is time to draw conclusions. This is where we summarize our findings from EDA and decide the next steps:

- Did we notice any patterns or relationships when visualizing the data?
- Does it look like we can make accurate predictions from our data? Does it make sense to move to modeling the data?
Should we handle missing data points? How?
- How is the data distributed?
- Does the data help us answer the questions we have or give insight into the problem we are investigating?
- Do we need to collect new or additional data?


Statistical foundations
When we want to make observations about the data we are analyzing, we often, if not always, turn to statistics in some fashion. The data we have is referred to as the sample, which was observed from (and is a subset of) the population. Two broad categories of statistics are descriptive and inferential statistics. With descriptive statistics, as the name implies, we are looking to describe the sample. Inferential statistics involves using the sample statistics to infer, or deduce, something about the population, such as the underlying distribution.

IMPORTANT NOTE

Sample statistics are used as estimators of the population parameters, meaning that we have to quantify their bias and variance. There is a multitude of methods for this; some will make assumptions on the shape of the distribution (parametric) and others won't (non-parametric). This is all well beyond the scope of this book, but it is good to be aware of.


Sampling
There's an important thing to remember before we attempt any analysis: our sample must be a random sample that is representative of the population. This means that the data must be sampled without bias (for example, if we are asking people whether they like a certain sports team, we can't only ask fans of the team) and that we should have (ideally) members of all distinct groups from the population in our sample (in the sports team example, we can't just ask men).


Descriptive statistics
We will begin our discussion of descriptive statistics with univariate statistics; univariate simply means that these statistics are calculated from one (uni) variable. Everything in this section can be extended to the whole dataset, but the statistics will be calculated per variable we are recording (meaning that if we had 100 observations of speed and distance pairs, we could calculate the averages across the dataset, which would give us the average speed and average distance statistics).

Descriptive statistics are used to describe and/or summarize the data we are working with. We can start our summarization of the data with a measure of central tendency, which describes where most of the data is centered around, and a measure of spread or dispersion, which indicates how far apart values are.
