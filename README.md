**EXECUTIVE SUMMARY: INEED WEBSCRAPE AND ANALYSIS**

  This projects goal was to scrape job postings related to the DataScience field from
indeed.com.au and analyze their components in an attempt to understand the key elements
that constitute different classes of: salary, and title.
Web scraping is a process in which a data set is created from various elements of a
website. In this instance this was accomplished using a selenium web driver(a tool for
clicking through webpages and collecting html metadata). The results of this scrape were
then cleaned with a python library called beautiful soup. This library allows us to convert the
html metadata into its root text and elements. We were interested in data relating to each
job postings title, description and salary information. This data was scraped and input into a
pandas dataframe for further processing and analysis.

  Once we had a cleaned data frame with each row made up of a unique job posting
and columns representing features of that job (title, salary, description) we moved on to
modeling. Our initial hypothesis is that certain key words in a job description will indicate
higher salaries. To test this we split our salary information into two classes: high and low.
The split threshold was determined by taking the median of the salaries. We then trained a
variety of machine learning models on numerical representations of the job descriptions.
Unlike the human brain, machines are not yet capable of processing language and learning
words in an abstract way. By creating numerical representations of words we convert words
to a syntax that machines understand which allows us to apply complex statistical
evaluations and machine learning models to them.

  The outputs of our models which we analysed were their coefficients and feature
weights. These outputs tell us which of our features (in our case words and phrases that
occur in the descriptions) impacted the machine's decision as to which salary class to assign
a job it had not yet encountered. By examining the coefs with the most impact on the
decision and cross referencing it with our knowledge of what traditionally entails high
salaries, we can provide insights that determine high salary jobs. In our case we found that
traditional keywords such as “leadership”, “Engineering”,” and '”Senior” had large impacts on
our classification. We also observed more domain specific keywords were important in
determining high salary (“data science”, “bigdata”, “data engineer”).

  A similar process was implemented to determine what features constitute a job title of
“data scientist”. There is a lot of confusion as to what exactly determines titles in the various
fields relating to Data. Our model provided useful insights for keywords that indicate a title of
“Data Scientist”. Traditionally data analysts do not use machine learning and programming
languages. This is reflected in our models results. Some of the top keywords for data
scientists were : “deep learning, “machine learning”, and “programming languages”.
In the future we could use our model to better classify job postings by title and to
estimate salary ranges for postings that lack them. The model is limited by the size of the
data set and would be improved by training on a much larger sample. There is also a
concern of data leakage as many of the descriptions contain salary information and
keywords directly related to the title. This leakage could be addressed going forward by a
more refined cleaning of job descriptions.
