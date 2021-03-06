# ProcessData.ipynb

This file cleans up and procecess the two tweetset.csv datasets so that they can be imported and used with the machine learning models

processed_1.csv is generated from this file by processing tweetset_1.csv
processed_2.csv is generated from this file by processing tweetset_2.csv

# FeatureExtraction.ipynb

This file creats 8 different NLP vectorizations for 4 different scenarios

The four scenarios are:

1) Training Data and Testing Data come from processed_1.csv (stratified 80/20 split)
2) Training Data and Testing Data come from processed_2.csv (stratified 80/20 split)
3) Training Data is processed_1.csv and Testing Data is processed_2.csv
4) Training Data is processed_2.csv and Testing Data is processed_1.csv

The eight NLP schemes are:

1) Unigrams with frequency counts
2) Unigrams with Tf-idf scores
3) Bigrams with frequency counts
4) Bigrams with Tf-idf scores
5) Reduced Frequency Unigrams
6) Reduced Tf-idf Unigrams
7) Reduced Frequency Bigrams
8) Reduced Tf-idf Bigrams

The unigrams and bigrams are generated with roughly the top 80% most frequently occuring unique features to remove low-occuring features from the data. This should allow the trained models to focus on the most significant features.

The reduced unigrams and bigrams are sparse reductions that are 5% the size of the corresponding NLP vectors.

Warning: Running this entire file and saving every subsequent NLP vector will take up a lot of storage (well over 100 GB). It is recommended that only 8 of the vectorizations corresponding to 1 specific scenario are run and saved at a time. That data should be used to train, evaluate, and save several machine learning models and then should be deleted before starting on another scenario to conserve space.
