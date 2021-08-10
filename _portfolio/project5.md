---
title: Neural Networks (Pt. 2)
subtitle: Lesson 5
image: assets/img/portfolio/project4/neural-network-architecture.png
alt: 

caption:
  title: Neural Networks (Pt. 2)
  subtitle: Lesson 5
  thumbnail: assets/img/portfolio/project4/neural-network-architecture.png
---
<p align="left">
Neural networks handle mistakes using an algorithm called backpropagation to make sure all the neurons that contributed to an error get their math adjusted. <br> <br>

Neural networks have two main parts: <br>
1. The architecture <br>
2. The weights  <br> <br>

The architecture includes neurons and their connections. The weights are numbers that fine-tune how the neurons do their math to get an output. If a neural network makes a mistake,  usually, the weights aren’t adjusted correctly and we need to update them so they make better predictions next time. The task of finding the best weights for a neural network architecture is called optimization. <br> <br>

To better understand optimization, let’s start with an example. <br> <br>

Suppose we have a dataset containing house sizes and prices in Portland, Oregon. Our goal is to predict housing prices. A simple way to do this is by graphing those data points.. Then, we can look for a pattern in that graph to make predictions. A way computers do this is with an optimization strategy called linear regression. We start by drawing a random straight line on the graph, which kind of fits the data points. <br> <br>

To optimize, we need to know how incorrect this guess is. Hence, we calculate the distance between the line and each of the data points, add it all up, and that gives us the error (note that we are quantifying how big of a mistake we made). <br> <br>

The goal of linear regression is to adjust the line to make the error as small as possible.
We want the line to fit the training data as much as it can. The result is called the line of best fit. We can use this straight line to predict how many swimmers will show up for any temperature. <br> <br>

To get more accurate results, we might want to consider more than two features, like for example adding the number of bathrooms in the residence,  which would turn our 2d graph into 3d. And our line of best fit would be more like a plane of best fit. But if we added a fourth feature, like the number of floors in the residence,  we can’t visualize this anymore. As we consider more features, we add more dimensions to the graph, the optimization problem gets trickier, and fitting the training data is tougher. <br> <br>

This is where neural networks come in handy. <br> <br>

By connecting together many simple neurons with weights, a neural network can learn to solve complicated problems, where the line of best fit becomes a weird multi-dimensional function. <br> <br>


To stick with the same example, the input layer of this neural network takes features like square footage of the house, the number of bathrooms, number of floors, and so on. The output layer predicts the price of the house. <br> <br>

Let’s ignore the architecture of the neural network for now and focus on the weights. We begin by setting the weights to random numbers, like the random line on the graph we drew earlier. Note that this time, it’s not just one random line because we have lots of inputs, so it is a lot of lines that are combined together to make one function. <br> <br>

To train this neural network, we will give the network access to the dataset because we also know the price of each house in the dataset. The neurons will multiply those features by the weights, add the results together, and pass information to the hidden layers until the output neuron has an answer. <br> <br>

Suppose for the house of 500 sq feet, the neural network outputs the price $145k, and the true price is $100k. 
There is a difference between the neural network’s output and the actual price of each house. Because we just have one output neuron, that difference of 45k is the error. <br> <br>

In some neural networks though, the output layer may have a lot of neurons, so the difference between the predicted answer and the correct answer is more than just one number. <br> <br>

In these cases, the error is represented by what’s known as a loss function. Moving forward, we need to adjust the neural network’s weights so that the next time we give the neural network similar inputs, its math and final output will be more accurate. We need the neural network to learn from its mistakes, which is similar to the supervisor button idea when we were discussing the perceptron program. a button to supervise his learning when he had the perceptron program. <br> <br>

Backpropagation helps neurons learn. The basic goal is to look at the loss function and then assign blame to neurons back in the previous layers of the network. Some neurons’ calculations may have been more to blame for the error than others, so their weights will be adjusted more. <br> <br>

This information is fed backwards, which is where the idea of backpropagation comes from. For example, the error from our output neuron would go back a layer and adjust the weights that get applied to our hidden layer neuron outputs. The error from our hidden layer neurons would go back a layer and adjust the weights that get applied to our features. <br> <br>

Recall that our goal is to find the best combination of weights to get the lowest error. To explain the logic behind optimization with a metaphor, let’s imagine that weights in our neural network are like latitude and longitude coordinates on a map. The error of our neural network is the altitude -- lower is better. The neural network is where the explorer is on a quest to find the lowest point in the deepest valley. The latitude and longitude of that lowest point -- where the error is the smallest -- are the weights of the neural network’s global optimal solution. <br> <br>

The neural network has no idea where this valley actually is. By randomly setting the initial weights of our neural network, we’re basically dumping our model in the middle of nowhere. All the model knows is its current latitude, longitude, and altitude. <br> <br>

We might be lucky and be on the side of the deepest valley. However, we could also be at the top of the highest mountain somewhere far away. The only way to know is to explore by looking around and making a guess. <br> <br>

Suppose we notice that we can descend down a little by moving northeast, so our model takes a step down and updates its latitude and longitude. From this new position, the model  looks around and picks another step that decreases its altitude a little more. With every step, the model updates its coordinates and decreases its latitude. <br> <br>

Eventually, the model looks around and finds that it cannot go down anymore. Thus, the model thinks it has found the lowest point in the deepest valley. However, if we look at the whole map, we can see that our model found the bottom of a small gorge when it ran out of “down.” This solution is better than where the model started, but is not the lowest point of the deepest valley. This is called a local optimal solution, where the weights make the error relatively small, but not the smallest it could be. <br> <br>

Backpropagation and learning always involves lots of little steps, and optimization is tricky with any neural network. Referring to our previous example of optimization as exploring a metaphorical map, we’re never quite sure if we’re headed in the right direction or if we’ve reached the lowest valley with the smallest error -- again that’s the global optimal solution. <br> <br>

But, we can use some tricks to help us better navigate. For example, when we drop an explorer somewhere on the map, they could be really far from the lowest valley, with a giant mountain range in the way. It might be a good idea to try different random starting points to be sure that the neural network isn’t getting stuck at a locally optimal solution. <br> <br>

Or instead of restarting over and over again, we could have a team of explorers that start from different locations and explore the jungle simultaneously. <br> <br>

We could even adjust the explorer’s step size, so that they can step right over small hills as they try to find and descend into a valley. This step size is called the learning rate, and it’s how much the neuron weights get adjusted every time backpropagation happens. <br> <br>

Ultimately, we’re looking for ways to minimize the loss function as we train neural networks. But even if we use a bunch of training data and backpropagation to find the global optimal, we still need to make sure that the system can answer new questions. <br> <br>

It’s easy to solve a problem we’ve seen before, like taking a test after studying the answer key. We may get an A, but we didn’t actually learn much. To really test what we’ve learned, we need to solve problems we haven’t seen before. The same is true for neural networks. <br> <br>

More data can be better for finding patterns and accuracy, as long as the computer can handle it. Over time, backpropagation will adjust the neuron weights, so that the neural network’s output matches the training data.This is called fitting to the training data, and with this complicated neural network, we’re looking for a multi-dimensional function. <br> <br>

Sometimes, backpropagation is too good at making a neural network fit to certain data. There are lots of coincidental relationships in big datasets. For example, the divorce rate in Maine may be correlated with U.S. margarine consumption, or skiing revenue may be correlated with the number of people dying by getting trapped in their bedsheets. Neural networks are really good at finding these kinds of relationships. This can be a big problem, because if we give a neural network some new data that doesn’t adhere  to these silly correlations, then it will probably make some strange errors. That’s a danger known as overfitting. <br> <br>
</p>
