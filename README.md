# Question And Answering System
An intelligent system which predicts answers for the given questions from provided comprehension. It is implemented using Neuro-Linguistic Programming and Python.

### Technologies used:
nltk, sckit-learn, keras, tensorflow

## Implementation
### Data Extraction:
The question answering model is trained using SQuAD data: a new reading comprehension dataset consisting of 100,000+ questions posed by crowd workers on a set of Wikipedia articles, where the answer to each question is a segment of text from the corresponding reading passage and uses pre trained word vectors combination of Wikipedia 2014 dump and the Gigaword 5 corpus. To view the SQuAD data set used for training, run the squad_explore.py.

### Data Preprocessing:
The dataset extracted from squad can’t be used as it is in our neural network model. For suitable features to be utilized data has to be preprocessed. 
Firstly, the data is retrieved from the stored json file into three different lists: paragraph, question and answer. Now, paragraph and questionnaire treated as input and answers as output. These passages are then tokenized with tokenize function and are broken into tokens. For this keras tokenizer library is used. We have raw text,
but we want to make predictions on a per-word basis. This means we must tokenize our comments into sentences, and sentences into words. 

### Vectorization of Features and Dictionary formation:
With the help of Tokenized words a dictionary is formed containing passages, questions and answers. In which each word is mapped with a unique index. Vectorization is performed with the help of GloVe encoding. GloVe encoding is achieved by mapping words into a meaningful space where the distance between words is related to semantic similarity. W used pre trained word vectors which is a combination of Wikipedia 2014 dump and the Gigaword 5 corpus. This representation is trained using an original method called Global Vectors (GloVe). It encodes 400,000 tokens as unique vectors.

### Training:
The prediction model has two parts: GloVe model, which uses pre trained word vectors; and Sequence to Sequence model, which was trained using the SQuAD data set on with 200 epochs and batch size of 64.

### Prediction:
With the trained models, the predictors load these model and predict answer based on the paragraph context and the question.
