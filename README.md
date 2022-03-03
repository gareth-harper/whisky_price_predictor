# Identifying Value For Money In The World Of Whisky!

<p align="center" width="100%">
  <img src="images/whisky_image.png">
</p>

### 1.	Overview
This capstone project was completed as part of the General Assembly Data Science Immersive bootcamp. The purpose was to investigate the factors affecting whisky prices, to make predictions based on the data, and to identify opportunities following exploration and modeling of the data.

### 2.	Hypothesis
My aim was to help whisky buyers make better informed decisions when purchasing whisky. Consider the following formula:

$$ Value = \frac{Predicted Price}{Actual Price} $$

My hypotheses are therefore:
* Can a regression model be developed to accurately predict the price of whisky given various features of the whisky such as age, vintage, country of origin, alcohol content etc.?
* Can I identify whiskies that provide the best value for money?

### 3.	Business Problem
Whiskies with a Value greater than 1 represent those that are underpriced, and the higher the Value the more underpriced the whisky is. This could have a significant impact on large whisky purchasers as they can buy better quality whiskies at lower prices. This can either be used to increase profit margins, increase customer satisfaction (by offering better value for money), or some combination of the two depending on the business' requirements. This problem can be generalized to any retail business involved in the buying and selling of goods.

### 4.	Data Acquisition
The information used in this project was obtained from Hard To Find Whisky (htfw.com), a retail website selling over 6,500 different whiskies. I performed a web scrape of the data over multiple csv files that were then appended together and loaded into a single dataframe.

Following cleaning (described in next chapter) the following features were obtained:

| Feature | Explanation |
| :- | :- |
| Distillery | The company producing the whisky. |
| Series | The edition. Typically, a single distillery will produce numerous whiskies. |
| Cask Strength | A term used to describe a whisky that has not been substantially diluted after its storage in a cask. |
| Cask Type	| Not only refers to the wood used for the cask, but whether the cask is new or previously used. |
| Single Cask | Whether the whisky is drawn from one individual cask. |
| Packaging | How the item is packaged. |
| Bottler | Whether the whisky is bottled at the distillery it is made, or at an independent bottler. |
| Country | The country in which the whisky is produced. |
| Stopper | How the whisky bottle is sealed. |
| Description | A description of the whisky including any tasting notes or special points of interest. |
| Bottle Size | The volume of the bottle measured in centilitres (100cL = 1L). |
| Vintage | The year the distilling process commenced. |
| Year Bottled | The year the whisky was bottled. |
| Age | The number of years the whisky spent distilling in the cask. |
| Alcohol content | Alcohol is contained in a given volume. |
| Price | The whisky price – my target variable! |





# Classifying Salaries of Data-Related Jobs

### Introduction

One of my projects for the General Assembly Data Science Immersive course was to scrape job listings from a job aggregation website and apply machine learning algorithms to predict salaries for Data Science related roles in the United Kingdom.
This project was completed in January 2022.

### Goals

The goals of the project are summarized as follows:
1. Determine the factors that are most important in predicting salary for the roles chosen.
2. Scrape data from a job aggregation tool in order to obtain necessary data.
3. To predict salary the most appropriate approach would be a regression model. Here, instead, we just want to estimate which factors lead to high or low salary and work with a classification model.

As we only have two classes (whether the salary is 'low' or 'high'), the baseline model accuracy is 50% (Guessing whether the salary is in either category without any modeling would ensure you are correct half the time, on average).

### Scraping the Data

Job aggregation website Indeed.com was scraped using BeautifulSoup as the website is a simple text page where you can easily find relevant entries. It was possible to identify a number of key tags for information which might be helpful to scrape such as job location, company name, job title, and salary.

I limited my search to job postings in the UK only, including cities across England, Scotland, Wales and Northern Ireland.

### Data Cleaning and EDA

Once the data was collected, it was cleaned using various techniques learned throughout the course. Although I was initially able to scrape nearly 60,000 data points, after cleaning I was left with just more than 1,300. This was largely due to many duplicated data points, and entries with missing or irrelevant information among other factors. The number of useable data points was deemed sufficient to build predictive models to complete the project.

<br>
<p align="center" width="100%">
<kbd><img src="images/01 Salary Distribution Histogram.png" width="700"  /></kbd>
</p>

<p align="center"><i><sub>Salary Distribution of Data-Related Jobs. UK. January 2022.</sub></i></p>
<br>
