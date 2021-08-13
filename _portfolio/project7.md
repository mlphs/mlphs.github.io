---
title: Reinforcement Learning
subtitle: Lesson 7
image: assets/img/portfolio/project7/tic-tac-toe.png
alt: 

caption:
  title: Reinforcement Learning
  subtitle: Lesson 7
  thumbnail: assets/img/portfolio/project7/tic-tac-toe.png
---
<p align="left">
We learn lots of things by trial-and-error. This kind of “learning by doing” to achieve complicated goals is called Reinforcement Learning. 
Reinforcement Learning is particularly useful for situations where we want to train AIs to have certain skills we don’t fully understand ourselves. <br> <br>

For example, I’m pretty good at walking, but trying to explain the process of walking
is kind of difficult. With reinforcement learning, we can train AIs to perform complicated tasks.
Unlike other techniques, we only have to tell them at the very end of the task if they succeeded, and then ask them to tell us how they did it. <br> <br>

Here are some real world examples of where RL is useful: <br>
>> Self-driving cars: cars can use computer vision (to see roads, other cars, pedestrians, etc) and route guidance features (e.g. maps, GPS) to learn control
   braking, acceleration, turning, and more <br>
>> Game bots: We could build an agent to play a game in which we can write down the rules and logic <br>
>> Business Analytics: We could train an agent to buy or sell stocks based on a variety of stock market indicators <br> <br>


If we want an AI to learn to walk, we give them a reward if they’re both standing up and moving forward, and then figure out what steps they took to get to that point.
The longer the AI stands up and moves forward, the longer it’s walking, and the more reward it gets. The key to reinforcement learning is just trial-and-error. <br> <br>

For humans, an example of a reward might be a cookie. For an AI system, a reward is a small positive signal that basically tells it “good job” and “do it again!”. <br> <br>

In reinforcement learning, we have an agent that is going to learn. An agent makes predictions or performs actions, e.g., moving a tiny bit forward, or picking the next best move in a game.
The agent performs actions based on its current inputs, which we call the state. <br> <br>

In supervised learning, after each action, we would have a training label that tells our AI whether it did the right thing or not. We can’t do that here with reinforcement
learning, because we don’t know what the “right thing” actually is until it’s completely done with the task. This difference actually highlights one of the hardest parts of
reinforcement learning called credit assignment. It’s hard to know which actions helped us get the reward and which actions slowed down our AI when we don’t pause to think 
after every action. <br> <br>

The agent ends up interacting with its environment and takes many actions until it gets a reward. Every time the agent succeeds at its task, we can look back on the actions
it took and slowly figure out which game states were helpful and which weren’t. <br> <br>

During this reflection, we’re assigning value to those different game states and deciding
on a policy for which actions work best. <br> <br>

Let’s take a look at an example. Consider the game Tic-Tac-Toe. 
</p>
  
<img src="assets/img/portfolio/project7/tic-tac-toe.png" width="500">

<p align="left">
The state is the current status of the environment. In the game of tic-tac-toe, the state would be the board and the position of all existing marks.

The agent gets to observe the state and then try to choose the optimal action.

The agent receives positive rewards for winning and negative rewards for losing/tying.

The action is the “move” in which the agent chooses.

</p>

### Sources
1. [Reinforcement Learning: Crash Course AI #9](https://www.youtube.com/watch?v=nIgIv4IfJ6s&list=PLH2l6uzC4UEVGUu2--3xBjTMFily1IwP9&index=11)
2. [Lecture 9: Reinforcement Learning - High School Machine Learning](https://www.youtube.com/watch?v=HlmB-zM8C3M&list=PL3yIcCK-hyoODmv6Gl8H1snvrqLvdwIqI&index=9)
