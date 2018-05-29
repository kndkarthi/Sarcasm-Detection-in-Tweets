# Introduction

                 "Sarcasm is the lowest form of wit, but the highest form of intelligence"
                                                Oscar Wilde

Sarcasm is a subtle linguistic trait, where usually the author states the opposite of what they mean. Detecting Sarcasm requires common sense and contextual knowledge which makes it a difficult problem to address. With the prevalence of sarcasm in tweets and comments online, it has become important to devise algorithms and models to distinguish sarcastic statements from non-sarcastic ones. Here we present a comparative study of various classification algorithms in machine learning used to classify sarcastic & non-sarcastic tweets with some newly devised features like passive-aggressiveness and emoji sentiment flip for better accuracy.

Classification algorithms used:

1. Naive Bayes
2. Logistic Regression
3. Support Vector Machines
4. Random Forest
5. Neural Networks
6. Decision Trees

# Methodology

Data collection and preprocessing was major step in the project where the following techniques were used:
1. We remove tweets that start with ‘@User’ as they are retweets and do not provide information about the original tweet which can potentially be sarcastic.
2. We limit our study to English tweets as more resources are available for the processing of text in English language.
3. In our project, we integrate emojis as a feature to detect sarcasm or at least a change in polarity.
4. User mentions and URLs are removed from the tweet as they are not indicative of the original nature of the tweet.
5. We remove duplicates that may result from retweets.

Feature Engineering:

In this project we use 21 special features along with usual unigrams and bigrams for classification. These 21 features were divided in to 4 categories:

1. Text expression-based features
2. Emotion-based features
3. Familiarity-based features
4. Contrast-based features

# Results and Conclusion

The table below shows the F1 scores of the classifiers when each feature is used individually

![image](https://user-images.githubusercontent.com/31497107/40632326-83d09e30-629a-11e8-965d-dcb8b774a382.png)

Accuracy for different feature categories

![image](https://user-images.githubusercontent.com/31497107/40632333-9f76f4e0-629a-11e8-833f-762049f0ace4.png)

Incrementally adding feature categories

![image](https://user-images.githubusercontent.com/31497107/40632345-b851f06e-629a-11e8-9963-999ae3710c51.png)


From the table below, we notice that the context based features performed worse than random or only a slightly better classifier. But emotion based features and contrast based features performed better than the rest. According to the accuracies and F1 Scores in Figures 1-2, emotion based features outperformed the other categories. We notice that in some case, having a single feature exceeded the performance of the category itself (e.g. Negative Word Count in Support Vector Machine). Also contrast-based features give consistent results for all the classifiers. We also notice that independently the features do not give very good accuracy but when we use them together they give good accuracy category-wise. Based on our results, we notice that since the emotion based features (six features) dominated the F1 score metric, we fixed these features as our base feature set and then started adding feature one category at a time. Contrary to what’s expected, we noticed that even when having the full set of features, there will be a given combination of different features (that doesn’t include the total 21 features) that will outperform the full set. This can be attributed to the fact that some of the tweets might not have all the features that we test for. 

Sarcasm Detection requires unique feature engineering techniques by considering contextual characteristics. Our study shows that just increase in the number of features is not enough to achieve high accuracy, but selection of the right set of features is the basis of successful classification. These set of features will change with the change in dataset and data source. Sarcastic and non-sarcastic comments have different linguistic characteristics, hence the model needs to be trained with a balanced dataset. An unbalanced dataset may classify with higher accuracy but will produce low F1-score as the class with higher number of samples dominates the model training. Sarcasm is a behavioural trait and requires contextual analysis, hence expanding the feature space with author background and topic understanding will be an interesting area of future research. Additionally, previous tweet history from the same authors might lead to a more accurate contextual analysis.

# Code Details

To run the code follow these steps:

1. Get the repository
2. Run feature_extraction.py to generate a feature_list.csv with all the features
3. Run necessary functions from utils.py
4. Run Classifiers.py to get the results



