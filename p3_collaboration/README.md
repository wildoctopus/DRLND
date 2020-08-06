Project 3: Collaboration and Competition

Project Discription: 
[insert image tennis.png]
In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

    After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
    This yields a single score for each episode.

The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.


Environment/Project setup:
Follow the instructions below to explore the environment on your own machine! You will also learn how to use the Python API to control your agent.

Step 1: Clone this repo in your local machine.

Step 2: Download the Unity Environment

For this project, you will not need to install Unity - directly download the prebuilt unity environment from one of the links below. You need only select the environment that matches your operating system:

Linux: click here
Mac OSX: click here
Windows (32-bit): click here
Windows (64-bit): click here

Then, place the file in the p3_collaboration/ folder in your cloned repository, and unzip (or decompress) the file.

Instructions:

Follow the instructions provided in Navigation.ipynb to get started with training your own agent! For information on how the algorithm works and future improvements that can be done, check Report.md file.
