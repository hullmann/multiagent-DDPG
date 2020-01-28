# Deep Reinforcement Learning Udacity Nanodegree
## Project 3: Collaboration and Competition

The [Unity ML-Agents toolkit](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md) contains the [Tennis Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) in which two tennis rackets keep the ball in the game by bouncing it over the net. 
In the [Collaboration and Competition Project](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet) of the [Deep Reinforcement Learning Udacity Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893), the Tennis environment has been slightly adapted by Udacity, so there might be differences to the original environment. In a nutshell, we teach the agents to play using a Multiagent Deep Deterministic Policy Gradient method. 

[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"

![image1]

### Project details
In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

Due to the continuous action space, classical value-based methods are hard to apply. Instead, we solve the environment using the Multiagent Deep Deterministic Policy Gradient (DDPG) method. This is a flavour of an actor-critic method, where the actor is trained to maximize the expected outcome as is predicted by the critic network. As a twist, our critics also _see_ the observation space and next actions of the opponents. This is allowed, as this only happens during training. When we test the agents, we don't need the critics anymore, and the actors only rely on their local observations.

I worked on this project as part of the [Deep Reinforcement Learning Udacity Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893) and adapted the DDPG agent code from the [Pendulum project in Udacity's Deep Reinforcement Learning Repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum) and turned it into a multiagent version.

## Getting Started

1. Set up your environment according to the instructions of the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies)

2. Clone this GitHub repository [multiagent-DDPG](https://github.com/hullmann/multiagent-DDPG)

3. Udacity provides a modified Unity environment. Please download the one matching your OS from the links below:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

Place the file in the `multiagent-DDPG/` folder (cloned in step 2.), and unzip the file. 

## Instructions
Follow the instructions in [Tennis.ipynb](https://github.com/hullmann/multiagent-DDPG/blob/master/Tennis.ipynb) to train your agent or scroll to the bottom of the code to let the agent run based on pretrained weights. Technical details of the solution are documented in [Report.ipynb](https://github.com/hullmann/multiagent-DDPG/blob/master/Report.ipynb) .
