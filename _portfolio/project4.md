---
title: Neural Networks (Part 1)
subtitle: Lesson 4
image: assets/img/portfolio/project4/neural-network-architecture.png
alt: 

caption:
  title: Neural Networks (Part 1)
  subtitle: Lesson 4
  thumbnail: assets/img/portfolio/project4/neural-network-architecture.png
---
<p align="left">
Previously, we looked at a perceptron (a program that imitates one neuron). But, our brains make decisions based on hundreds of millions of neurons, which have trillions of connections between them. <br> <br>

We can do a lot more with AI if we connect a bunch of perceptrons together to create what is called an artificial neural network. <br> <br>

Neural networks are better for tasks like image recognition. The secret to their success is hidden layers. 
All neural networks are made up of an input layer, an output layer, and any number of hidden layers in between. <br> <br> 

There are many different arrangements, but we will look at the classic multilayer perceptron. 
The input layer is where the neural network receives input data represented as numbers. 
Each input neuron represents a single feature,which is some characteristic of the data.
Features are straightforward if we are talking about something that’s already a number, (e.g. grams of sugar in a donut). But, just about anything can be represented as a number. Sounds can be represented as the amplitudes of the sound wave (so, each feature would have a number representing the amplitude at a moment in time). Words in a paragraph can be represented by how many times each word appears (so, each feature would be the frequency of one word). <br> <br>

If we are trying to label an image of a dog, each feature would represent information about a pixel.
For a grayscale image, each feature would have a number representing how bright a pixel is, but for a colored image, we can represent each pixel with 3 numbers (the amount of red, green, and blue). <br> <br>

Once the features have data, each one sends its number to every neuron in the next layer (which is called the hidden layer). Then, each hidden layer neuron mathematically combines all the numbers it gets.<br> <br>

The goal is to measure whether the input data has certain components. <br> <br>

In an image recognition problem, these components can be a color in the center, a curve near the top, or even whether the image contains eyes, ears, or fur. <br> <br>

Instead of answering yes or no like in the perceptron, each neuron in the hidden layer does some complicated math and outputs a number. Then, each neuron sends its number to every number in the next layer, which could be another hidden layer or the output layer.

The output layer is where the final hidden layer outputs are mathematically combined to answer the problem.
Let’s say we are trying to label an image as a dog. We might have a single output representing a single answer (that the image is a dog). But, if there are many answers, we’ll need a bunch  of output neurons. Each output neuron corresponds to the probability for each label (e.g. dog, cat, bird, and more). We pick the answer with the highest probability. 
</p>
