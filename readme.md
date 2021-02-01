# short-text-language-identification

## prereads

* [what is encoding - basically we need all data to be in utf-8 or unicode encoding](https://www.w3.org/International/questions/qa-what-is-encoding)
* [naive bayes langdetect by shuyo](https://www.slideshare.net/shuyo/language-detection-library-for-java)
* [automatic language identification using deep neural networks](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42538.pdf)
  * representation of a sentence is as an "i-vector" - idk didn't look too deeply
* [language identification from text documents](http://cs229.stanford.edu/proj2015/324_report.pdf)
  * pretty good, vectorized each sentence over 1 to 5-grams of the tokens delimited by white space characters
  * compares RNN with multinomial naive bayes and logistic regression
  * pretty fat LSTM layer, 1280 hidden states with dropout of 0.4 was best result
* [manually constructed data + neural net for lang ID for a given word](https://medium.com/coinmonks/language-prediction-using-deep-neural-networks-42eb131444a5)
  * not BOW representation; assumed each word is up to 12 characters, have 1 hot vector for each character, total of 26 * 12 = 312 digit long strings to represent each word
  * does not consider odd characters and accents, etc.
* [deep learning programming language detection](https://github.com/aliostad/deep-learning-lang-detection)
  * Approach for DL has been based on Zhang and LeCun's 2016 [paper "Text Understanding from Scratch"](https://arxiv.org/pdf/1502.01710.pdf). The main technique is that instead of using word2vec to create word embedding, characters are quantised (turned to one-hot-vector) and then the document is represented by a sequence of quantised characters (vectors)(see manual construction bullet point above). Currently the document is truncated at 2KB and smaller docs are padded by all zero vectors.
* [how apple does short text lang identification - not too helpful cause the images won't load but it seems they also use n-gram approach?](https://machinelearning.apple.com/research/language-identification-from-very-short-strings)
* [animated lstm and gru architectures as refresher](https://towardsdatascience.com/animated-rnn-lstm-and-gru-ef124d06cf45)

* [relatively small dataset from tatoeba](https://tatoeba.org/eng/downloads)

* [test cases](https://medium.com/the-artificial-impostor/detecting-chinese-characters-in-unicode-strings-4ac839ba313a)

* [cool tangent - Multiclass Language Identification using Deep Learning on Spectral Images of Audio Signals](https://arxiv.org/abs/1905.04348)

## approaches

### representation of a sentence

can try any of the following:

* bag of words / n-grams
* naive bayes probability for each word / n-gram
* characters are quantised (turned to one-hot-vector) and then the document is represented by a sequence of quantised characters (vectors)

### regularization of neural net

* dropout layers
* dropout during LSTM layer
* [regularization of a dense layer](https://keras.io/api/layers/regularizers/)

[see also](https://towardsdatascience.com/machine-learning-model-regularization-in-practice-an-example-with-keras-and-tensorflow-2-0-52a96746123e)
