# Steps to Start Training custom models in Amazon SageMaker
## Different algorithm in Tensorflow and Pytorch trained in SageMaker using SageMaker containers or custom containers
In this repository we will develop many notebooks and scripts to train models in several scenarios with Tensorflow or Pytorch framework. Many of them will be explained in my Medium o personal fastaipages blog.


**On development**
*Different models are under development like the transformer NMT custom container and other Pytorch models are comming in the next weeks.*

## Problem description

**Problem: Neural Machine Translation, NMT**
*Machine translation (MT) is the task of automatically converting source text in one language to text in another language. Given a sequence of text in a source language, there is no one single best translation of that text to another language. This is because of the natural ambiguity and flexibility of human language. This makes the challenge of automatic machine translation difficult, perhaps one of the most difficult in artificial intelligence.*

From the above we can deduce that NMT is a problem where we process an input sequence to produce an output sequence, that is, a sequence-to-sequence (seq2seq) problem. Specifically of the many-to-many type, sequence of several elements both at the input and at the output, and the encoder-decoder architecture for recurrent neural networks is the standard method.

## The data set

**For the NMT problem**
For this exercise we will use pairs of simple sentences, the source in English and target in Spanish, from the Tatoeba project where people contribute adding translations every day. This is the [link](http://www.manythings.org/anki/) to some traslations in different languages. There you can download the Spanish - English spa_eng.zip file, it contains 124457 pairs of sentences. The data is also available in the data folder in this repo.

We use a list of **non breaking prefixes** to avoid the tokenizer to split or break words including that prefixes. Inm our example we do not want to remove some the dot for some well-konw words.You can find non breaking prefixes for many languages in the Kaggle website: 

https://www.kaggle.com/nltkdata/nonbreaking-prefixes/activity


The text sentences are almost clean, they are simple plain text, so we only need to remove dots that are not a end of sentence symbol and duplicated white spaces. 

## Content
This repository contains the next source code file:
- transformer_nmt_training_and_serving: This notebook shows how to train a transformer model on the NMT problem using script mode in Tensorflow 2 with a prebuilt container from SageMaker.

**On development**
- transformer_nmt_training_custom_container: It is a demo on how to train a ML model in the framework Amazon SageMaker using a custom container. This model is very simple so you do not really need to launch a training job on SageMaker but it is intended for educational purposes. We also deploy our model as a service and make some predictions. This notebook requieres the folders:
    - train: here is where the training script is located. It also includes the model.py with the definition of our Transformer Class and a utils.py with some helper functions to preprocess the text.
    - serve: this folder is needed to deploy the model, it contains a model.py and utils.py, the same as before, and a predict.py with the lines of code to make predictions on the model. 

## Contributing
If you find some bug or typo, please let me know or fixit and push it to be analyzed. 

## License

These notebooks are under a public GNU License.