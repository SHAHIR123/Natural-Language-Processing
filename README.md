# Natural-Language-Processing
## Create a Classifier for Sentiment Analysis with NLTK

NLTK is the most popular Python package for Natural Language processing, it provides algorithms for importing, cleaning, pre-processing text data in human language and then apply computational linguistics algorithms like sentiment analysis.

### Date Set 

NLTK also includes many easy-to-use datasets in the nltk.corpus package. We are using movie_reviews package for this Project.
In particular in the movie_reviews dataset we have 2000 text files, each of them is a review of a movie, and they are already split in a neg folder for the negative reviews and a pos folder for the positive reviews.

### Tokenize Text in Words

The first step in Natural Language processing is generally to split the text into words, this process might appear simple but it is very tedious to handle all corner cases, see for example all the issues with punctuation we have to solve if we just start with a split on whitespace. nltk has a sophisticated word tokenizer trained on English named punkt.
hen we can use the word_tokenize function to properly tokenize this text.

### Build a bag-of-words model

The simplest model for analyzing text is just to think about text as an unordered collection of words (bag-of-words). This can generally allow to infer from the text the category, the topic or the sentiment.

From the bag-of-words model we can build features to be used by a classifier, here we assume that each word is a feature that can either be True or False. We implement this in Python as a dictionary where for each word in a sentence we associate True, if a word is missing, that would be the same as assigning False.

### Train a Classifier for Sentiment Analysis

Using our build_bag_of_words_features function we can build separately the negative and positive features. Basically for each of the 1000 negative and for the 1000 positive review, we create one dictionary of the words and we associate the label "neg" and "pos" to it.

We are using NaiveBayesClassifier from nltk librabry to generate model.

### Evaluate the Classifier

Accuracy of the model on the training set i.e. the same data used for training, we expect this to be a very high number because the algorithm already "saw" those data. Accuracy is the fraction of the data that is classified correctly, we can turn it into percent. It is 98.06%.

The accuracy above is mostly a check that nothing went very wrong in the training, the real measure of accuracy is on the remaining 20% of the data that wasn't used in training, the test data. That is 71.75%.

So we can consider the accuracy here is around 70% which is pretty good for such a simple model if we consider that the estimated accuracy for a person is about 80%.
