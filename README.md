# Introduction

                 "Sarcasm is the lowest form of with, but the highest form of intelligence"
                                                Oscar Wilde

Sarcasm is a suble linguistic trait, where usually the author states the opposite of what they mean. Detecting Sarcasm requires common sense and contextual knowledge which makes it a difficult problem to address. With the prevalence of sarcasm in tweets and comments online, it has become important to devise algorithms and models to distinguish sarcastic statements from non-sarcastic ones. Here we present a comparative study of various classification algorithms in machine learning used to classify sarcastic & non-sarcastic tweets with some newly devised features like passive-aggressiveness and emoji sentiment flip for better accuracy.

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


The table below shows the F1 scores of the classifiers when each feature is used individually


![image](https://user-images.githubusercontent.com/31497107/40632326-83d09e30-629a-11e8-965d-dcb8b774a382.png)


Accuracy for different feature categories

![image](https://user-images.githubusercontent.com/31497107/40632333-9f76f4e0-629a-11e8-833f-762049f0ace4.png)

Incrementally adding feature categories

![image](https://user-images.githubusercontent.com/31497107/40632345-b851f06e-629a-11e8-9963-999ae3710c51.png)





