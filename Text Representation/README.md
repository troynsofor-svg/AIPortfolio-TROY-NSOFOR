# Problem Statement:
While computers perform (or function) on numerical data, the main problem the project solves is how to proficiently change raw text into numerical descriptions that algorithms could explain.

Throughout the notebook, the problem describes and investigates different techniques for this transformation, beginning from fundamental techniques such as preprocessing and Bag of Words (BOW), then to more advanced weighted descriptions such as TF-IDF and N-grams, and lastly delving into dense representations like word embeddings. The ultimate goal is to utilize these descriptions to real-world tasks, like creating a text classification system for sentiment analysis, and to comprehend the trade-offs and moral considerations included in all the approaches.

# Approach:
I solved it by converting human language (text) into a numerical format that machine learning algorithms could comprehend and process. I solved this by investigating and executing some text representation techniques and algorithms.

Here's a breakdown of each:

Text Preprocessing: I began by cleaning the text through steps such as lowercasing, eliminating punctuation, tokenization, eliminating stop words, and stemming.

Sparse Representations:
Bag of Words (BOW): I executed this to describe text as a count of word occurrences, crucially losing word order but catching word frequency.

TF-IDF (Term Frequency-Inverse Document Frequency): This technique designated weights to words derived from their frequency in a document and their rarity over the whole dataset, emphasizing critical terms.

N-grams: I investigated n-grams (sequences of words such as bigrams and trigrams) to catch several word orders and context that BOW and fundamental TF-IDF may skip.

Dense Representations:

Word Embeddings (GloVe): I applied pre-trained word embeddings to describe words as dense vectors, catching semantic relationships and enabling for word arithmetic.

Applications and Analysis:

Cosine Similarity: Used to calculate the similarity between text embeddings produced by BOW and TF-IDF.

Text Classification (Multinomial Naive Bayes): I've created a sentiment classification system using this algorithm, by comparing its performance with various vectorizations.

Feature Importance Analysis: This was used for comprehending which words contributed the most to the classification choices.

# Results
Here's the breakdown of the results, including metrics, accuracy, and performance:

Overall Classification Accuracy:

All three techniques, Bag of Words (BOW), TF-IDF, and N-grams, accomplished the same accuracy of 0.667 (or 66.7%).

Feature Comparison:

BOW: Applied 1000 features.
TF-IDF: Applied 1000 features.
N-grams: Applied 1000 features (with ngram_range=(1, 2)).

Detailed Performance Metrics (for every method, as they yielded the same results):

# Negative Class (Label 0):
Precision: 0.62 (this indicates that 62% of the predictions for the negative class were accurate).
Recall: 0.87 (this indicates that the model accurately spotted 87% of every negative review).
F1-Score: 0.72 (this is the harmonic mean of precision and recall).

# Positive Class (Label 1):
Precision: 0.78 (indicating that 78% of the predictions for the positive class were accurate).
Recall: 0.47 (indicating that the model accurately spotted 47% of every actual positive review).
F1-Score: 0.58 (58%).

# Key Observations:
All of the text representation techniques performed similarly in terms of overall accuracy and class-specific metrics on the specific dataset and classification task.
The model demonstrated a higher recall for negative reviews (0.87) but a lower recall for positive reviews (0.47). On the other hand, its precision for positive reviews (0.78) was higher than the precision for negative reviews (0.62).
The feature analysis for TF-IDF spotted words such as 'francie', 'homer', and 'great' as the top positive features, and 'girls', 'prinze', and 'ho' as the top negative features.

# Key Findings
I learned about the Common Preprocessing Steps (Lowercasing, Removing punctuation, Tokenization, Removing stop words, and Stemming).

# Technologies Used:
(Libraries): Scikit-Learn, Matplotlib, Seaborn, Gensim, Wordcloud, NLTK, Numpy, Pandas


(Tools): NLTK (Natural Language Toolkit), Gensim, Scikit-Learn, Pandas, Matplotlib and Seaborn


(Frameworks): NLTK, Gensim, Scikit-Learn, Pandas, Matplotlib, Seaborn, collections (Counter, defaultdict), re (Regular Expression), math, and itertools (combinations)

# How to Run:
1. Open Google Colab
2. Go to and click on File (Open Notebook)
3. Click on L04_Text_Representation_ITAI_2373_Lab-1.ipynb
