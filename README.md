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

### 5.	Data Cleaning
Generally, the data required extensive cleaning before it could be used in a meaningful way. Besides fairly standard cleaning operations, some notable cleaning include:
* Series and Description features were subset for Natural Language Processing (NLP),
* Symbols and special characters were removed from all remaining features, and they were converted to appropriate data types,
* Using the relationship Year Bottled = Vintage + Age I was able to impute missing values,
* IterativeImputer was used for remaining missing values for these three features, and
* Outliers were removed using percentiles (values <1% and >99% were removed).

The final dataset comprised 16 features and 5,660 whiskies.

### 6.	Exploratory Data Analysis
The EDA process provided valuable insight into the different features, and the relationships between them.

It was important to understand the distribution of price as this was my intended target variable in the predictive models to come. It was immediately clear that the prices in my data were not normally distributed and were highly skewed to the right. Even after removing outliers, my average whisky price was about £540, with a minimum price of £30 and a maximum price of £10,000. 



