---
title: The Perceptron
subtitle: Lesson 3
image: assets/img/portfolio/project2/donut-classification-2d-dboundary.png
alt: 

caption:
  title: The Perceptron
  subtitle: Lesson 3
  thumbnail: assets/img/portfolio/project3/perceptron.png
---
<p align="left">
In 1958, a psychologist named Frank Rosenblatt was inspired by the Darmouth conference to create an artificial neuron. His goal was to teach this AI to classify images as triangles or not triangles using his supervision (hence, supervised learning). He called this machine <b>the perceptron</b>.
</p>

<p align="left">
He attached the perceptron to a camera. He would show the camera a picture of a triangle and not triangle (e.g. a circle). Depending on whether the camera saw ink or paper in each spot, each pixel would send a different electric signal to the perceptron. Then, the perceptron would add up all the signals that matched the triangle shape. 
</p>

<p align="left">
If the total charge was above its threshold, it would send a send an electric signal to turn on a light. (Yes, that's a triangle!)
</p>

<p align="left">
But, if the electric charge was too weak to hit the threshold, the machine would not do anything, and the light would not turn on. (No, that's not a triangle!)
</p>

<p align="left">
At first, the perceptron was basically making random guesses. To train the perceptron with supervision, Rosenblatt used yes and no buttons. <br>
If the perceptron was correct, he would push the yes-button, and nothing would change. <br>
If the perceptron was wrong, he would push the no-button, which would set off a chain of events that adjusted how much electricity crossed the synapses and adjusted the machine's threshold level. This made the perceptron more likely to get the answer correct next time. <br>
</p>
  
<p align="left">
Nowadays, we can use modern computers to program AI to behave like neurons. <br>
First the artificial neurons receives inputs multiplied by different weights, which correspond to the strength of each signal. <br>
The threshold is represented by a special weight called the **bias**, which can be adjusted to raise or lower the neuron's eagerness to fire. <br>
</p>
  
<img src="/assets/img/portfolio/project3/perceptron.png" width="500">

<p align="left">
All the inputs are multiplied by their respective weights, added together, and a mathematical function gets the result. <br>
In the simplest AI systems, this function is called a step function, which can only output a 0 or 1. <br>
If the sum is less than the bias, then the neuron will output a 0, which could indicate not-triangle (or, something different depending on the task). <br>
If the sum is greater than or equal to the bias, then the neuron will output a 1, which indicates the opposite result. <br>
An AI can be trained to make a decision about anything, where you have enough data and supervised labels.
</p>

### Bagels vs. Donuts Example
<p align="left">
Bagels and donuts might look super similar to each other, so we want to be able to distinguish between the two. <br>
Suppose we measure the mass and diameter of bagels, and supervise a program so it gets better at labeling them. Initially, the program does not know anything about bagels, donuts, or what their masses or diameters might be. The program will initially use random weights for mass, diameter, and bias to make a decision between whether something is a donut or bagel. As the program learns, the weights will be updated. <br>
We can use different mathematical functions to account for how far an AI is from the right decision. <br>
</p>

<p align="left">
We'll keep it simple and use a step function (an either-or-choice, like bagel or donut).
</p>

<p align="left">
Let consider a mixed bag of donuts and bagels. Suppose we pull out our first item, and it happens to be a donut with a mass of 34 grams and a diameter of 7.8 cm. The perceptron takes these inputs, multiplies them by their respective weights, and adds them together.
</p>

<p align="left">
The bias is like the bagel threshold. If the summer is greater than or equal to the bias (which is the threshold for the neuron firing), the program will output bagel. If the sum is less than the bias (i.e. it has not crossed the bagel threshold), the program will output donut. 
</p>


<p align="left">
We can think of this program as a graph, with the mass on one axis and the diameter on the other. The weights and bias are used to calculate a line called a decision boundary on the graph, which separates bagels from donuts. 
</p>
