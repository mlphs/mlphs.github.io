---
title: The Perceptron
subtitle: Lesson 3
image: assets/img/portfolio/project3/perceptron.png
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

<p align="left">
If we represent this bagel as a data point, we would graph it at (20, 5). This data point is above the decision boundary, and therefore in the bagel zone. Thus, when we ask the program what the first item we pulled out of the bag is, the program will output bagel, which is wrong because the item is a donut. 
</p>

<img src="/assets/img/portfolio/project3/donut-perceptron.png" width="500">

<p align="left">
Since the program is initially using random weights, the program essentially makes a random guess. We can help the program learn by updating its weights. So, we take an old weight and add a number calculated with an equation called an update rule.
</p>

<p align="left">
Because our perceptron can be completely right or completely wrong, the update rule is relatively simple. 
</p>


<p align="left">
If the program makes the right prediction of labelling the donut as a donut, we add 0 to the weight, and the weight stays the same.
</p>

<p align="left">
But, if the program makes the wrong prediction and labels the donut as a bagel, the update rule has a value, which is a small positive or small negative number. We will add that value to the weight, and the weight will change.
</p>

<p align="left">
Conceptually, this means the program learns from failure, but not from success. 
</p>

<p align="left">
We pulled a donut out of the bag, and the program predicted that the item was a bagel. So, we will let the program know that it made the wrong choice, and it will consequently update its weights. <br>
When the weights update, the decision boundary changes. The datapoint we added is now below the decision boundary line and in the donut zone.
</p>

<img src="/assets/img/portfolio/project3/bagel-perceptron.png" width="500">

<p align="left">
Now, the program will classify another item with this mass and diameter as a donut. <br>
Suppose we pull out a second item with a mass of 40 grams and a diameter of 2.5 cm. We give this to the program, and it predicts that the item is a donut correctly. The data point appeared below the decision boundary in the donut zone.
</p>

<img src="/assets/img/portfolio/project3/bagel-perceptron-2.png" width="500">

<p align="left">
We let the program know that its prediction was correct, so the weights stay the same and so does the decision boundary. <br>
Now, we can do this many more times to train the program's perceptron. 
</p>

<p align="left">
After we have trained the program, we have to test it on a bunch of new data to see how well the program learned. We can visualize the results in a confusion matrix. We can add together what the program got right and dividing by the total number of items to get the test accuracy. 
</p>

|                | Predicted Donut | Predicted Bagel | Total     |
| :---           |    :----:       |          :----: |      ---: |
| Actually Donut | 8               | 17              | 25        |
| Actually Bagel | 2               | 73              | 75        |
| Total          | 10              | 90              | 100 Total |        

(8 + 73)/ 100 = 81%

<p align="left">
To really understand what is wrong, we can look at the <b>precision</b> and <b>recall</b>.
</p>

<p align="left">
<b>Precision</b> tells you how much you should trust your program when it says it found something. Of the 10 donuts we gave the program, it said 8 of them were actually donuts, so the program is 80% precise, and we can be 80% sure that the program is giving us donuts when the items are actually donuts. 
</p>

<p align="left">
<b>Recall</b> tells you how much your program can find the thing you are looking for. Of the 25 items that were donuts, the program correctly labelled 8 of them. So, the program's recall is 32%.
</p>

<p align="left">
The precision and recall depend on the criteria the program is using to make a decision. As we can see in the graph below, the program generally thinks that donuts generally have smaller diameter and mass than bagels.
</p>

<img src="/assets/img/portfolio/project3/donut-bagel-perceptron.png" width="500">

<p align="left">
When it comes to classifying donuts, the program has high precision because if it says something is a donut, we're pretty sure it is actually a donut. But the program has some recall, because some donuts can be bigger than the donuts we used to train the perceptron program and might fall in the bagel zone.
</p>

<p align="left">
Figuring out what criteria to use is the key for most AI challenges. If we wanted better  accuracy for this donut vs. bagel problem, we could have used inputs other than mass and diameter, such as checking for whether the item has seeds or sprinkles.
</p>


