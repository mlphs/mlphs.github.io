---
title: Supervised Learning
subtitle: Lesson 2
image: assets/img/portfolio/01-thumbnail.png
alt: 

caption:
  title: Supervised Learning
  subtitle: Lesson 2
  thumbnail: assets/img/portfolio/01-thumbnail.png
---
Humans are not born with many skills. We need to learn how to sort mail, land airplanes, and have friendly conversations. Computer scientists have tried to teach computers how to learn like we do, with a process called **supervised learning**.

The process of learning is how anything can make decisions. Humans, animals, or AI systems can adapt their behavior based on their experiences.

We will discuss three types of learning:
1. **Reinforcement learning** is the process of learning in an environment through feedback from an AI's behavior. Think about how babies learn to walk. Nobody teaches a baby how to walk, but they learn from their experiences of practicing and stumbling, until they can put one foot in front of the other. 
2. **Unsupervised learning** is the process of learning *without* training labels. It is also known as clustering or grouping. Sites like Youtube use unsupervised learning to find patterns and frames of videos, and compress those frames so videos can be streamed to us quickly. 
3. **Supervised learning** is the process of learning *with* training labels. It is the most widely used kind of learning when it comes to AI. We will discuss supervised learning in more detail below.

To explain supervised learning, we will walk through an example.

Suppose we have a dataset containing house sizes and prices in Portland, Oregon. Our goal is to predict housing prices. 

<img src="https://github.com/mlphs/mlphs.github.io/tree/master/assets/img/portfolio/project2/housing-regression.png" width="100" height="100">

Given the data, let's say we have a friend who owns a house that is 750 sq feet and our friend wants to know how much to sell the house for. 
One learning algorithm would be to put straight line through data and based on that, maybe house sell for 175k.
![alt text](https://github.com/mlphs/mlphs.github.io/blob/master/assets/img/portfolio/project2/housing-regression-linear.png?raw=true)
