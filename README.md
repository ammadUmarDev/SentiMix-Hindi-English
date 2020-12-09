# SentiMix-Hindi-English
Predict the sentiment of a given code-mixed tweet. The sentiment labels are positive, negative, or neutral, and the code-mixed languages will be English-Hindi and English-Spanish. Besides the sentiment labels, we will also provide the language labels at the word level. The word-level language tags are en (English), spa (Spanish), hi (Hindi), mixed, and univ (e.g., symbols, @ mentions, hashtags).

AI Project Fall 2020
SentiMix Hindi-English

Name
Ammad Umar
Roll No
17I-0092
Section
C


CodaLab Username
Ammad_092_C 
Ranking

F1 accuracy
0.670
Project Code
https://colab.research.google.com/drive/19iNAjff_7JviYBnrxVkkl7fND-5ZOe3t?usp=sharing

The SentiMix task - A summary 

The task is to predict the sentiment of a given code-mixed tweet. The sentiment labels are positive, negative, or neutral, and the code-mixed languages will be English-Hindi and English-Spanish. Besides the sentiment labels, we will also provide the language labels at the word level. The word-level language tags are en (English), spa (Spanish), hi (Hindi), mixed, and univ (e.g., symbols, @ mentions, hashtags). Efficiency will be measured in terms of Precision, Recall, and F-measure. 
Sentimental Analysis
Sentiment analysis is a powerful tool that allows computers to understand the underlying subjective tone of a piece of writing. This is something that humans have difficulty with, and as you might imagine, it isn’t always so easy for computers, either. But with the right tools and Python, you can use sentiment analysis to better understand the sentiment of a piece of writing.
Spacy for NLP
Spacy is written in cython language, (C extension of Python designed to give C like performance to the python program). Hence is a quite fast library. spaCy provides a concise API to access its methods and properties governed by trained machine (and deep) learning models.

Implementation of spacy and access to different properties is initiated by creating pipelines. A pipeline is created by loading the models. There are different types of models provided in the package which contains the information about language – vocabularies, trained vectors, syntaxes and entities.

These pipelines output a wide range of document properties such as – tokens, token’s reference index, part of speech tags, entities, vectors, sentiment, vocabulary etc. Let’s explore some of these properties.

Tokenization
Every spaCy document is tokenized into sentences and further into tokens which can be accessed by iterating the document.

Part of Speech Tagging
Part-of-speech tags are the properties of the word that are defined by the usage of the word in the grammatically correct sentence. These tags can be used as the text features in information filtering, statistical models, and rule based parsing.

Entity Detection Spacy
It consists of a fast entity recognition model which is capable of identifying entity phrases from the document. Entities can be of different types, such as – person, location, organization, dates, numerals, etc. These entities can be accessed through “.ents” property.
Dependency Parsing
One of the most powerful features of spacy is the extremely fast and accurate syntactic dependency parser which can be accessed via lightweight API. The parser can also be used for sentence boundary detection and phrase chunking. The relations can be accessed by the properties “.children” , “.root”, “.ancestor” etc.
Word to Vectors Integration
Spacy also provides inbuilt integration of dense, real valued vectors representing distributional similarity information. It uses GloVe vectors to generate vectors. GloVe is an unsupervised learning algorithm for obtaining vector representations for words.

Understanding Data
The data is in CONLL format. It looks like:

meta    uid    sentiment
token    lang_id 
meta    uid    sentiment
token    lang_id
token    lang_id 

Uid is a unique id for each tweet. 
lang_id is 'HIN' if the token is in Hindi, 'ENG' if the token is in English, and 'O' if the token is in neither of the languages. 
The sentiment is either positive, negative or neutral. 
The train data after the split has 14k tweets.
The validation data has 3k tweets.

Data Preprocessing
The necessary steps include (but aren’t limited to) the following:
Tokenizing sentences to break text down into sentences, words, or other units
Removing stop words like “if,” “but,” “or,” and so on
Removing punctuations words
Normalizing words by condensing all forms of a word into a single form
Vectorizing text by turning the text into a numerical representation for consumption by your classifier
Clean, tokenize, vectorize, and classify using Count Vectorizor.

Features are ‘Sentences’
Labels are ‘Labels’

Model Selection
Gradient Boosting Classifier for classification.

GB builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary differentiable loss functions. In each stage n_classes_ regression trees fit on the negative gradient of the binomial or multinomial deviance loss function. Binary classification is a special case where only a single regression tree is induced.

Model Pipeline
Initiating a pipeline that takes each tweet, tokenizes it, removes stop words, removes punctuations, after vectorization and normalization the data is fit to model.
