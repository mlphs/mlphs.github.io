---
title: NLP
subtitle: Lesson 8
image: assets/img/portfolio/project8/rnn.png
alt: 

caption:
  title: NLP
  subtitle: Lesson 8
  thumbnail: assets/img/portfolio/project8/rnn.png
---
<p align="left">
Natural Language Processing (NLP) mainly explores two big ideas <br> 
1. Natural language understanding: how we get meaning out of combinations of letters. These are AI that filter spam emails, figure out whether a search for “apple” was
   the fruit or company, and instruct a self-driving car how to get to a friend’s house. <br> 
2. Natural language generation: how to generate language from knowledge. These are AI that perform translations, summarize documents, or chat with you. <br> <br>

The key to both problems is understanding the meaning of a word. This is tricky, because words do not have meaning on their own. We assign meaning to symbols. 
Moreover, in many cases, language can be ambiguous. And, the meaning of a word depends on the context it is used in. <br> <br> 

One way to guess which words have similar meaning is to use distributional semantics, i.e., seeing which words appear in the same sentences or not. 
To make computers understand distributional semantics, we have to use math. <br> <br> 

One simple technique is to use count vectors. A count vector is the number of times a word appears in the same article or sentence as other common words. 
If two words show up in the same sentence, they probably have similar meanings. <br> <br> 

Suppose we ask an algorithm to compare the following words using count vectors to guess which of them has similar meaning: car, cat, and felidae. 
Suppose we download the beginning of the Wikipedia pages for each word to see which other words show up. A lot of the top words are all the same: the, and, of, in. 
These are all function words or stop words, which help define the structure of language, and help convey precise meaning. “An apple” means any apple, but “the apple” 
specifies one in particular. Because they change the meaning of another word, they don’t have much meaning by themselves, so we can remove them for now and simplify 
plurals and conjugations. <br> <br> 
</p>

<img src="assets/img/portfolio/project8/count-vectors.png" width="500">

<p align="left">
Based on this, it looks like cat and felidae mean almost the same thing, because they both
show up with lots of the same words in their Wikipedia articles. Neither of them mean the same thing as car. <br> <br> 

One of the problems with count vectors is that we have to store a LOT of data. To compare a bunch of words using counts like this, we’d need a massive list of every word 
we’ve ever seen in the same sentence, and that’s unmanageable. We’d like to learn a representation for words that captures all the same relationships and similarities as 
count vectors but is much more compact. <br> <br> 

We needed a model that could build internal representations and that could generate predictions. This is where the encoder-decoder model comes in: the encoder tells us
what we should think and remember about what we just read and the decoder uses that thought to decide what we want to say or do. <br> <br> 
</p>

### Language Modeling
<p align="left">
Let’s create a game of fill in the blank to see what basic pieces we need to train an unsupervised learning model. This is a simple task called language modeling.
If I have the sentence “I’m kinda hungry, I think I’d like some chocolate _____ .”, what are the most likely words that can go in that spot? How can we train a model to 
encode the sentence and decode a guess for the blank? <br> <br> 

I can guess the answer might be “cake” or “milk” but probably not something like “potatoes.”
The group of words that can fill in that blank is an unsupervised cluster that an AI could use.
For this sentence, our encoder might only need to focus on the word chocolate so the
decoder has a cluster of “chocolate food words” to pull from to fill in the blank. <br> <br> 

Now let’s try a harder example: “Dianna, a friend of mine from San Diego who really loves physics, is having a birthday party next week,
so I want to find a present for ____.” <br> <br> 

There are two important things to note here <br> 
1. The word Dianna appeared 27 words ago <br> 
2. Diana happens to use the pronoun “her” <br> <br> 

Thus, we want our encoder to build a representation that captures all these pieces of information from the sentence, so the decoder can choose the right word for the blank.
</p>

### RNNs
<p align="left">
Let’s step away from our high level view of language modeling and try to predict the next word in a sentence anyway with a neural network. 
To do this, our data will be lots of sentences we collect from things like someone speaking or text from books. Then, for each word in every sentence, 
we’ll play a game of fill-in-the-blank. We’ll train a model to encode up to that blank and then predict the word that should go there. Since we have the whole sentence, 
we know the correct answer. <br> <br> 

First, we need to define the encoder. We need a model that can read the input sentence.
We’ll use a type of neural network called a Recurrent Neural Network or RNN. RNNs have a loop in them that lets them reuse a single hidden layer, which gets updated
as the model reads one word at a time. Slowly, the model builds up an understanding of the whole sentence, including which words came first or last, which words are
modifying other words, and a whole bunch of other grammatical properties that are linked to meaning. <br> <br> 
</p>

<img src="assets/img/portfolio/project8/rnn.png" width="500">

<p align="left">
Now, we can’t just directly put words inside a network. We also don’t have features we can easily measure and give the model either. Unlike images, we can’t even measure
pixel values. So, we’re going to ask the model to learn the right representation for a word on its
own (note: this is where the unsupervised learning comes in). <br> <br> 

We’ll start off by assigning each word a random representation, which in this case is a random list of numbers called a vector. Next, our encoder will take in each of
those representations and combine them into a single shared representation for the whole sentence. <br> <br> 

At this point, our representation might be gibberish, but in order to train the RNN, we need it to make predictions. For now, we’ll consider a very simple decoder, a 
single layer network that takes in the sentence representation vector, and then outputs a score for every possible word in our vocabulary. <br> <br> 

We can interpret the highest scored word as our model’s prediction. Then, we can use backpropagation to train the RNN, like we’ve done before with neural networks. <br> <br> 

By training the model on which word to predict next, the model learn weights for
the encoder RNN and the decoder prediction layer. The model changes those random representations we gave every word at the beginning. If two words mean something similar, 
the model makes their vectors more similar. <br> <br> 

This is how we can take in part of a sentence and predict the next word. 
</p>

### Other NLP Tasks
<p align="left">
Now, let’s discuss another NLP task. If our model took in English and produced Spanish, we’d have a translation system. Or, our model could read questions and produce answers, 
like Siri or Alexa try to do. <br> <br> 

The representations of words that our model learns for one kind of task might not work for others. For example, if we trained a model based on reading a bunch of cooking recipes,
the model might learn that roses are made of icing and placed on cakes. But, the model won’t learn that cake roses are different from real roses. <br> <br> 

Acquiring, encoding, and using written or spoken knowledge to help people is a huge and exciting task, because we use language for so many things! Every time you type or talk 
to a computer, phone or other gadget, NLP is there. 
</p>


### Sources
1. [NLP: Crash Course AI #7](https://www.youtube.com/watch?v=oi0JXuL19TA&list=PLH2l6uzC4UEVGUu2--3xBjTMFily1IwP9&index=8)
2. [Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
