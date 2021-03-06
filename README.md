# Predict-the-language-of-source-code

There are hundreds and thousands of programming languages available today. Identifying the famous languages may be easy by looking at the code syntax or file extensions but not so for less popular or older languages. Nonetheless, we can train the machine learning models to learn and identify the language of the code snippets.

The learning process can be divided into two parts - feature extraction and a learning algorithm to classify the data. I used Keras text preprocessing utilities (One hot encoding) to prepare the text for feeding to a Naive Bayes classifier and Word embedding to feed to a Keras Sequential model. 

The word Keras Tokenizer API converts the raw text into tokens taking into account the most common words (vocabulary size), each token is assigned an integer index and then this integer index is converted into a vector of size equal to the vocabulary size. This technique is called the Word level One hot encoding. This vector, hence obtained, is provided as an input to the Naive Bayes classifier which predicts the language of the validation data with an accuracy of 99.8%.

Word embedding refers to the feature learning approach in which words are mapped to vectors of real numbers and semantically similar words have similar representations. The difference between the two approaches is that the vectors obtained through one-hot encoding are binary, sparse and high-dimensional (same dimensionality as the vocabulary size) while the vectors by word embeddings are low-dimensional or dense vectors.

There are two ways to obtain word embeddings: 1. Learning word embeddings by initialising the word vectors randomly and learning the weights using Backpropagation algorithm. 2. Using pre-trained word embeddings like Word2Vec, GLoVe. I used the first method and trained the vectors from scratch. This vector goes to the dense layers as input. This model predicts the language of the validation dataset with an accuracy of 77%.

For now, I used 4 languages for classification namely c, java, javascript and python, and a small dataset of 1000 files of each language type. This is a basic model, I would work on it to improve the accuracy of the neural network model. 
