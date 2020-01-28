# Deep Reinforcement Learning Udacity Nanodegree
## Project 3: Collaboration and Competition

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

The [Unity ML-Agents toolkit](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md) contains the [Reacher Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) in which double-jointed arms have to move to target locations (see [video](https://www.youtube.com/watch?v=2N9EoF6pQyE)).

[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"

![image1]

### Project details

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

In a nutshell, we teach the robotic arms to follow the targets by the Deep Deterministic Policy Gradient method.

This environment rewards a reacher in the target location with +0.1. The vector observation space is 33 dimensional and the vector action space has 4 dimensions corresponding to the torque applicable to two joints. The environment is considered 'solved' when an average reward of +30 per episode is achieved. 

Due to the continuous action space, classical value-based methods are hard to apply. Instead, we solve the environment using the Deep Deterministic Policy Gradient (DDPG) method. This is a flavour of an actor-critic method, where the actor is trained to maximize the expected outcome as is predicted by the critic network. The twenty different robotic arms share their experiences and thus learn faster than a single actor.

I worked on this project as part of the [Deep Reinforcement Learning Udacity Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893) and adapted the DDPG agent code from [Pendulum project in Udacity's Deep Reinforcement Learning Repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum)

## Getting Started

1. Set up your environment according to the instructions of the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies)

2. Clone this GitHub repository [multiagent-DDPG](https://github.com/hullmann/multiagent-DDPG)

3. Udacity provides a modified Unity environment. Please download the one matching your OS from the links below:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

Place the file in the `continuouscontrol-DDPG/` folder (cloned in step 2.), and unzip the file. 

## Instructions
Follow the instructions in [Continuous_Control.ipynb](https://github.com/hullmann/continuouscontrol-DDPG/blob/master/Continuous_Control.ipynb) to train your agent or scroll to the bottom of the code to let the agent run based on pretrained weights. Technical details of the solution are documented in [Report.ipynb](https://github.com/hullmann/continuouscontrol-DDPG/blob/master/Report.ipynb) .
