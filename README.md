# Twitter Sentiment Analysis
![twitter-logo-on-distressed-background-DG81YC](https://user-images.githubusercontent.com/104419109/187983202-a35ee19e-c806-451c-a701-a3a0a1112185.jpg)
# Contributors: 
- Daniel Oselu     
- John Kanoru    
- Roseline Maina
- Angela Cheruto
- Benson Muriu
- Irene Maina
- Nelly Ng'eno
- Janet Gachoki

# Overview
This project uses Multinomial Naive Bayes to predict the sentiment of tweets towards Apple and Google products using data obtained from CrowdFlower found on [data.world](https://data.world/crowdflower/brands-and-product-emotions)

# Project Summary
In a world where technology startups are common, consumer perception of a brand can provide us with valuable information about their purchasing behavior and, in turn,
the financial performance of the business that produces them.In order to determine which brands to research further for potential investment, Longview techventures
wants a generalizable model to measure sentiment across various brands. 

Longview Techventures is only interested in whether consumers feel positive about the brand and
have hired us to help them develop a predictive model that keeps track of recent tweets about tech products so they can make smart investment choices.

# Data
This project primarily uses data gathered from CrowdFlower which can be found on [data.world](https://data.world/crowdflower/brands-and-product-emotions) or in the data 
folder in this project's GitHub repository. The data contains 9203 datapoints containing columns containing the full tweet, a column identifying what brand or product
the tweet was about if any, and a final column indicating whether it has any emotion positive or negative or none towards the brand or product. The products found by 
searching keywords were all either Apple or Google products. The data was gathered in 2013 and all the tweets came from the #SXSW tag.

The dataset significant class imbalance  with most of the data (61%) being marked as no emotion and only 6% of the data expressing negative views towards the brand or 
product.

## Data Preparation and Exploration 
Duplicated rows were dropped and rows that had missing values were either dropped or replaced with Undefined for those in the product column.

Links, punctuation and stopwords were removed from the data prior to modeling. '#' was removed from twitter hashtags, but the content of the tag was kept. The data was small enough that lemmatization was usable to reduce the dimensionality of the data.

To get a general idea of both the word frequencies and product sentiments several data visualizations were made:
![wordcloud](https://user-images.githubusercontent.com/104419109/188010279-36094366-e957-4b71-b7d7-d41952cc18ce.png)
![image](https://user-images.githubusercontent.com/104419109/188012597-c20e7e07-974f-49bf-9b4e-989fef4b5395.png)
![image](https://user-images.githubusercontent.com/104419109/188011760-b69f0247-5ded-48bb-b939-15f4e73c8ac1.png)
![image](https://user-images.githubusercontent.com/104419109/188011490-aea06446-15cb-4b43-841f-21c8e3a5d70f.png)

# Modelling
The sentiment column was used as the target variable and the tweet column was used as predictor variable. Initial modeling efforts showed that  our models suffers from 
the class imbalance. 
Tradition classification algorithms: Naive Bayes, Random Forest and Logistic Regression were tested as well as the more sophisticated LSTM network. Despite most of the 
traditional classification models suffering from training overfit, Multinomial Naive Bayes improves on the overfit slightly but the accuracy is limited to 74%.
![image](https://user-images.githubusercontent.com/104419109/188016952-a1f525c0-b5eb-4c51-91c1-da262be508f2.png)

# Future Improvements
Testing additional vectorizers and models may improve on these results. Pre-trained vectorizers such as Google's Word2Vec, Stanford's GloVe, and SpaCy may produce 
better results.

Scrape for more data to possibly balance the four classes, especially negative and positive tweets.

Build a binary class focus on only the positive and negative comments then add the neutral comments later on.

Obtain more tweet-data from other tech companies, particularly small startups and PR companies.

# For More Information
Please review our full analysis in our Jupyter Notebook or our presentation.

# Repository Structure
├── data

├── images

├── README.md

├── Tweets_sentiment_analysis.ipynb

└── Twitter_Sentiment_Analysis_Notebook.pdf




