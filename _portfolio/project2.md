---
title: Supervised Learning
subtitle: Lesson 2
image: assets/img/portfolio/project2/donut-classification-2d-dboundary.png
alt: 

caption:
  title: Supervised Learning
  subtitle: Lesson 2
  thumbnail: assets/img/portfolio/project2/donut-classification-2d-dboundary.png
---
<p align="left">
Humans are not born with many skills. We need to learn how to sort mail, land airplanes, and have friendly conversations. Computer scientists have tried to teach computers how to learn like we do, with a process called <b>supervised learning</b>.
</p>

<p align="left">
The process of learning is how anything can make decisions. Humans, animals, or AI systems can adapt their behavior based on their experiences.<br>
</p>

<p align="left">
We will discuss three types of learning: <br>
1. <b>Reinforcement learning</b> is the process of learning in an environment through feedback from an AI's behavior. Think about how babies learn to walk. Nobody teaches a baby how to walk, but they learn from their experiences of practicing and stumbling, until they can put one foot in front of the other. <br>
2. <b>Unsupervised learning</b> is the process of learning *without* training labels. It is also known as clustering or grouping. Sites like Youtube use unsupervised learning to find patterns and frames of videos, and compress those frames so videos can be streamed to us quickly. <br>
3. <b>Supervised learning</b> is the process of learning *with* training labels. It is the most widely used kind of learning when it comes to AI. We will discuss supervised learning in more detail below.
</p>
  
<p align="left">
To explain supervised learning, we will walk through a few examples.
</p>
  
### Regression
<p align="left">
Suppose we have a dataset containing house sizes and prices in Portland, Oregon. Our goal is to predict housing prices. 
</p>

<img src="/assets/img/portfolio/project2/housing-regression.png" width="500">

<p align="left">
Given the data, let's say we have a friend who owns a house that is 750 sq feet and our friend wants to know how much to sell the house for. 
One learning algorithm would be to put straight line through data and based on that, maybe sell the house for 175k.
</p>

<img src="/assets/img/portfolio/project2/housing-regression-linear.png" width="500">

<p align="left">
Instead of fitting a straight line, we could also fit a quadratic function to the data and based on that, maybe sell the house for 240k.
</p>

<img src="/assets/img/portfolio/project2/housing-regression-quadratic.png" width="500">

<p align="left">
This is an example of a supervised learning algorithm. Supervised learning refers to the fact that we provide the algorithm with a dataset where the "right answers" are given. 

In the housing problem, for every example in the dataset, we provided the right price that the house sold for. Our task was to produce more of these right answers. This is called a regression problem, where we predict continous valued outputs (which, in this case, is price of the house).

Next, we will look at another supervised learning example.
</p>

### Classification
<p align="left">
Suppose we have a bunch of donuts and bagels, and we want to be able to determine whether or not some food is a donut. Suppose we have 5 examples of donuts and 5 examples of bagels, and we know the mass of each food item in grams.
</p>

<img src="/assets/img/portfolio/project2/donut-classification.png" width="500">

<p align="left">
Let's say we have a food item. We want to estimate the probability that the food item is a donut. 

This is an example of a classification problem, where we have discrete valued outputs (0 or 1). Note that it is possible to have more than two possible values for the output (e.g., if we wanted to classify food as donut, bagel, or croissant). 

We can also draw our donut and bagel data as follows. Note that we take the original plot of the dataset and map it down to a real line. The orange triangles indicate bagel examples (non-donut examples) and the blue triangles indicate donut examples. 
</p>

<img src="/assets/img/portfolio/project2/donut-classification-1d.png" width="500">

<p align="left">
In this example, we use only one feature or attribute (i.e., mass in grams). Suppose we know the diameter of the food items in centimeters in addition to the mass in grams. 
</p>

<img src="/assets/img/portfolio/project2/donut-classification-2d.png" width="500">

<p align="left">
Let's say we have a food item, as indicated by the green triangle. We want to estimate the probability that the food item is a donut. The learning algorithm can draw a straight line through the data to try to separate the donuts from bagels. 
</p>

<img src="/assets/img/portfolio/project2/donut-classification-2d-dboundary.png" width="500">

<p align="left">
Based on where the green triangle falls with respect to the decision boundary, we would decide it is more likely that the food item is a bagel than it might be a donut. So, we would classify the food item as a bagel. 

In this example, we had two features: mass and diameter. In other machine learning problems, we might have more features. 
</p>

### Exercise
<p align="left">
Based on what we've learned, let's do a quick exercise. 

You are running a company and you want to develop learning algorithms to address each of the two problems.\
<b>Problem 1:</b> You have a large inventory of identical items. You want to predict how many of those items will sell over the next three months.\
<b>Problem 2:</b> You'd like software to examine individual customer accounts, and for each account decide whether it has been hacked/compromised. 

Should you treat these as classification or regression problems?\
A) Treat both problems as classification problems\
B) Treat problem 1 as a classification problem and problem 2 as a regression problem\
C) Treat problem 1 as a regression problem and problem 2 as a classification problem\
D) Treat both problems as regression problems\

The correct answer is C.
</p>

### Sources
1. [Lecture 1.2 — Supervised Learning — Machine Learning by Andrew Ng](https://www.youtube.com/watch?v=bQI5uDxrFfA)
2. [Supervised Learning: Crash Course AI #2](https://www.youtube.com/watch?v=4qVRBYAdLAo&list=PL8dPuuaLjXtO65LeD2p4_Sb5XQ51par_b&index=3)


