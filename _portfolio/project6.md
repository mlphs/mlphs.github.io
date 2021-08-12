---
title: Unsupervised Learning
subtitle: Lesson 6
image: assets/img/portfolio/project6/unsupervised-learning.png
alt: 

caption:
  title: Unsupervised Learning
  subtitle: Lesson 6
  thumbnail: assets/img/portfolio/project6/unsupervised-learning.png
---
<p align="left">
In supervised learning, we have datasets where each example was labeled as either a positive or negative example (e.g. donut or bagel). For each example, we were told explicitly what the “right answer” is. <br> <br>

In unsupervised learning, we are given data that does not have any labels. We’re given a dataset, and our goal is to find some type of structure in the data. 
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning.png" width="500">

<p align="left">
Given the dataset, an unsupervised learning algorithm might decide that the data lives in two different clusters. This is called a clustering algorithm. <br> <br>

Clustering can be used for many applications, such as <br>
>> Organizing large computer clusters to make data centers work more efficiently <br>
>> Identify cohesive groups of friends in social network analysis <br>
>> Group customers into different market segments to automatically and more efficiently sell or market to your
   different market segments together <br>
>> Perform astronomical data analysis to get interesting and useful theories about how galaxies are formed <br>
</p>

### K-Means Clustering
<p align="left">
To better understand clustering, let’s look at an example. Let’s say we buy a packet of iris seeds to plant in a garden. After the flowers bloom, it looks like there were several different species of irises mixed up in that one packet. We can use AI to help us analyze the garden. <br> <br> 
  
To construct the model, we need to answer to key questions: <br>
1. What observations can we measure? We could measure color, but all the irises are purple, so that’s not the best way to help tell them apart. But, different irises seem to have different petal lengths and widths. <br>
2. How do we want to represent the world? We will assume that there are k clusters in our data, but we do not know where they are. To help us, we can use the k-means clustering algorithm. <br> <br> 
  
In particular, we want to calculate the mean by adding up all data points in a cluster and dividing by the total number of points. <br> <br> 
Let’s start off with k = 3 (i.e., we are looking for three types of irises). 
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-1.png" width="500">

<p align="left">
To start, our model doesn’t know anything, so the averages and the predictions are random. Each flower in our dataset is randomly given a label as type 1, type 2, or type 3.
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-2.png" width="500">

<p align="left">
Next, our model tries to correct itself. The average of each cluster of data points should be in the middle. The model corrects itself by calculating new averages, marked by the x’s on the graph. Note that the graph is still pretty noisy. For example, there are many type 2 flowers close to the average of type 3 flowers.
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-3.png" width="500">

<p align="left">
Logically, we know irises of the same species tend to have similar petals. Since we did a correction or learning step, we can repeat the process, starting with a new prediction step. We can predict new labels using the x’s that mark the averages of each label. We will give each datapoint the label of its closest x. Then, we will calculate new averages. 
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-4.png" width="500">

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-5.png" width="500">

<p align="left">
We can repeat the process again. Eventually, the x’s will stop moving, and we will have a model of iris clusters crested with unsupervised learning.  
</p>

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-6.png" width="500">

<img src="assets/img/portfolio/project6/unsupervised-learning-iris-7.png" width="500">

### Cocktail Party Algorithm
<p align="left">
Clustering is just one type of unsupervised learning algorithm. Another unsupervised learning algorithm is known as the cocktail party problem. <br> <br>
  
Imagine there’s a party room where people are talking to each other, and there are voices overlapping since people are talking at the same time. Suppose there are two people talking at the same time. One of these people is talking to you, and it is hard to hear them. We will put two microphones in the room. Because these microphones are at two different distances from the speakers, each microphone records a different combination of these two speakers' voices. <br> <br>
  
Suppose in the first microphone recording, we hear someone counting in english and someone counting in spanish at the same time. Speaker 1 is louder in microphone 1 and speaker 2 is louder in microphone 2 because the two microphones are at different positions relative to the two speakers. <br> <br>

We will provide the  cocktail party algorithm with these two recordings, and ask the algorithm to find structure in the data. The algorithm will listen to these audio recordings and say that the two audio recordings are being added together to produce the two recordings. Moreover, the cocktail party algorithm will separate the two audio sources that were being added together to form our recordings. <br> <br>
</p>


### Sources
1. [Lecture 1.3 - Unsupervised Learning - Machine Learning by Andrew Ng](https://www.youtube.com/watch?v=jAA2g9ItoAc)
2. [Unsupervised Learning: Crash Course AI #6](https://www.youtube.com/watch?v=JnnaDNNb380)
