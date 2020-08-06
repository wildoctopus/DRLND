# Project 2: Continous Control

## Project Discription:
For this project, we have to work with the Reacher environment.
![](https://github.com/wildoctopus/DRLND/blob/master/p3_collaboration/reacher.gif) <br>
caption - Unity ML-Agents Reacher Environment


In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of our agent is to maintain its position at the target location for as many time steps as possible.
The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

Now this project require to solve one of the two versions of the environment.
* Option 1: Solve the First Version

The task is episodic, and in order to solve the environment, our agent must get an average score of +30 over 100 consecutive episodes.

* Option 2: Solve the Second Version

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, our agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

    After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different)         scores. We then take the average of these 20 scores. This yields an average score for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 


## Getting statrted - Project/Environment setup: 

Follow the instructions below to explore the environment on your own machine! You will also learn how to use the Python API to control your agent.

* Step 1: Clone this repo in your local machine.

* Step 2: Download the Unity Environment

For this project, you will not need to install Unity - directly download the prebuilt unity environment from one of the links below. You need only select the environment that matches your operating system:

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip) 
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

Then, place the file in the p2_continous-control/ folder in your cloned repository, and unzip (or decompress) the file.

## Instructions:
Follow the instructions provided in Continous_Control.ipynb to get started with training your own agent! For information on how the algorithm works and future improvements that can be done, check Report.md file.



## References :

The problem description has been taken from Udacity [DRLND course](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893)
