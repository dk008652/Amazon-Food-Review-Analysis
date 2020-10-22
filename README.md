# Amazon-Food-Review-Analysis

Amazon Food Review Analysis(Sentiment Analysis):
Amazon fine food review analysis is a problem related to text processing where the task is to find whether a review of a product is positive or negative. To start with this task, download the dataset kaggle.

This dataset consist 10 attributes.
{$name all attribute}

Data Cleaning and Text Preprocessing: We used the "score" attribute as a deciding factor if given review depicts positive or negative sentiment. The score attribute ranges between [0, 5] where value of 3 represents neutral sentiment so we remove all documents(review/row) of score value of 3 and any score value below 3 mapped as negative and above 3 as positive review.

Dataset might contain duplicate reviews, to get unbiased results those reviews to be removed keeping only the first one.
Attribute Helpfullnumerator tells how many people found this review useful and Helpfulldenominator tells both how many found it useful or how many not.
Documents which have Helpfullnumerator value greater than Helpfulldenominator to be removed as these reviews are considered as fake.
 As a part of data cleaning we have to clean the reviews for better processing and finally getting better results. So HTML tags, any punctuation and alphanumeric words present in reviews are removed. To deal with HTML tags, punctuation, or alphanumeric words, regular expression(re) library is used.

Once the data cleaning part is completed we perform text preprocessing tasks like stemming and removing stopwords. To be specific for stemming, porter stemming is used rather than snowball as it gives better results than later one.
Stopwords are defined by the words which occur most frequently in documents. Ex. a, an, the, to, for, is, are, in, etc. Any word in a document with length 2 or less are also removed as these words do not contribute much in improving the result but improve the time complexity of the task.
Text Vectorization: Once preprocessing is completed documents are converted into vectors by various available methods viz. bag of words(count vectorizer), tfidf(term frequency inverse document frequency) or word2vec.

Bag of Words: This method counts the number of times a word appears in a document. Method of unigram, bi-gram or n-gram can also be used for experimental purposes to decide which method gives best accuracy on test data. Bag of words gives more importance to words which appear most frequently in a document but it does not correlate the appearance of words in other documents like tfidf does.

Tfidf(Term Frequency Inverse Document Frequency): This method gives some weighting factor to each word which tells how important a word in the corpus is. Now the word which appears more no of times in a document but appears less in other documents are given a high weighting factor. A word which appears in most of the documents with high frequency is given very less importance or less weighing factor (or less tfidf value).

TF: (No of times a word appears in a document) / (Total no of words in a document).
IDF(Inverse Document Frequency): (Total No of documents) / (No of documents where a particular word present(word for which we calculate tfidf)).

TF-IDF  =  TF  *  log( IDF )

Method used for classification and corresponding results.
KNN: finding best performing hyperparameter value(K): Accuracy 85%.
NB: Hyperparameter(alpha) = 			      Accuracy 87%.
LR: Hyperparameter(lambda) = 			      Accuracy 92%.
SVM: Hyperparameter(C = 1 / lambda) = 		      Accuracy 92%.

Any hyperparameter which gives good results on validation dataset, is used to measure the performance of the model on test data.
Performance Metrics which were also used along accuracy: F1, Recall, Precision.










 


